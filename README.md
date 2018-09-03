# Alpine

这是一个一键脚本，功能就是将当前VPS环境一键更换为Alpine系统，并自动安装Caddy + PHP组成运行环境，同时配合Supervisord进行进程守护。

默认运行程序为Typecho，所有优化均以16MB内存为基准，若为大内存请自行调整PHP配置。

*使用本脚本出现的任何问题请自行承担，俺扛不起！*

演示地址：[https://16mb.tw](https://16mb.tw)

## 使用说明

```bash
wget --no-check-certificate https://github.com/ylqjgm/Alpine/raw/branch/master/alpine.sh && chmod +x alpine.sh && ./alpine.sh
```

执行脚本后会要求输入当前VPS环境，目前仅支持`lxc`及`openvz`两种，其余未测试，不知是否可行。

设定VPS环境后选择网卡名称，脚本设定网络为DHCP自动获取，若需配置静态IP请在安装完成后自行设定。

## 测试环境

本地VMWare中安装Proxmox，并使用Proxmox开启虚拟机进行测试，所有测试虚拟机模板均为Proxmox官方提供模板，所有系统均使用x64，未对i386进行测试

测试系统：

> 1. CentOS 6
> 2. CentOS 7
> 3. Debian 7
> 4. Debian 8
> 5. Debian 9
> 6. Ubuntu 14.04
> 7. Ubuntu 16.04

## 存在问题

> 1. 系统更换为`Alpine`后，再次启动会造成VNC界面无法登陆，但SSH不受影响。
> 2. 可能会存在`Caddy`设置https后无法启动的问题（本地环境，未验证真实环境）。