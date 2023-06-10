# ssh 实现内网穿透

## 命令
// 本地端口转发到远程端口
ssh -CfN -i <证书地址> username@ip（跳板机器） -L <本地端口>:<目标ip>:<目标端口>

// 例子
ssh -CfN -i ~/.ssh/id_rsa.pem user@0.0.0.0 -L 10000:192.168.1.2:22

//解释
通过~/.ssh/id_rsa.pem证书，以user用户登录到0.0.0.0 跳板机 讲本地的10000端口绑定到192.168.1.2的22端口

//使用命令登录
ssh -p 10000

### 参数解析

-C：压缩传输
f：后台运行
N：不执行远程命令
-i: 证书地址
-L：本地端口:目标ip:目标端口