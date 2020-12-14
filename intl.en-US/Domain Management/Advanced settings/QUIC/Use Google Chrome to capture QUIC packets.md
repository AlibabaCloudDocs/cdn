# Use Google Chrome to capture QUIC packets

This topic describes how to use Google Chrome to capture Quick UDP Internet Connections \(QUIC\) packets that are sent to a domain name accelerated by Alibaba Cloud Content Delivery Network \(CDN\).

The latest version of Wireshark is used. For more information, see [Download Wireshark](https://www.wireshark.org/#download).

## Procedure

1.  Open Google Chrome, enter Chrome://flags into the address bar, and then press Enter. Find **Experimental QUIC protocol** and set it to **Enabled**.

    **Note:** By default, QUIC is disabled in Google Chrome. You must manually enable QUIC.

2.  Exit Google Chrome.

3.  Use a command-line interface \(CLI\) to open Google Chrome and open the URL of the accelerated domain name.

    **Note:** After QUIC is enabled, Google Chrome uses the latest version of QUIC to connect to the server. However, the latest version of QUIC supported by Alibaba Cloud CDN is Q46. This may cause the handshakes between Google Chrome and the server to fail. Therefore, you must use a CLI to open Google Chrome before you can open the URL of the accelerated domain name from Google Chrome.

    The following figures show the difference between using a CLI to open Google Chrome in a Mac and a Windows operating system.

    -   Mac: Enter `/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --disable-setuid-sandbox --enable-quic --quic-version=Q046 --origin-to-force-quic-on=quic-qn.xhscdn.com:443 URL` into the CLI and press Enter to open Google Chrome. You can then open the URL of the accelerated domain name. The connection is established over QUIC. Make sure that QUIC is enabled for the accelerated domain name.

        ![Mac](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2470083061/p169895.png)

    -   Windows: Enter the command into the CLI and press Enter to open Google Chrome. You can then open the URL of the accelerated domain name. The connection is established over QUIC.

        The command consists of three parts. Separate them with half-width space characters.

        1.  The path of Google Chrome on the on-premises machine.

            **Note:** To view the path, you can right-click the Google Chrome icon, select Properties, and then find the Target field. If the path contains space characters, enclose the path with quotation marks.

        2.  `--disable-setuid-sandbox --enable-quic --quic-version=Q046 --origin-to-force-quic-on=quic-qn.xhscdn.com:443`.
        3.  The URL of the accelerated domain name. Make sure that the domain name has QUIC enabled.
        If the **Protocol** column displays the QUIC protocol, it indicates that data can be transmitted over QUIC.

        **Note:** If you cannot find the Protocol column in your Chrome DevTools, right-click the table header and select Protocol to show the column.

        ![QUIC](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2470083061/p169761.png)

4.  Open Wireshark and select **WLAN 2** to start capturing packets. Set the filter condition to `udp.port == 443`.

    In a Mac operating system, the Protocol column displays GQUIC. In a Windows operating system, the Protocol column displays UDP.

    ![Capture packets](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2470083061/p169770.png)

    ![UDP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2470083061/p170311.png)


