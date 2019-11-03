# newifi3-pandora-ipk

#安装kpr后把自定义规则订阅的地址改为 https://dev.tencent.com/u/shaoxia1991/p/koolproxyR_rule_list/git/raw/master/kpr_our_rule.txt
#不修改有时会更新失败


pandora镜像源http://pandorabox.tuuz.cc:8000/pandorabox/

# newifi3用的koolproxyR别到论坛分享！一定要记住！！

## 准备工作：
先运行：</br>
`opkg install openssl-util  ipset dnsmasq-full diffutils iptables-mod-nat-extra wget ca-bundle ca-certificates libustream-openssl`</br>
手动安装以上依赖包</br>
* 如果没有 **openssl** ，就不能正常生成证书，导致https过滤失败！
* 如果没有 **ipset, dnsmasq-full, diffutils**，黑名单模式也会出现问题！（ipset 需要版本6）,如果你的固件的busybox带有支持diff支持，那么diffutils包可以不安装
* 如果没有 **iptables-mod-nat-extra** ，会导致mac过滤失效！
* 如果没有 **wget, ca-bundle, ca-certificates, libustream-openssl** ，会导致规则文件更新失败，host规则条数变为0,如果你的固件的busybox带有支持https的wget，那么这几个包可以不安装



## 使用方法
```Brach
    #源码根目录，进入package文件夹
    cd package
    #下载源码
    git clone https://github.com/Ameykyl/luci-app-koolproxyR
    #回到源码根目录
    cd ..
    make menuconfig
    #编译
    make package/luci-app-koolproxyR/{clean,compile} V=s



* TG群：https://t.me/koolproxyR
