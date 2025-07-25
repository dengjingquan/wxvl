#  从LNK到Chrome零日漏洞，揭秘高级间谍组织TaxOff的狩猎进化史  
原创 Hankzheng  技术修道场   2025-06-22 06:02  
  
![](https://mmbiz.qpic.cn/sz_mmbiz_png/wWBwsDOJT4icnGM2rfv3oHuzhrs0SIanGnUVeZgmB8ibfE2pZAg9hmZrpo7NbZWIJVYXorVZ0Ps71jwW3nktZOsQ/640?wx_fmt=png&from=appmsg "")  
  
近期，Google Chrome浏览器一个已被修复的零日漏洞（CVE-2025-2783  
）在野利用事件，如同一块探路石，为我们揭示了一个技术高超、行事隐秘的高级威胁组织——**TaxOff**  
（或称Team46）的完整活动轨迹。这不仅是一次漏洞警报，更是一份关于顶级网络攻击者如何不断进化其“狩猎”技巧的详实档案。  
## 最新“军火”：Chrome零日漏洞与“沙箱越狱”  
  
在2025年3月的攻击行动中，TaxOff亮出了其武器库中迄今最致命的武器——Chrome **CVE-2025-2783**  
 零日漏洞。要理解其威力，我们必须先了解“浏览器沙箱”。  
  
**浏览器沙箱（Sandbox）**  
，本质上是为网页代码构建的一座“数字监狱”。所有代码都必须在狱中运行，无法触碰监狱外的真实电脑系统。而**“沙箱逃逸”**  
漏洞，则相当于在这座监狱的墙上打开了一个秘密通道。TaxOff正是利用此漏洞，通过伪装成“普里马科夫报告”论坛邀请函的钓鱼邮件，诱骗受害者点击链接。一旦点击，恶意代码便“越狱”成功，其高度定制的**Trinper后门**  
得以植入系统，完全控制受害者的电脑。  
## 攻击者画像：一部清晰的TTP进化史  
  
安全研究人员通过对横跨数年的攻击活动进行关联分析，成功描绘出TaxOff/Team46令人警惕的“三级跳”式进化路径：  
- **阶段一：娴熟的基础技术 (2024年初)**  
  
采用“传统”但高效的攻击链：通过钓鱼邮件分发内含恶意快捷方式（.lnk）的ZIP包，点击后通过PowerShell部署加载器。在此阶段，他们灵活运用了**开源shellcode加载器Donut**  
，以及**常被用于红队演练及真实攻击的强大工具Cobalt Strike**  
，来投放最终载荷。这表明他们对攻防工具生态有深入的了解。  
  
- **阶段二：零日能力的初次显露 (2024年中)**  
  
首次武器化零日漏洞。在针对Yandex浏览器的攻击中，他们利用了一个**DLL劫持零日漏洞（CVE-2024-6473）**  
。这是一个关键的转折点，标志着该组织已从单纯利用人的弱点，升级为具备挖掘和利用软件自身核心缺陷的能力。  
  
- **阶段三：顶级漏洞的在野利用 (2025年)**  
  
将目标锁定在全球拥有最多用户的Chrome浏览器，并成功利用其零日漏洞。这体现了该组织已跻身顶级攻击者的行列，拥有获取和工程化利用最高价值漏洞的资源和能力。  
  
## 核心载荷Trinper：精巧的“多线程”后门  
  
作为TaxOff的核心武器，C++编写的Trinper后门在设计上极为精巧。它大量采用了**多线程技术**  
，通过将不同恶意任务（如键盘记录、文件窃取、C2通信、自我隐藏）拆分到并行的线程中，使其活动看起来不像是单一、线性的恶意进程，而更像是操作系统正常的、零散的多任务处理。这种“化整为零”的策略，能有效迷惑和绕过诸多基于行为模式检测的安全产品。  
## 战略推测：谁是TaxOff？  
  
分析其持续的攻击目标——俄罗斯的政府机构、金融部门和铁路货运等关键行业，结合其使用的零日漏洞和定制化复杂工具，所有线索都指向一个结论：TaxOff/Team46极有可能是一个具备**国家背景**  
、资源充足的**高级持续性威胁（APT）**  
组织。其首要动机并非短期经济利益，而是长期的、以窃取高价值情报为目的的**网络间谍活动**  
。  
  
TaxOff/Team46的案例清晰地表明，高级网络威胁行为者是动态演进的。他们不断投资于漏洞研究和恶意软件开发，以确保能够突破最严密的安全防线。对于任何组织而言，防御这类对手，不仅需要及时的补丁更新，更需要深度的威胁情报和持续性的安全监控能力。  
  
