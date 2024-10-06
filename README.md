in this repo, server backup id saved.
by load balancer settings
web01 and web02

-----------------for web01 ------------
backup code:
sudo tar -czf lb01_back.tar.gz /etc/haproxy /etc/letsencrypt/ /etc/ssl/ /etc/ufw/
sudo tar -czf web01_back.tar.gz /etc/nginx /etc/datadog-agent/ /etc/gunicorn/ /etc/mysql/ /etc/ufw/
sudo tar -czf web02_back.tar.gz /etc/nginx /etc/datadog-agent/ /etc/gunicorn/ /etc/mysql/ /etc/ufw/

in  the above script, i have backed up key files of my servers
when restoring, it would be ideal to use them all to restore.
my application server is backed by datadog agent. so it is only
present in web01. if i run the restore on web02, it will not
restore because my web02 was not used as appliction server
