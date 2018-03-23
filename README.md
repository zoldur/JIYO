# JIYO
Shell script to install a [Jiyo Masternode](http://www.jiyo.io/) on a Linux server running Ubuntu 14.04 or 16.04. Use it on your own risk.

***
## Installation:
```
wget -q https://raw.githubusercontent.com/zoldur/JIYO/master/jiyo_install.sh
bash jiyo_install.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the JIYO Coin Desktop Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **20000** **JIYO** to **MN1**.
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

**Ubuntu 16.04**:
```
systemctl status Jiyo #To check the service is running.
systemctl start Jiyo #To start Jiyo service.
systemctl stop Jiyo #To stop Jiyo service.
systemctl is-enabled Jiyo #To check whetether Jiyo service is enabled on boot or not.
```
**Ubuntu 14.04**:  
```
/etc/init.d/Jiyo start #To start Jiyo service
/etc/init.d/Jiyo stop #To stop Jiyo service
/etc/init.d/Jiyo restart #To restart Jiyo service
```
***

## Issues
Please update your wallet configuration by adding the following lines:
```
addnode=34.211.45.106:6080
addnode=144.202.98.227:6080
addnode=45.77.252.225:6080
addnode=37.143.9.203:6080
addnode=209.250.250.240:6080
addnode=167.99.81.130:6080
addnode=45.76.210.76:6080
addnode=66.175.209.37:6080
addnode=207.246.94.195:6080
addnode=207.148.125.196:6080
addnode=172.104.23.79:6080
addnode=45.77.116.207:6080
addnode=45.77.73.70:6080
addnode=45.76.232.84:6080
addnode=144.202.100.126:6080
addnode=172.245.156.104:6080
addnode=104.238.184.79:6080
addnode=144.202.120.103:6080
addnode=178.209.127.160:6080
addnode=185.87.193.198:6080
```

## Donations:  

Any donation is highly appreciated.  

**JIYO**: JMtUx8tNK5vuhPcLdUnNKSBAUbeKuFooyC  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB

