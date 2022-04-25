## Docker Installations
### Install yarn
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```
```
sudo apt update
sudo apt install yarn
```

### Install & Update Node JS
Follow [this](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)
```
cd ~
curl -sL https://deb.nodesource.com/setup_16.x -o /tmp/nodesource_setup.sh
sudo bash /tmp/nodesource_setup.sh
sudo apt install nodejs
```
Check node version
```
node -v
```

### Install FiftyOne
```bash
git clone https://github.com/voxel51/fiftyone
cd fiftyone
```

```bash
make python
```

build docker
```bash
docker build -t voxel51/fiftyone .
```

### Running Docker
```
docker run -v ${SHARED_DIR}:/fiftyone -p 5151:5151 -it voxel51/fiftyone
```

#   docker run \
#       -v ${SHARED_DIR}:/fiftyone \
#       -p 5151:5151 \
#       -it voxel51/fiftyone

```bash
docker run \
    -v ${SHARED_DIR}:/fiftyone \
    -p 5252:5252 \
    -it voxel51/fiftyone
```

docker run \
    -p 5252:5252 \
    -it voxel51/fiftyone

ssh -L 8080:localhost:<PORT> <REMOTE_USER>@<REMOTE_HOST>

ssh -L 8080:localhost:5252 azureuser@13.76.103.59