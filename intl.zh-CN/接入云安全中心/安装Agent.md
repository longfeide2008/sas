# 安装Agent {#concept_dl4_ykc_zdb .concept}

云安全中心Agent是云安全中心提供的本地插件，您必须在服务器操作系统上安装云安全中心Agent才能使用云安全中心提供的安全防护服务。

云安全中心支持对离线Agent进行一键自动安装。一键安装功能无需您单独下载插件或执行任何命令安装Agent。

## 查看服务器保护状态 {#section_izq_114_k2b .section}

您可以查看服务器的保护状态来确认云安全中心Agent是否已安装及其在线/离线状态，通过控制台资产列表页面查看您所有服务器的Agent 在线状态，或在 **设置** \> **安装/卸载** 页面查看Agent插件已离线的所有资产情况。

-   **保护中**表示Agent已安装且处于**在线**状态。
-   **未受保护**表示Agent未安装或处于**离线**状态。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13631/15543582616339_zh-CN.jpg)

若您的服务器保护状态显示为**未受保护**，请参照本文档描述的内容安装Agent。

如果出现离线情况，请参考[Agent 离线排查](intl.zh-CN/接入云安全中心/Agent离线排查.md#)。

## 前提条件 {#section_n14_rlh_ghb .section}

安装Agent前请确认您服务器的环境：

-   阿里云服务器可直接安装Agent。
-   通过专线连接、内网通信的非阿里云服务器，需要修改服务器的DNS配置，指定以下任意一个云安全中心服务端DNS解析地址：

    `106.11.248.209/106.11.248.51 jsrv.aegis.aliyun.com`

    `106.11.248.90/106.11.250.224 update.aegis.aliyun.com`


**说明：** 如果您已在服务器上安装了安全软件（如安全狗、云锁等），可能会导致Agent插件无法正常安装。建议您在安装Agent插件前确认您的服务器上是否存在这类安全软件，如果存在建议您先关闭、或卸载该安全软件之后再安装Agent插件。

## 一键安装Agent { .section}

云安全中心支持对阿里云服务器一键安装Agent，非阿里云服务器需执行手动安装。

1.  登录[云安全中心管理控制台](https://yundunnext.console.aliyun.com/?p=sas)。
2.  单击 **设置** \> **安装/卸载** 。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13631/155435826142148_zh-CN.png)

3.  单击**操作**栏的**安装客户端**，勾选单个服务器安装Agent或多台服务器名称后，单击左下角**一键安装**对多台服务器执行批量安装Agent。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13631/155435826142154_zh-CN.png)


Agent 插件安装完成约五分钟后，您即可在云安全中心管理控制台中查看您服务器的在线情况：阿里云服务器将会从**未受保护**变成**保护中**。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13631/155435826142161_zh-CN.png)

