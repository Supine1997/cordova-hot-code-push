# Change Log

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
