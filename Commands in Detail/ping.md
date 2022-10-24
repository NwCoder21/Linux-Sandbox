# ping 

This command is used to ping a certain hoston the local network or on the internet. 

## Syntax:
```yaml
$ ping <host> 
```

The <host> can be either a domain name or an IP address. For example: 

---
  
# `-c` option

Using the `-c` option, we can specify the amount of times we want to attempt to ping, otherwise, it will keep trying to ping it unless you press `ctrl-c`. The below example will attempt to ping ebay.com three times

```yaml
$ ping -c 3 ebay.com 
``` 
## why use ping?
  
The reason why ping is used is to check if a host is connected to the network. It is also used to check if your is connected to the network or not. 


