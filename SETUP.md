# SETUP instructions
## install node
https://github.com/nodejs/help/wiki/Installation
### download node
`wget https://nodejs.org/dist/v12.18.2/node-v12.18.2-linux-x64.tar.xz` or whatever version you need
### unpack
`tar -xf node-v12.18.2-linux-x64.tar.xz`

### update path
`nano ~/.profile`
`export PATH=[...]/bin:$PATH`

### refresh path
`. ~/.profile`

### install dependencies
`npm install -g ionic@latest`


## install repo
`git clone https://github.com/azyth/viduVigils.git`

`cd viduVigils`
`npm install`

INSTALLED!

### Run
`ionic serve`

OpenVidu Platform service must be up and running in your development machine. The easiest way is running this Docker container which wraps both of them (you will need Docker CE):

## Get docker
https://docs.docker.com/engine/install/ubuntu/
`sudo apt-get remove docker docker-engine docker.io containerd runc`
`sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common`
### add fingerprint
`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
`sudo apt-key fingerprint 0EBFCD88` // veryfy public key matches `9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88`
`sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"`

`sudo apt-get update`
`sudo apt-get install docker-ce docker-ce-cli containerd.io`

### list versions
`apt-cache madison docker-ce`
### test
`sudo docker run hello-world`

`docker run -p 4443:4443 --rm -e OPENVIDU_SECRET=MY_SECRET openvidu/openvidu-server-kms:2.14.0`

Go to `localhost:8100` to test the app once the server is running