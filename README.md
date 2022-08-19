# Networkquality_v2

# Requirement

1-Go 

2-The source code

# Go Installation

```
sudo apt-get update  
sudo apt-get -y upgrade  
```
Now download the Go language binary archive file using following link. To find and download latest version available or 32 bit version go to official download page:https://go.dev/dl/
```
wget https://dl.google.com/go/go1.19.linux-amd64.tar.gz
```
Now extract the downloaded archive and install it to the desired location on the system. For this tutorial, I am installing it under /usr/local directory.


```
sudo tar -xvf go1.19.linux-amd64.tar.gz
sudo rm -r /usr/local/go
sudo mv go /usr/local 
```

Now you need to setup Go language environment variables for your project. Commonly you need to set 3 environment variables as GOROOT, GOPATH and PATH. Create go directory

```
mkdir ~/go
```
Edit ~/.bashrc file

```
nano ~/.bashrc
```
Add this below at the end of file
```
export GOROOT=/usr/local/go 
export GOPATH=$HOME/go 
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH 
```

Refresh profile file to
```
source ~/.bashrc
```
Verify the installation
```
go version
```
Result
```
go version go1.19 linux/amd64
```

To get the source code, clone this repository

```
$ git clone https://github.com/celiakassa/Networkquality_v2.git
```
### Build
 
```
$ go mod download 
$ go build networkQuality.go
```

That will create an executable named `networkQuality`.

### Run

```
$ ./networkQuality --config monitor.uac.bj --port 4449 --path /config
```

Add executable named `networkQuality` to variable path

```
sudo mv networkQuality /usr/bin 
```
add scheduled tasks with crontab

```
crontab -e
```


Add at the start of file the path of executable `networkQuality` and executable of go

To found your go path :

```
$PATH
```
```
PATH:=/usr/bin:/home/celia/go/bin
```

Add this below at the end of file

```
*/10 * * * * networkQuality --config monitor.uac.bj --port 4449 --path /config
```

