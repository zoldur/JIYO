# JIYO
Shell script to install a [Jiyo Masternode](http://www.jiyo.io/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.  
This script will instal version 2.1
***

## VPS installation:
```
wget -N https://raw.githubusercontent.com/zoldur/JIYO/master/jiyo_install.sh
bash jiyo_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the JIYO Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **5000** **JIYO** to **MN1**.
4. Wait for 15 confirmations.
5. Go to **Tools -> "Debug console - Console"**
6. Type the following command: **masternode outputs**
7. Go to  ** Tools -> "Open Masternode Configuration File"
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
12. Open **Debug Console** and type:
```
startmasternode "alias" "0" "MN1"
```
***

## Usage:
```
jiyo-cli mnsync status
jiyo-cli getinfo
jiyo-cli masternode status
```
Also, if you want to check/start/stop **Jiyo** , run one of the following commands as **root**:

```
systemctl status Jiyo #To check the service is running.
systemctl start Jiyo #To start Jiyo service.
systemctl stop Jiyo #To stop Jiyo service.
systemctl is-enabled Jiyo #To check whetether Jiyo service is enabled on boot or not.
```
***
## Old Jiyo delete:
In order to delete your Jiyo Masternode,  please run the following commands:
```
systemctl stop Jiyo
systemctl disable Jiyo
rm -r /root/.jiyo*
rm -r /usr/local/bin/jiyo*
rm -r /etc/systemd/system/Jiyo.service
```
***

## Masternode update:
In order to update your Jiyo Masternode from 2.0 to 2.1, please run the following commands:
```
cd /tmp
wget -N https://github.com/jiyocoin/jiyox/releases/download/v.2.1/jiyo-2.1-linux-64bit.tar.gz
tar xvzf jiyo-2.1-linux-64bit.tar.gz
systemctl stop Jiyo
mv jiyod jiyo-cli /usr/local/bin
systemctl start Jiyo
rm -r jiyo*
```
***

## Donations:

Any donation is highly appreciated.

**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
