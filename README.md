# CloudNode-CDS-v2
Shell script to install a [Cloudnode Masternode]on a Linux server running Ubuntu 16.04 or Ubuntu 18.04.  
This script will install **Cloudnode**.

## Installation:
```
 git clone https://github.com/udaydeep1992/cds-mn-installer.git
 cd cds-mn-installer
 chmod -R 755 cds.sh
 bash cds.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps for Windows Wallet
1. Open the Cloudnode Wallet.
2. Go to RECEIVE and create a New Address: **MN1**
3. Send **10000000** **CDS** to **MN1**.
4. Wait for confirmations.
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
* Output index:  **Second value from Step 6** It can be **0** or **1**
9. SAVE and exit the Wallet.
10. Open CDS Wallet, go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again.
10. Click **Start All** or **Start Alias**
11. If then also not starting then click on >tools>debug console> Type: startmasternode alias false "name of your MN alias"

***

## To check the status in your VPS:
```
cloudenode-cli getinfo
cloudenode-cli masternode status
cloudenode-cli mnsync status
```
Also, if you want to check/start/stop **cds** , run one of the following commands as **root**:
```
systemctl status CDS.service #To check the service is running.
systemctl start CDS.service #To start cds service.
systemctl stop CDS.service #To stop cds service.

```
***

