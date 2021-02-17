## Mac常见使用

**Homebrew**

- 安装任意包
```
$ brew install <packageName>
```
示例：安装wget
```
$ brew install wget
```
- 卸载任意包

```
$ brew uninstall <packageName>
```
示例：卸载git
```
$ brew uninstall git
```
- 查询可用包

```
$ brew search <packageName>
```
- 查看已安装包列表
```
$ brew list
```
- 查看任意包信息
```
$ brew info <packageName>
```
- 更新Homebrew
```
$ brew update
```
- 查看Homebrew版本
```
$ brew -v
```
- Homebrew帮助信息

```
$ brew -h
```
http://blog.csdn.net/u010275932/article/details/76080833

**mac 开启信任源**

```shell
sudo spctl --master-enable
sudo spctl --master-disable
```

**查看端口占用**

```shell
lsof -i:8080
```

