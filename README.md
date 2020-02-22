# V2ray + Websocket + TLS

* 自动生成 UUID
* 默认使用 caddy 自动获取证书
* 自动生成安卓 V2rayNG vmess 链接
* 自动生成 iOS ShadowRocket Vmess 链接
* 自动生成 iOS 二维码

## 使用方法

* Install Docker
* Configure your domain resolving to your server's IP address
* Make sure ports 443 and 80 are available.

``` bash
docker image build -t v2ray_ws:0.0.1 .

docker run -d --rm --name v2ray -p 443:443 -p 80:80 -v $HOME/.caddy:/root/.caddy v2ray_ws:0.0.1 YOURDOMAIN.COM V2RAY_WS && sleep 3s && sudo docker logs v2ray

# specify uuid
docker run -d --rm --name v2ray -p 443:443 -p 80:80 -v $HOME/.caddy:/root/.caddy v2ray_ws:0.0.1 YOURDOMAIN.COM V2RAY_WS UUID && sleep 3s && sudo docker logs v2ray
```

Log:

``` bash
sudo docker logs v2ray
```

Stop:

``` bash
sudo docker stop v2ray
```
