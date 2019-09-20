<div align="center">

<img src="https://cdn.jsdelivr.net/gh/jscdn/svg@1.0.1/bhadoo-cloud-logo.svg" data-canonical-src="https://cdn.jsdelivr.net/gh/jscdn/svg@1.0.1/bhadoo-cloud-logo.svg" height="80" />

Fetch Torrents using .torrent file or Magnet Links, Fetch Files from Other Servers to Own Server and Upload to Google Drive.

Open URLs in Proxy to bypass Restrictions (works like VPN), Check [Demo](https://server1.bhadoocloud.ga) and [Demo Site Status](https://site-status.hashapp.ga/?q=server1.bhadoocloud.ga)

![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/parveenbhadoo/bhadoocloud.svg)
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/parveenbhadoo/bhadoocloud.svg?style=flat)
![Docker Pulls](https://img.shields.io/docker/pulls/parveenbhadoo/bhadoocloud.svg)
![Docker Stars](https://img.shields.io/docker/stars/parveenbhadoo/bhadoocloud.svg)
![Docker Size](https://images.microbadger.com/badges/image/parveenbhadoo/bhadoocloud.svg)
![Docker Version](https://images.microbadger.com/badges/version/parveenbhadoo/bhadoocloud.svg)

![GitHub repo size](https://img.shields.io/github/repo-size/parveenbhadooofficial/bhadoocloud.svg)
![GitHub last commit](https://img.shields.io/github/last-commit/parveenbhadooofficial/bhadoocloud.svg)

</div>

![screenshot](https://raw.githubusercontent.com/ParveenBhadooOfficial/Bhadoo-Cloud/master/.github/screenshot02.png)

# Usage

Info: Heroku is not supported, Use AWS EC2 (1 Year Free), G Cloud (300$ for 1 Year Free), MS Azure (30 Days Free) for Bhadoo Cloud Installations.

Installation on [AWS Cloud](https://aws.amazon.com/ec2/)

* Select an Ubuntu 18.xx Server Image
* Use [Putty](https://www.putty.org/) to Login using SSH
* Follow the below commands one by one.

```
  sudo apt-get update && sudo apt-get upgrade
  sudo apt-get install linux-image-extra-virtual
```

```
  sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```

```
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```
  sudo apt-key fingerprint 0EBFCD88
```

```
  sudo add-apt-repository \
     "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) \
     stable"
```

```
  sudo apt-get update
```

```
  sudo apt-get install docker-ce
```

```
  sudo docker run hello-world
```

* You'll see a Line saying Hello World that means everything you've done worked till now

```
  sudo usermod -a -G docker $USER
```

* Replace `$USER` with your username, it maybe be `ubuntu` by default.
* Close Putty and Login again.

```
  docker run --name ct -d -p 80:3000 \
    --restart always \
    -e GOOGLE_CLIENT_ID='***' -e GOOGLE_CLIENT_SECRET='***' -e GOOGLE_REDIRECT_URL='***/oauthCallback' \
    parveenbhadoo/bhadoocloud node server/server.js
```

Fill `***` with appropriate values from Google Developer Console.

* You can also Delete the Container using below if needed.

```
  docker stop $(docker ps -a -q)
  docker rm $(docker ps -a -q)
```

* You can also remove pulled image to pull latest image again.

```
  docker images -a
  
  docker rmi Image Image2
```

Replace Image with Docker Image ID (Multiple Supported)

# Get Google_Client_ID and Secret

* Open [Google Dev Credentails Site](https://console.developers.google.com/apis/credentials).
* Create a Project, name as you like.
* Enable [Drive API](https://console.developers.google.com/apis/library/drive.googleapis.com)
* In [Credentails Page](https://console.developers.google.com/apis/credentials) Click `Create Credentials` and then Click `OAuth Client ID`.
* Select Web Application.
* In `Authorized JavaScript origins` enter your domain name or IP whichever you are using for Bhadoo Cloud.
* In `Authorized redirect URIs` enter your domain name or IP with `/oauthCallback` at last.
* Use http:// or https:// as available.
* If you are using Cloudflare for website use https:// and Set Flexible HTTPS in Cloudflare.
* Copy your details and use above.
* `GOOGLE_REDIRECT_URL` is same as `Authorized redirect URIs`

# Resources

* subdomain.bhadoocloud.ga are available to use with our Google Credentials. Email admin[at]hashhackers[dot]com

* [Video: How to install Bhadoo Cloud on Amazon Web Services (AWS)](https://youtu.be/yhsQU6uXNMA)

* [Video: How to use Bhadoo Cloud to Upload Torrents or Files to Google Drive](https://youtu.be/ynRkZ1OaQSQ)

* [Video: How to remove Docker Images from AWS Server to Fetch Latest Images](https://youtu.be/SGrB0oo8F_4)

* [Proxy Server](https://github.com/ParveenBhadooOfficial/PHP-Web-Proxy)


Build from [github.com/Mrigank11/embetacloud](https://github.com/Mrigank11/embetacloud) and [github.com/jpillora/cloud-torrent](https://github.com/jpillora/cloud-torrent)

License [MIT](https://github.com/ParveenBhadooOfficial/BhadooCloud/blob/master/LICENSE)

Contributions are Welcome.

## Supported By

[![BrowserStack](https://raw.githubusercontent.com/ParveenBhadooOfficial/BhadooCloud/master/files/browserstack.png)](https://www.browserstack.com/)

Supported by [BrowserStack](https://www.browserstack.com/), which allows us to test projects online with any browser as a service. :-)

Document Last Updated on 11:34 am Sunday, 20 September 2019 (IST).
