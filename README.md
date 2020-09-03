- [原始仓库](https://github.com/nordnet/cordova-hot-code-push)
- [修复仓库](https://github.com/amosbaby/cordova-hot-code-push)
- [原始README](README_ORIGIN.md)

> 2020/09/02

> 兼容Capacitor

> install
```shell script
npm install git+http://192.168.3.168:12000/tool/cordova-hot-code-push.git
npm install @ionic-native/hot-code-push
ionic cap sync
```

`android/app/src/main/res/xml/config.xml`
```xml
  <chcp>
    <config-file url="http://petid.qqqid.com/apk/chcp.json"/>
  </chcp>
```
