# X-FOR-code

把这2个文件替换系统自带

变量设置参考 https://github.com/dsadsadsss/X-docker.git

但是这XRAY内置配置了

配置如下：

```
{
	"log": {
		"access": "/dev/null",
		"error": "/dev/null",
		"loglevel": "warning"
	},
	"inbounds": [{
			"port": 8001,
			"listen": "0.0.0.0",
			"protocol": "vmess",
			"settings": {
				"clients": [{
					"id": "fd80f56e-93f3-4c85-b2a8-c77216c509a7",
					"alterId": 0
				}]
			},
			"streamSettings": {
				"network": "ws",
				"wsSettings": {
					"path": "/vms"
				}
			}
		},
		{
			"port": 8002,
			"listen": "0.0.0.0",
			"protocol": "vless",
			"settings": {
				"clients": [{
					"id": "fd80f56e-93f3-4c85-b2a8-c77216c509a7"
				}],
				"decryption": "none"
			},
			"streamSettings": {
				"network": "ws",
				"wsSettings": {
					"path": "/vls"
				}
			}
		}
	],
    "dns":{
        "servers":[
            "https+local://8.8.8.8/dns-query"
        ]
    },
    "outbounds":[
        {
            "protocol":"freedom"
        },
        {
            "tag":"WARP",
            "protocol":"wireguard",
            "settings":{
                "secretKey":"cKE7LmCF61IhqqABGhvJ44jWXp8fKymcMAEVAzbDF2k=",
                "address":[
                    "172.16.0.2/32",
                    "fd01:5ca1:ab1e:823e:e094:eb1c:ff87:1fab/128"
                ],
                "peers":[
                    {
                        "publicKey":"bmXOC+F1FxEMF9dyiK2H5/1SUtzH0JuVo51h2wPfgyo=",
                        "endpoint":"162.159.193.10:2408"
                    }
                ]
            }
        }
    ],
    "routing":{
        "domainStrategy":"AsIs",
        "rules":[
            {
                "type":"field",
                "domain":[
                    "domain:openai.com",
                    "domain:ai.com"
                ],
                "outboundTag":"WARP"
            }
        ]
    }
}
```

