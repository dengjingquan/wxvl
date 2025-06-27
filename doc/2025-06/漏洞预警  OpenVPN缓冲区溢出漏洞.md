#  漏洞预警 | OpenVPN缓冲区溢出漏洞  
浅安  浅安安全   2025-06-27 00:00  
  
**0x00 漏洞编号**  
- # CVE-2025-50054  
  
**0x01 危险等级**  
- 高危  
  
**0x02 漏洞概述**  
  
OpenVPN是一款开源的虚拟私人网络软件，利用SSL/TLS协议实现加密通信，支持点对点和站点到站点的安全连接，广泛应用于远程访问和企业网络。  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/7stTqD182SUq88uQTsWXticMSxiakqdwBia2Z1ao2f5jfrXmMiagU0icibjWe65HXyunQiaVx4bMv5tt6LCicAxqpA1tBQ/640?wx_fmt=png&from=appmsg "")  
  
**0x03 漏洞详情**  
###   
  
**CVE-2025-50054**  
  
**漏洞类型：**  
缓冲区溢出  
  
**影响：**  
程序崩溃  
  
****  
  
**简述：**  
OpenVPN的Windows数据通道卸载驱动程序存在缓冲区溢出漏洞，当用户空间进程向内核驱动程序发送超过1500字节的控制消息时，会导致Windows DCO驱动程序崩溃。  
  
**0x04 影响版本**  
- ovpn-dco-win <= 1.3.0  
  
- 2.6.0-I005 <= OpenVPN GUI for Windows <= 2.6.14-I001  
  
- OpenVPN GUI for Windows = 2.7_alpha1-I001  
  
**0x05****POC状态**  
- 未公开  
  
**0x06****修复建议**  
  
**目前官方已发布漏洞修复版本，建议用户升级到安全版本****：**  
  
https://openvpn.net/  
  
  
  
