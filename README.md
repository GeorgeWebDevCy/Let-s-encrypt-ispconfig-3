# LE4ISPC
Let's Encrypt for ISPConfig 3, Postfix+Dovecot, Pure-ftpd With Auto Updater for ispserver.pem.

# IMPORTANT! 
Before proceeding, you should have followed step 1-5

Securing ISPConfig 3 Control Panel (Port 8080) With Let's Encrypt Free SSL
[Introduction]
[Creating A Website Using ISPConfig Server Hostname FQDN]
1. Create a site for your server in ISPConfig panel via Sites > Website > Add new website. Remember! This is your server website and as such it must contain your server fully qualified domain name (FQDN). I will refer to it as `hostname -f` in this guide, hopefully in can work without any changes for your server as well.

[Accessing ISPConfig Website Online]
2. Check if your server site is ready and accessible online as Let's Encrypt needs to verify your website is accessible before issuing SSL key, certificate and chain file for your server site. You also have to create its dns zone and allow it to properly propagate as Let's Encrypt needs to verify it too.

[Enabling SSL For ISPConfig 3 Control Panel (Port 8080)]
3. If you haven't enabled SSL during ISPConfig setup i.e. for its control panel at port 8080, enable it by typing ispconfig_update.sh in the terminal and select yes for SSL. We don't need this to be a proper key nor do we want to keep it but we want to work faster, thus we can simply enter for all of its fields. When you finished this, the self-signed SSL should already be enabled for your ISPConfig.

[Checking SSL For ISPConfig 3 Control Panel (Port 8080)]
4. Check your browser to confirm by opening ISPConfig control panel at port 8080. Note that you might get some warning at this stage since the created SSL files are self-signed but the browser will confirm that your ISPConfig has SSL enabled or otherwise.

[Securing ISPConfig Website With Let's Encrypt SSL]
5. If the above is done, go back to ISPConfig panel > Sites > Website > Website Name, then click SSL and Let's Encrypt check buttons and save - to create Let's Encrypt SSL files and enable them for your server site. If successful your server site shall now be using this Let's Encrypt SSL files but not your ISPConfig 8080 page. If unsuccessful, you will not be able to proceed further, so do check its log file for a clue.

# HOW-TO FOR NGINX
In your terminal, in root mode, run:
```
wget https://raw.githubusercontent.com/ahrasis/LE4ISPC/master/nginx/le4ispc.sh
chmod +x le4ispc.sh
./le4ispc.sh
```

# HOW-TO FOR APACHE2
In your terminal, in root mode, run:
```
wget https://raw.githubusercontent.com/ahrasis/LE4ISPC/master/apache/le4ispc.sh
chmod +x le4ispc.sh
./le4ispc.sh
```