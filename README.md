# EasyV2ray

## Usage

* Install Docker
* Configure your domain resolving to your server's IP address
* Make sure ports 443 and 80 are available.

``` bash
git clone https://github.com/psjay/v2rayDocker.git
cd v2rayDocker

# build image first
docker image build -t v2ray_ws:0.0.1 .

# run container
docker run -d --rm --name v2ray -p 443:443 -p 80:80 -v $HOME/.caddy:/root/.caddy v2ray_ws:0.0.1 YOURDOMAIN.COM V2RAY_WS && sleep 3s && sudo docker logs v2ray

# specify uuid
docker run -d --rm --name v2ray -p 443:443 -p 80:80 -v $HOME/.caddy:/root/.caddy v2ray_ws:0.0.1 YOURDOMAIN.COM V2RAY_WS UUID && sleep 3s && sudo docker logs v2ray
```

Stop:

``` bash
sudo docker stop v2ray
```
