# iOS上架指南

## 1 前提

默认开发者已经有iOS开发者账号。账号类型区别可以在[账号说明](https://developer.apple.com/support/compare-memberships/)中查看。

## 2 创建证书
### 2.1 创建请求文件
在mac的应用里找到**钥匙串(Keychain Access)**应用
![keychain Screenshot](./assert/keychain.png)
填写好证书信息，保存请求文件到电脑。(Email Address填开发者的邮件，common name是证书中密钥的名字，CA email address可以不填)
![getcer Screenshot](./assert/getcer.png)
完成后在**钥匙串(Keychain Access)**应用中可以发现多了两个common name命名的文件

private key保存在mac的Keychain Access中，用于签名（CodeSign）对外发布的App。<br>
public key一般随证书（随Provisioning Profile，随App）散布出去，对App签名进行校验认证，必须保护好本地Keychain中的private key，以防伪冒。
![keychainlogin Screenshot](./assert/keychainlogin.png)
并且在相应文件夹中多了证书请求文件
![cer Screenshot](./assert/cer.png)
### 2.2 创建证书
登陆[苹果开发者官网](https://developer.apple.com)，[申请证书](https://developer.apple.com/account/ios/certificate/create)
![applecer Screenshot](./assert/applecer.png)
证书有两种: <br>
Development(开发证书)
`开发证书用于开发和调试应用程序，可用于联机调试`<br>
Production(发布证书)
`生产证书用来发布应用程序`
