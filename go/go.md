```
module github.com/exercise

require (
    golang.org/x/text v0.3.0
    gopkg.in/yaml.v2 v2.1.0 
)

replace (
    golang.org/x/text => github.com/golang/text v0.3.0
)
```

```
https://goproxy.io

GOPROXY=https://mirrors.aliyun.com/goproxy/
```

