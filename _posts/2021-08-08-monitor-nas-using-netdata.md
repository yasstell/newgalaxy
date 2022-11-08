---
title: Superviser son NAS Synology avec netdata
date: 2021-08-08 14:00:00 +0800
categories: [Synology]
tags: [synology, netdata]
image:
  src: /img/nas_monitoring.png
  width: 800
  height: 500
---

Netdata is a free open-source monitoring tool. It is fast and lightweight (perfect for home servers and NAS equipment). It doesn't require much resources to run the agent and collect system and applications metrics. The tool can also display real-time monitoring information on the dashboard.
Netdata can run on any linux distribution and even on other platforms. The good news is that it can also be installed on synology NAS.

Here is how to proceed :

### Step 1 : enable SSH and login to synology NAS

The first step consists on enabling SSH on your Synology NAS. To do so, you have to check SSH service in Terminal & SNMP menu.

{{< figure src="/img/2020/monitor-synology-netdata1.PNG" >}}

If you plan to maintain SSH enabled, I recommend to change the SSH port. For security reasons, it's not safe to keep the default 22 port, especially if your NAS is reachable from outside the local network.

Then you can connect to your Synology NAS using SSH via a tool such as Putty or from a terminal using this command :

```
ssh USER_OF_YOUR_NAS@IP_ADDRESS_OF_YOUR_NAS
```

### Step 2 : install Netdata

The installation procedure is quite simple. You have to download the script with wget or curl and then execute the script to start installation.
Here are the commands to use :

```
  wget -O /tmp/kickstart-static64.sh https://my-netdata.io/kickstart-static64.sh
  sh /tmp/kickstart-static64.sh
```
During the installation you will need to :

  - enter your password
  - accept installation by entering "y"

Once the installation is finished, you will be able to open the dashboard of netdata using this url :
http://IP_ADDRESS_OF_YOUR_NAS:19999

More information can be found here :
https://learn.netdata.cloud/docs/agent/packaging/installer/methods/kickstart-64

### Step 3 : run as a specific user

This step is not mandatory as netdata is already running using root after step 2. However it's better to create a specific user for this purpose. Here are the steps to follow on your Synology NAS :

 1. Create a group netdata via the Synology group interface. Disable any access to folders and applications.
 2. Create a user netdata via the Synology user interface. Give it a random password. Disable any access to folders and applications. Assign the user to the netdata group.
 3. Change the ownership of the following directories using SSH :

```
sudo chown -R root:netdata /opt/netdata/usr/share/netdata
sudo chown -R netdata:netdata /opt/netdata/var/lib/netdata /opt/netdata/var/cache/netdata
sudo chown -R netdata:root /opt/netdata/var/log/netdata
```

More information can be found here :
https://learn.netdata.cloud/docs/agent/packaging/installer/methods/synology

### Step 4 : create startup script

In order for netdata to run automatically at startup you need to perform more operations. Here are the steps to follow :

 1. Add this file (https://gist.github.com/oskapt/055d474d7bfef32c49469c1b53e8225f) as /etc/rc.netdata and make it executable with chmod 0755 /etc/rc.netdata.

```
sudo curl https://gist.githubusercontent.com/oskapt/055d474d7bfef32c49469c1b53e8225f/raw/6444ef9e9995acc98aadd316e96017a8d64425fb/rc.netdata >> /etc/rc.netdata
sudo chmod 0755 /etc/rc.netdata
```

 2. Create the file /etc/rc.local and make it executable with chmod 0755 /etc/rc.local.

 ```
 sudo touch /etc/rc.local
 sudo chmod 0755 /etc/rc.local
 ```

 3. Edit the file /etc/rc.local and add this line :

```
# Netdata startup
[ -x /etc/rc.netdata ] && /etc/rc.netdata start
```

More information can be found here :
https://learn.netdata.cloud/docs/agent/packaging/installer/methods/synology

### Step 5 : update netdata

If you need to update netdata in order to have the latest build you have just to run the installation script again (As described in step 1). The script will stop netdata, download the latest build and install it.

### Step 6 : add netdata to Homeassistant

If you have Homeassistant, you can add netdata to your configuration.
You will need to add this to your configuration.yaml file :

```yaml
    panel_iframe:
      nas:
        title: 'NAS'
        url: http://IP_ADDRESS_OF_YOUR_NAS:19999
        icon: mdi:server
```
Here is the result on my homeassistant :
{{< figure src="/img/2020/monitor-synology-netdata2.PNG" >}}
