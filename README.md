## Usage

xbuild是一款自动化多渠道打包工具.


## Installation

```powershell
curl -sS -O https://raw.githubusercontent.com/zhuayi/xbuild/master/xbuild xbuild

chmod +x xbuild

xbuild  channel.json  BuildNumber
```



## Example

### channel.json
```json
{
    "workspace": "xcworkspace路径",
    "xcodeproj": "xcodeproj路径,
    "scheme": "scheme名称",
    "AppMacro": "AppMacro宏文件,用来存放 apiserver 变量, AppMacro必须包含(IS_FORMAL:0->企业版, 1 AppStore 版, kAPI_USER_SERVER: 服务器地址, kchannelId渠道标示符)",
    "infoPath" : "Info.plist路径",
    "certificate": {

         // 企业版
        "enterprise" : {
                "codesign": "8311fea8-9ffa-42df-b6da-c484ad8a14ea(签名描述文件)",
                "buildID" : "Bundle Identifier",
                "profile" : "证书名称"
            },
        // AppStore 版
        "AppStore" : {
            "codesign": "8311fea8-9ffa-42df-b6da-c484ad8a14ea(签名描述文件)",
                "buildID" : "Bundle Identifier",
                "profile" : "证书名称"
        }
    },

    // 渠道
    "channel": [
        
        // 蒲公英渠道
        {
            "channnelName" : "渠道名",
            "apiServer" : "https:\\/\\/chengdan.xiaoying.com(接口服务器地址)",
            "channelType" : "enterprise(企业版 or AppStore 版本)"
        }
    ]
}
```

## Author

zhuayi, 2179942@qq.com

## License

xbuild is available under the MIT license. See the LICENSE file for more info.
