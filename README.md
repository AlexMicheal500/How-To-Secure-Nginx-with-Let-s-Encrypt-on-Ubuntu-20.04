# How-To-Secure-Nginx-with-Let-s-Encrypt-on-Ubuntu-20.04
To carryout this task use the following steps sequencially:

1. Have an application mapped to a port e. 8080:80. (https://www.youtube.com/watch?v=_EBARqreeao&t=9s)
NOTE: Do not use 443:443 or 80:80 because ths will cause an nginx error and if you do "sudo systemctl status nginx", it will fail.

2. Install Nginx (https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04)
NOTE: i. Do not install ssl certificate before doing this step. Else it will fail.
      ii. When firewall is inactive, to activate, use the following commands:
          sudo apt-get install ufw
          sudo ufw allow ssh
          sudo ufw enable
          sudo ufw status

3. Make nginx to be a proxy server using the port 80. (https://www.digitalocean.com/community/tutorials/how-to-configure-nginx-as-a-reverse-proxy-on-ubuntu-22-04)

4. To install SSL certificate follow the link https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04

5. To not allow users have access to your site, from the inbound rule in AWS, remove port 8080. This is for security reason and so the proxy deals with http requests while the ip:8080 deals with the web app.
