# ssh

start a socks proxy on LOCAL_PROT

```
ssh -qTfnN -D $LOCAL_PORT $username@$host
```

# socksd

https://github.com/lparam/socksd

start a socks5 proxy server

# proxychains

command line tool.

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

# proxifier

https://www.proxifier.com/

a GUI configurable proxy client tool. 

like proxychains, but better.

Proxifier allows network applications that do not
support working through proxy servers
to operate through a SOCKS or HTTPS proxy and chains.

# kcptun

https://github.com/xtaci/kcptun

make a network tunnel encrypted, turn TCP stream into UDP datagram.
very fast(x2 ~ x5), but take more bandwidth.


BEFORE

```
	  TCP(very slow)
client ---------------------> server
```

AFTER

```
	TCP                 UDP(very fast,encrypted)                 TCP
client ----> tunnel-client -------------------------> tunnel-server ----> server
```


examples

browers-socks-proxy ---> tunnel-client ---> tunnel-server ---> ssh -D ...

