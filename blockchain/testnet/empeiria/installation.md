# Installation

### Install Dependencies

```bash
sudo apt update && sudo apt upgrade -y 
sudo apt install -y git gcc make unzip jq
```

### tall GO if needed <a href="#tall-go-if-needed" id="tall-go-if-needed"></a>

```bash
ver="1.22.2"
cd $HOME
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> ~/.bash_profile
source ~/.bash_profile
go version
```

### Set Vars <a href="#sett-vars" id="sett-vars"></a>

change MONIKER="Moniker" with your own moniker and change SYMPHONY\_PORT="14" to your own port

```bash
echo "export WALLET="wallet"" >> $HOME/.bash_profile
echo "export MONIKER="Moniker"" >> $HOME/.bash_profile
echo "export EMPED_CHAIN_ID="empe-testnet-2"" >> $HOME/.bash_profile
echo "export EMPED_PORT="14"" >> $HOME/.bash_profile
source $HOME/.bash_profile
```

#### Install Binary <a href="#install-binary" id="install-binary"></a>

```bash
cd $HOME
curl -LO https://github.com/empe-io/empe-chain-releases/raw/master/v0.1.0/emped_linux_amd64.tar.gz
tar -xvf emped_linux_amd64.tar.gz 
mv emped ~/go/bin
```

### Initialize Node <a href="#initialize-node" id="initialize-node"></a>

```bash
emped init $MONIKER --chain-id empe-testnet-2
emped config chain-id $EMPED_CHAIN_ID
emped config keyring-backend test
```

### Download Genesis and Addrbook <a href="#download-genesis-and-addrbook" id="download-genesis-and-addrbook"></a>

```bash
wget -O $HOME/.empe
```
