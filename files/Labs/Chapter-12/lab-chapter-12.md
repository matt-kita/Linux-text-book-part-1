# Lab - Chapter 12

1) Using two virtual machines, while powered off, in the VirtualBox settings, enable a second network interface and set the type to **Bridged Adapter** (details are in last chapter and the VirtualBox networking details are in chapter 03).

   a. Capture a screenshot of each system using the `ping` tool to ping the other IP and its results.
   b. Modify the `/etc/hosts` file and add an entry for both system in both systems.
   c. Execute the `ping` command again this time using the hostname declared in the `/etc/hosts` file.

2) Repeat the above exercise but deactivate NetworkManager in systemctl and activate systemd-networkd (CentOS).

   a. In addition, on Ubuntu modify the Netplan conf to use networkd and place your YAML configuration there.

3) Using firewalld, open port 22 permanently to allow SSH connections to your Fedora or CentOS system.

4) Using firewalld, open port 80 permanently to allow SSH connections to your Fedora or CentOS system.

5) Enable the firewall to start at boot and show its status after a successful boot.

6) Install and enable firewalld on Ubuntu, deactivate UFW if it is running.

7) Create a self-signed SSL certificate.

8) Create a sample PHP webpage that displays `phpinfo()` at "https://localhost/index.php". Name the file `info.php` and push it to your GitHub repo.

   a. Make sure you have installed all the pre-reqs (Apache2 and PHP).

9) Enable the Apache Webserver and the proper firewall port to serve yoru `phpinfo()` page over **https** following [this Digital Ocean configuration tutorial](https://www.digitalocean.com/community/tutorials/how-to-create-a-self-signed-ssl-certificate-for-apache-in-ubuntu-18-04 "Digital Ocean Self-signed Apache2 cert config").

10) Going to [Wordpress.org](https://wordpress.org "Wordpress install") and download the latest tar.gz file.  Follow the 5 minute setup to configure a working WordPress blog.

11) Repeat the install process above, this time using two servers, with static IP addresses configured, placing the MySQL database on a separate IP address -- configuring WordPress properly and installing all needed pre-reqs.

    a. Make sure to open the proper firewall ports and note that the first server will be the webserver and requires the apache2, php, php-mysql, and the php-client library only.
    b. The second database server requires the `mysql-server` package.  Make one to be Ubuntu, and the other to be Fedora/CentOS.

12) Install the Ghost Blogging Platform on a single OS of your choice.

    a. Install nodejs, nginx, and mysql prerequisites.
    b. Create a directory in your home directory called **ghost-files**. Execute the install tutorial in the next step in that directory.
    c. Follow the install instructions at [Ghost.org](https://github.com/TryGhost/Ghost "Ghost Blogging Platform") to install the Ghost blogging platform.

13) Create a shell script to automate the following steps.  Name the shell script: `install-env.sh` and push it to your chapter-12 folder in GitHub along side the lab answers as well as place the content of the script as an answer to this questions.

    a. Use two fresh Ubuntu 18.04 Desktop Virtual Machines
    b. Determine the IP addresses ahead of time for each system (use a bridged network)
    c. Dedicate one server as web-frontend and one as database backend
    d. Install and activate Firewalld, open ports 22, 80, 443
    e. Download and install latest Wordpress tarball (look at using `sed -i` to do an in-place substitution of the default values in the wordpress config file).
    f. Create a self-signed Cert and configure Apache2 to use that cert.
    g. Configure the firewall to only allow single IP connection for SSH and port 80 and 443.
    h. use the `firefox` command to launch the WordPress Welcome page using HTTPS