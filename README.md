# ipk-tools
scripts for modify openwrt IPK files

提供一些脚本，用来解包/打包 OpenWRT 的 IPK 文件。

如果在 macOS 里使用，需要安装 gtar 和 gsed。

## 解包
假设有个 `work/ABC.ipk`，执行
```shell
./script/unpack work/ABC.ipk
```
将会产生 `work/ABC` 文件夹。其中：

* `work/ABC/CONTROL` 里包含的是元数据，其中`control`文件可以修改版本号什么的
* `work/ABC` 里的其他文件（夹）就是 IPK 安装时将释放到根目录的文件（夹）


## 打包
假设之前解包后的文件夹是 `work/ABC`，执行
```shell
./script/pack work/ABC
```
将在 `work` 文件夹下产生 ipk 文件，文件名由 `包名_版本号_CPU架构.ipk` 构成
