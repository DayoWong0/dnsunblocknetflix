# linux修改dns一键脚本

脚本非本人原创

Author : MXiDev

Website : https://mxidev.com)

#使用方法
复制命令 修改命令末尾的dns地址 执行即可 可能需要root权限

脚本1:chattr -i /etc/resolv.conf && wget -N --no-check-certificate https://raw.githubusercontent.com/chengziqaq/dnsunblocknetflix/master/dns-change.sh && chmod +x dns-change.sh && ./dns-change.sh 自定义的dns

脚本2:chattr -i /etc/resolv.conf && wget -N --no-check-certificate https://shop.bgp.sh/modules/addons/stream_unblock/library/shell/dns-change.sh && chmod +x dns-change.sh && ./dns-change.sh 自定义的dns


例如:修改dns为114.114.114.114

执行:
chattr -i /etc/resolv.conf && wget -N --no-check-certificate https://raw.githubusercontent.com/chengziqaq/dnsunblocknetflix/master/dns-change.sh && chmod +x dns-change.sh && ./dns-change.sh 114.114.114.114
