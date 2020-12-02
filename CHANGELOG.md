# Change Log

## 1.1.8 (2020-11-22)

修复拉取热更新失败
表现: 应用市场自动更新或者覆盖安装后第一次打开没有尝试拉取热更新代码
原因: 覆盖安装或者 iOS 的存储不够(之前热更新的存储目录是 NSCachesDirectory，存储不够时会被系统清理掉，覆盖安装时也会清理)时首次启动会尝试拷贝资源文件到热更新目录
之前的代码中只更新了 currentRelease 到 preference 中，没有更新 fileStructure，因此 fileStructure 仍然用的时候插件初始化时使用的 old release version。因此拷贝时错误的将新 binary 的资源文件拷贝到了 old release 对应的热更新目录。这样在 APP 启动后尝试拉取热更新时在热更新目录对应的 currentRelease 的目录中根本无法找到热更新配置文件，从而导致热更新失败。
解决办法: 检测到新 binary 更新 currentRelease 到 preference 中的同时，也要更新到 fileStructure，此时拷贝资源文件到热更新目录就正确。即使热更新目录被删除掉，启动时也会根据当前启动的 binary 重建热更新目录，从而在此正常拉取热更新

## 1.1.7 (2020-08-20)

修复 iOS 下热更新成功后刷新两次的错误

## 1.0.6 (2020-04-01)

增加下载进度

## 1.0.5 (2020-03-17)

针对苹果审核信息

> ITMS-90809: Deprecated API Usage - Apple will stop accepting submissions of apps that use UIWebView APIs.

需要将 cordova-ios 升级到 5.1.1，不能用 5.1.0 会有一个错误

inappbrowser 需要用 3.0 以上，目前还是有问题，需要搭配

> https://github.com/kleeb/cordova-plugin-inappbrowser

百度地图也会报错，需要将 cordova-plugin-baidumaplocation 升级到 4.0.3
