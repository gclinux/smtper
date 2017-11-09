## intuition

This is a very simple class of PHP mail sending
Supports UTF-8 , supports sending attachments.

一个支持附件的php邮件发送类

#### require

it need these ext in php:

需要开启以下PHP扩展:

> sockets,fileinfo , openssl

#### install:

support composer:

本类支持composer直接安装

```shell
composer require gclinux/smtper
```



#### how to use:



```php
$mail = new gclinux\Smtper();

 $mail->setDebug(true); //do you want to output the debug information.是否输出调试信息

 $mail->setServer("smtp.XXX.COM", "your_acount@XXXXX", "passwd"); //Setting the SMTP server without SSL. 无SSL的SMTP服务器设置

$mail->setServer("XXXXX", "joffe@XXXXX", "XXXXX", 465, true); //Seeting the SMTP server with SSL .SSL的SMTP服务器设置

 $mail->setFrom("XXXXX"); //Email Sender name 发送者

 $mail->setReceiver("XXXXX@local"); //Email reciver 接收者
 $mail->setReceiver("XXXXX2@local"); //Email reciver,multiple calls will add recivers.多次调用会累计添加接受者
 
 $mail->setCc("XXXX"); //Set CC .抄送
$mail->setBcc("XXXXX"); //Set CC,multiple calls will append.多次调用会添加.

 $mail->addAttachment("XXXX.png"); //Attachment 附件

 $mail->addAttachment("XXXX.csv"); // 添加附件，多个附件，调用多次 

 $mail->setMail("title ", "<b>body</b>"); //the titile and body 标题和内容

$mail->send();

```



it can work well without composer,but  you need to inlcude "src/Smtp.php"

它也可以不需要composer,但你要手动include src/Smtp.php这个文件:



```
include "src/Smtp.php"
```

