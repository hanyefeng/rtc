# Android Demo {#task889 .task}

本文档为您介绍了运行Android Demo的前提条件及具体步骤。您可以加入频道和远端用户进行音视频通信。

在执行跑通Demo步骤之前，您需要搭建App Server，具体操作请参见[搭建App Server](../../../../cn.zh-CN/快速入门/搭建App Server.md#)。

您需要下载示例代码，详情请参见[SDK下载](../../../../cn.zh-CN/SDK参考/SDK下载.md#khd_sdk_1)。

1.  配置参数。 
    1.  打开AliRtcConstants.java，配置App Server地址。 

        ``` {#codeblock_jwp_q1m_m5u .language-java}
        public class AliRtcConstants {
            /**
             * App Server的url，只需填写域名
             */
            public static final String GSLB_TEST = ;
            /**
             * 请求头携带的信息，可自定义
             */
            public static final String COMMON_UA_STR = "your UA";
        }
        ```

    2.  在AliRtcAuthService.java文件中，passwd字段对应的参数值需要根据自身App server来定 ，阿里云提供的App Server示例代码中未校验此字段。 

        ``` {#codeblock_ztb_b1b_0dc .language-java}
        public interface AliRtcAuthService {
            /**
             * 获取频道信息
             * @param userName 用户名
             * @param roomNum 频道号
             * @return
             */
            @GET("app/v1/login?passwd=12345678")
            Observable<RTCAuthInfo> getRTCAuthInfo(@Query("user") String userName, @Query("room") String roomNum);
        }
        ```

2.  运行。 

    **说明：** android端Demo必须在真机上运行，最低支持Android 4.1，完成以上设置即可运行DemoDemo。

    1.  Demo运行成功进入首页，输入相应频道号，单击确定按钮，进入下一页面。 

        ![Android Demo](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/170945/156462387049548_zh-CN.png)

    2.  进入频道页面后，可以看到本地已经开启的预览视图，单击开始按钮加入频道，如果该频道中有其他用户即可开始实时音视频通话。 

        ![Android Demo](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/170945/156462387149549_zh-CN.png)

