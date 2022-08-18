# Networkquality_v2

```
sudo apt-get update  
sudo apt-get -y upgrade  
```

wget https://dl.google.com/go/go1.16.4.linux-amd64.tar.gz

sudo tar -xvf go1.16.4.linux-amd64.tar.gz
sudo rm -r /usr/local/go
sudo mv go /usr/local 


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
go version go1.16.4 linux/amd64
```

To get the source code, clone
### Build

From `${RSPVNSS_SOURCE_DIR}` grab all the required modules:
```
$ go mod download
```

And then build:
```
$ go build networkQuality.go
```

That will create an executable in `${RSPVNSS_SOURCE_DIR}` named `networkQuality`.

### Run

From `${RSPVNSS_SOURCE_DIR}`, running the client is straightforward. Simply 

```
$ ./networkQuality
```

