- [原始仓库](https://github.com/nordnet/cordova-hot-code-push)
- [修复仓库](https://github.com/amosbaby/cordova-hot-code-push)
- [原始README](README_ORIGIN.md)
- [cli](https://github.com/nordnet/cordova-hot-code-push-cli)

> 2020/09/02

> 兼容Capacitor

> install
```shell script
npm install git+http://192.168.3.168:12000/tool/cordova-hot-code-push.git
npm install @ionic-native/hot-code-push
ionic cap sync
```

> cli
```shell script
npm install -g cordova-hot-code-push-cli
cordova-hcp build
```

> config

`android/app/src/main/res/xml/config.xml` || `ios/App/App/config.xml`

> 项目根目录添加 `cordova-hcp.json`
```json
{
  "name": "dofu-app",
  "ios_identifier": "com.globletech.petid",
  "android_identifier": "com.globletech.petid",
  "update": "resume",
  "content_url": "http://petid.qqqid.com/apk"
}
```

```xml
  <chcp>
    <config-file url="http://petid.qqqid.com/apk/chcp.json"/>
    <auto-download enabled="false"/>
    <auto-install enabled="false"/>
  </chcp>
```

> ios

`Project navigator> Pods > Development Pods > Capacitor > CAPBridgeViewController.swift` 追加方法
```
  override public func setValue(_ value: Any?, forKey key: String) {
      if(key.contains("teh-hot-code-push-plugin")) {  // 如果是热更新赋值
        setServerPath(path: key);
        if (bridge != nil) {
            loadWebView();
        }
      } else {
        super.setValue(value, forKey: key);
      }
  }
```
