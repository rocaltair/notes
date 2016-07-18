# ssh

start a socks proxy on LOCAL_PROT

```
ssh -qTfnN -D $LOCAL_PORT $username@$host
```

# socksd

https://github.com/lparam/socksd

start a socks5 proxy server


# proxychains

https://github.com/haad/proxychains

you need to configure /etc/proxychains.conf, 
add socks4 or socks5 or other protocol

```
proxychains <prog> [prog-args ...]
```

for examples:

```
proxychains wget -c http://example.com/test.zip
```

# kcptun

https://github.com/xtaci/kcptun

make a tunnel encrypted, turn TCP stream into UDP datagram
very fast(x2 ~ x5), but take more network flows.


before

```
	  TCP(very slow)
client ---------------------> server
```

after

```
	TCP                 UDP(very fast,encrypted)                 TCP
client ----> tunnel-client -------------------------> tunnel-server ----> server
```


examples

browers-socks-proxy ---> tunnel-client ---> tunnel-server ---> ssh -D ...

