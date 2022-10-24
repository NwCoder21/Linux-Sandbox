# ping - Packet Internet Groper

This command is used to ping a certain server/host on the local network or on the internet. The time it takes to get a response from the pinged device is known as latency. 


![image](https://user-images.githubusercontent.com/107522496/197481558-09e846b5-c5c3-427f-bb9c-8b4bc3ef38ba.png)



## Syntax
```yaml
$ ping <host> 
```

The <host> can be either a domain name or an IP address. For example: 

---
  
# `-c` option

Using the `-c` option, we can specify the amount of times we want to attempt to ping (the amount of packets to send), otherwise, it will keep trying to ping it unless you press `ctrl-c`. The below example will attempt to ping ebay.com three times

```yaml
$ ping -c 3 ebay.com 
``` 
## Why use ping?
  
The reason why ping is used is to check if a host is connected to the network. It is also used to check if your is connected to the network or not. 


