<p style="font-size:14px" align="right">
<a href="https://discord.gg/hcbT5ryUdF" target="_blank">Join NodeRobin discord <img src="https://camo.githubusercontent.com/0ef309f7e0b554033dd25b3ce83015db2f0f8952fb4c31318af095369d3d4453/68747470733a2f2f7669676e657474652e77696b69612e6e6f636f6f6b69652e6e65742f7468652d6d696e6572732d686176656e2d70726f6a6563742f696d616765732f642f64642f446973636f72642e706e672f7265766973696f6e2f6c61746573743f63623d3230313730333038303333353436" width="30"/></a>
</p>

<p style="font-size:14px" align="right">
<a href="https://hetzner.cloud/?ref=y8pQKS2nNy7i" target="_blank">Deploy your VPS using our referral link to get 20€ bonus <img src="https://user-images.githubusercontent.com/50621007/174612278-11716b2a-d662-487e-8085-3686278dd869.png" width="30"/></a>
</p>

<p align="center">
  <img height="100" height="auto" src="https://user-images.githubusercontent.com/50621007/176226900-aae9149d-a186-4fd5-a9aa-fc3ce8b082b3.png">
</p>

## Setting up vars
>Replace `YOUR_NODENAME` below with the name of your node
```
NODENAME=<YOUR_NODENAME>
```

Save and import variables into system
```
echo "export NODENAME=$NODENAME" >> $HOME/.bash_profile
source $HOME/.bash_profile
```

# Install peaq node
To setup peaq node follow the steps below

## Update packages
```
sudo apt update && sudo apt upgrade -y
```

## Install dependencies
```
sudo apt install curl jq ocl-icd-opencl-dev libopencl-clang-dev libgomp1 -y
```

## Update executables
```
cd $HOME
sudo rm -rf peaq-node
APP_VERSION=$(curl -s https://api.github.com/repos/peaqnetwork/peaq-network-node/releases/latest | jq -r ".tag_name")
wget -O peaq-node.tar.gz https://github.com/peaqnetwork/peaq-network-node/releases/download/${APP_VERSION}/peaq-node-${APP_VERSION}.tar.gz
sudo tar zxvf peaq-node.tar.gz
sudo chmod +x peaq-node
sudo mv peaq-node /usr/local/bin/
```

## Create peaq-node service
```
sudo tee <<EOF >/dev/null /etc/systemd/system/peaqd.service
[Unit]
Description=Peaq Node
After=network.target
[Service]
Type=simple
User=$USER
ExecStart=$(which peaq-node) \\
--base-path ./chain-data \\
--chain agung \\
--port 1033 \\
--ws-port 9944 \\
--rpc-port 9933 \\
--rpc-cors all \\
--pruning archive \\
--name $NODENAME
Restart=on-failure
RestartSec=10
LimitNOFILE=65535
[Install]
WantedBy=multi-user.target
EOF
```

## Run peaq services
```
sudo systemctl restart systemd-journald
sudo systemctl daemon-reload
sudo systemctl enable peaqd
sudo systemctl restart peaqd
```

## Check node logs
```
journalctl -fu peaqd -o cat
```
