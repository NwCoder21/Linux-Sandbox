# Simple Compression

The im of this script is to compress all the log files within a folder.

```bash
#!/bin/bash
for file in logfiles/*.log
do
        tart -czvf $file.tar.gz $file
done
```

![image](https://user-images.githubusercontent.com/107522496/214527320-c62f31ea-b437-4efa-8b0c-6c37b95beedb.png)



