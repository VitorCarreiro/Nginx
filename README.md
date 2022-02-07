# Nginx configuration for ubuntu.

**First thing first update your machine** ➡️ *apt update && apt upgrade -y*

✔️**Install nginx and ssl-cert**
⬇️
*apt install nginx

systemctl start nginx

apt install ssl-cert*

✔️**Go to** ➡️ *cd /etc/nginx/sites-available/* ⬅️

✔️**Make a copy of default so that if you make a mistake you can always go back to the default settings.**

*cp default secure

nano secure*
⏬

*Remove both :80 lines

And remove # from both :443 lines*

✔️**Add both these lines below snippets.conf**

*ssl_certificate /etc/ssl/certs/(yourcrt.crt);

ssl_certificate_key /etc/ssl/private/(yourkey.key);*

✔️**Change**

*root /var/www/html;

to ⬇️

root /var/www/htmls;*

✔️**Add your certificates to location below**

*/etc/ssl/certs/yourcrt.crt

/etc/ssl/private/yourkey.key*

✔️**Create a soft link of the secure file**

*cd /etc/nginx/sites-enabled/

ln -s /etc/nginx/sites-available/secure secure*

✔️**And your done!

Now check if you have everything working**

*systemctl restart nginx

systemctl status nginx*