一键安装后如果客户端状态显示为**安装失败**并提示**未安装云助手**，请先安装[云助手](../../../../../intl.zh-CN/部署与运维/云助手/云助手概述.md#)后再重试。

## 手动安装Agent {#section_qxq_hkv_ghb .section}

以下情况不支持一键自动安装、必须执行手动安装Agent：

-   您的服务器为非阿里云服务器
-   网络类型为经典网络
-   ECS不在[支持的区域](#table_ec1_2lh_ghb)内
-   服务器操作系统为Windows 2008、Redhat、FreeBSD、Coreos
-   未安装[云助手](../../../../../intl.zh-CN/部署与运维/云助手/云助手概述.md#)
-   服务器未开启

1.  登录[云安全中心控制台](https://yundun.console.aliyun.com/?p=sas)。
2.  单击 **设置** \> **安装/卸载** 。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/13631/155435826142148_zh-CN.png)

3.  根据您的服务器操作系统选择安装步骤，获取最新版本Agent插件。

    ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/28457/cn_zh/1502437441967/image2.png)

    -   **Windows 系统** 
        1.  在安装Agent页面，单击**点击下载**下载最新版本Agent安装文件到本地计算机。
        2.  将安装文件上传至您的Windows服务器，例如通过FTP工具将安装文件上传到服务器。
        3.  在您的Windows服务器上以管理员权限运行Agent插件安装程序。
        4.  非阿里云服务器输入安装验证Key。

            您可在Agent安装页面找到您的安装验证Key。

            ![](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/28457/cn_zh/1502437769287/image3.png)

            **说明：** 

            -   安装验证Key将用于关联您的阿里云账号，在云安全中心管理控制台登录您的阿里云账号即可保护您的服务器安全。
            -   每个安装验证KEY有效期为1小时，超过该时间将无法正确安装Agent插件。安装插件前请及时刷新安装验证KEY。
        5.  完成安装后，单击**立即查看**打开资产列表，查看资产在线状态。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/81987/155435826138980_zh-CN.png)

    -   **Linux 系统** 

        1.  根据您的实际情况，在安装Agent页面选择 **阿里云服务器** 或 **非阿里云服务器**。
        2.  以管理员身份登录您的Linux服务器。
        3.  根据您的服务器，选择32位或64位的安装命令并复制至您的Linux服务器上。
        4.  执行安装命令即可完成Agent插件的下载及安装。
        **说明：** 该安装命令包含从阿里云站点下载最新的Agent插件，如您使用的是非阿里云服务器请确认您的服务器已连接公网。


Agent插件安装完成约五分钟后，您即可在云安全中心管理控制台中查看您服务器的在线情况：

-   阿里云服务器会从**未受保护**变成**保护中**。
-   非阿里云服务器将会被添加至您的服务器列表中。

## 验证Agent安装 {#section_csp_z1d_zdb .section}

成功安装Agent后，建议您参照以下步骤进行验证：

1.  检查您的服务器上云安全中心Agent的AliYunDun和AliYunDunUpdate进程是否正常运行。关于云安全中心Agent进程说明，请参考[Agent说明](intl.zh-CN/接入云安全中心/Agent说明.md#)。
2.  在您的服务器上执行以下telnet命令，检查您的服务器是否能正常连通云安全中心服务器：

    **说明：** 确保您的服务器能够连通至少一个jsrv和一个update服务域名。

    -   `telnet jsrv.aegis.aliyun.com 80`
    -   `telnet jsrv2.aegis.aliyun.com 80`
    -   `telnet jsrv3.aegis.aliyun.com 80`
    -   `telnet update.aegis.aliyun.com 80`
    -   `telnet update2.aegis.aliyun.com 80`
    -   `telnet update3.aegis.aliyun.com 80`

如果云安全中心Agent安装验证失败，请参考[Agent离线排查](intl.zh-CN/接入云安全中心/Agent离线排查.md#)。

## 注意事项 {#section_fsp_z1d_zdb .section}

非阿里云服务器必须通过安装程序（Windows）或脚本命令（Linux）安装云安全中心Agent。

如果您的非阿里云服务器通过以下方式安装了Agent，则您需要删除云安全中心Agent目录后，按照上述手动安装步骤重新安装Agent。

-   通过已安装云安全中心Agent的镜像批量安装服务器。
-   从已安装云安全中心Agent的服务器上直接复制云安全中心Agent文件。

**云安全中心Agent文件目录**

-   Windows：C:\\Program Files \(x86\)\\Alibaba\\Aegis
-   Linux：/usr/local/aegis

## 一键安装功能支持的地域 {#section_frg_dlh_ghb .section}

|支持的地域|地域名称|
|-----|----|
|亚太|华东 1（杭州）|
|华东 2（上海）|
|华东 2 金融云|
|华北 1（青岛）|
|华北 2（北京）|
|华北 3（张家口）|
|华北 5（呼和浩特）|
|华南 1（深圳）|
|香港|
|新加坡|
|澳大利亚（悉尼）|
|马来西亚（吉隆坡）|
|印度尼西亚（雅加达）|
|日本（东京）|
|欧洲与美洲|德国（法兰克福）|
|英国（伦敦）|
|美国（硅谷）|
|美国（弗吉尼亚）|
|中东与印度|印度（孟买）|
|阿联酋（迪拜）|

