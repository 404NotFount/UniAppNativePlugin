# UniAppNativePlugin
UNIAPP项目，测试原生插件是否能跑起来

插件的配置信息在nativeplugins\xxx-Module\package.json中设置


{

    "name": "插件名称",
    "id": "DCloud-RichAlert", // 插件标识
    "version": "插件版本号",
    "description": "插件描述信息",
    "_dp_type":"nativeplugin",
    "_dp_nativeplugin":{
        "android": {
            "plugins": [
                    {
                        "type": "module",
                        "name": "DCloud-RichAlert_TestModule", //id为前缀
                        "class": "uni.dcloud.io.uniplugin_richalert.TestModule"
                    },
                    {
                        "type": "component",
                        "name": "DCloud-RichAlert_TestComponent",
                        "class": "uni.dcloud.io.uniplugin_richalert.TestComponent"
                    }
                ],
                "dependencies":[
                      "android中的依赖信息，不导入会报错notfound"
                ]
            }
        }
    }
    ...
    ...
    具体信息请到官网api文档中查看：
    https://nativesupport.dcloud.net.cn/NativePlugin/course/android?id=%e6%8f%92%e4%bb%b6%e7%bc%96%e5%86%99%e5%91%bd%e5%90%8d%e8%a7%84%e8%8c%83
