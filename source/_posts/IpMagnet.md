---
title: IpMagnet
date: 2018-02-09 19:12:25
tags: dev
---
## How To Setup IpMagnet To View What Ip You Are Sending To Torrent Trackers

### Assumptions
  You already have an AWS account
### How To
1. Provision an Amazon Linux AMI 2017.09.1 (HVM), SSD Volume Type EC2 instance
  - I used a t2.micro with all the defaults and had no issues
2. SSH into your new instance and install updates when prompted
3. Follow the guide listed in the install-LAMP link below up until you hit the MySQL Setup
4. sudo yum install git
5. cd into the /var/www/html directory
6. `git clone https://github.com/cbdevnet/ipmagnet.git`
7. Update the index.php file in the ipmagnet directory according to github instructions
  - Change the tracker URL (line 2) to point to the public location of the index.php file. `http://your.public.ec2.dns/ipmagnet/`
8. `sudo nano /etc/httpd/conf/httpd.conf`
9. Add snippet from github repo to prevent people from downloading SQLite db
`<Files "ipmagnet.db3">
	Order allow,deny
	Deny from all
</Files>`
10. Restart the apache server `sudo /etc/init.d/httpd restart`
11. You should now be able to navigate to `http://your.public.ec2.dns/ipmagnet` and download the magnet link
12. Shortly after initiating the magnet link download your ip address should appear in the browser
![Example](https://i.imgur.com/2UyPie8.png "Example")

---
## Resources

[https://torrentfreak.com/vpn-proxy-working-check-torrent-ip-address-140419/](https://torrentfreak.com/vpn-proxy-working-check-torrent-ip-address-140419/)
[https://github.com/cbdevnet/ipmagnet](https://github.com/cbdevnet/ipmagnet)
[https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html)
