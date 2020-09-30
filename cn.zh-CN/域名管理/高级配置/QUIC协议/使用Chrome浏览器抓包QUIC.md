# 使用Chrome浏览器抓包QUIC

本文为您介绍在Chrome浏览器中抓包QUIC的操作步骤。

需要下载最新版的wireshark，请参见[wireshark官网](https://www.wireshark.org/#download)。

1.  打开Chrome浏览器，在地址栏中输入Chrome://flags，按下回车键，找到**Experimental QUIC protocol**功能，选择**Enabled**开启QUIC。

    **说明：** Chrome浏览器默认未开启QUIC，需要手动开启。

    ![开启QUIC](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1816190061/p169402.png)

2.  彻底关闭Chrome浏览器。

3.  使用命令行打开Chrome浏览器并访问URL。

    **说明：** QUIC开启后，Chrome浏览器会默认使用最高版本的QUIC和服务器端握手，但是阿里云CDN目前最高只支持Q46版本，所以会握手失败。因此不能直接在Chrome浏览器中输入URL访问，需要通过命令行打开Chrome浏览器并访问。

    Mac和Windows操作系统，使用命令行打开Chrome浏览器的方式不同，如下所示：

    -   Mac：打开终端，使用命令行`/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --disable-setuid-sandbox --enable-quic --quic-version=Q046 --origin-to-force-quic-on=quic-qn.xhscdn.com:443 URL`（CDN域名需开通QUIC服务），按下回车键执行，会自动弹出Chrome页面并访问URL地址，此时就是以QUIC协议传输了。

        ![Mac](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8217390061/p169895.png)

    -   Windows：打开CMD命令行工具，使用命令行回车执行，会自动弹出Chrome页面并访问URL地址，此时就是以QUIC协议传输了。

        命令行分三个部分组成，每个组成部分之间需要以半角空格分隔，如下所示：

        1.  本地Chrome浏览器路径。

            **说明：** 本地Chrome浏览器路径，可以鼠标右键Chrome图标选择属性，在目标项中获取。需要注意，路径中若是存在空格，需要将整个路径加上英文双引号（""）。

        2.  `--disable-setuid-sandbox --enable-quic --quic-version=Q046 --origin-to-force-quic-on=quic-qn.xhscdn.com:443`。
        3.  URL（CDN域名需开通QUIC服务）。
        ![Windows](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8217390061/p169792.png)

        在**Protocol**项目中出现带有QUIC的内容，QUIC协议传输成功。

        **说明：** 如果您的开发者工具中没有Protocol，可以在标签里鼠标右击选择Protocol。

        ![QUIC](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1816190061/p169761.png)

4.  使用wireshark，选择**WLAN 2**同步开始抓包。筛选的条件为`udp.port == 443`。

    Mac操作系统可以看到Protocol显示的是GQUIC，Windows操作系统可以看到Protocol显示的是UDP。

    ![抓包](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1816190061/p169770.png)![UDP](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1390201061/p170311.png)


