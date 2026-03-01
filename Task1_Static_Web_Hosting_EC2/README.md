STATIC WEBSITE DEPLOYMENT ON AWS EC2 UBUNTU USING NGINX

  --------------------------------------------------
  STEP 1 — Launch EC2 Instance (AWS GUI)
  --------------------------------------------------
  Go to EC2 → Launch Instance. Choose Ubuntu Server
  22.04 LTS and t2.micro. Create or select a key
  pair. Allow inbound rules: - SSH (22) for login -
  HTTP (80) for website access

  Explanation: This creates your cloud server and
  allows web traffic.
  --------------------------------------------------


  --------------------------------------------------
  STEP 2 — Install Nginx (Web Server)
  --------------------------------------------------
  sudo apt update sudo apt install nginx -y

  Explanation: Nginx is the software that serves
  your website over HTTP.
  --------------------------------------------------

STEP 3 — Upload or Clone Website Files

cd /var/www/html 

sudo apt install git -y 

sudo git clone https://github.com/USERNAME/REPO.git

OR upload using SCP from local machine.

Explanation: Your HTML, CSS, and JS must be inside nginx’s web
directory.

  --------------------------------------------------
  STEP 4 — Move Website Files to Root Folder
  --------------------------------------------------
  Ex: cd split-landing-page
	sudo cp -r . ../ 
	cd ..

  Explanation: Nginx serves files from
  /var/www/html, so files must be in root.
  --------------------------------------------------



  --------------------------------------------------
  STEP 5 — Open Your Website
  --------------------------------------------------
  http://YOUR_PUBLIC_IP

  Explanation: If index.html exists, nginx
  automatically serves your static site.
  --------------------------------------------------
