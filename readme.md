# iedis 验证服务程序


- 本地配置hosts.

`127.0.0.1 www.codesmagic.com`
- 配置域名证书
cd 至src/main/resources 目录下,使用
`keytool -genkey -alias tomcat  -storetype PKCS12 -keyalg RSA -keysize 2048  -keystore keystore.p12 -validity 3650 -keypass 123123123aa -storepass 123123123aa
` 来配置证书。其中姓氏那一栏很重要，要与域名一致。否则会报`java.security.cert.CertificateException: No name matching localhost found`错误。解决方法参照 http://java.globinch.com/enterprise-java/security/fix-java-security-certificate-exception-no-matching-localhost-found/

````
您的名字与姓氏是什么?
  [Unknown]:  www.codesmagic.com
您的组织单位名称是什么?
  [Unknown]:  www.codesmagic.com
您的组织名称是什么?
  [Unknown]:  www.codesmagic.com
您所在的城市或区域名称是什么?
  [Unknown]:  a
您所在的省/市/自治区名称是什么?
  [Unknown]:  a
该单位的双字母国家/地区代码是什么?
  [Unknown]:  a
CN=www.codesmagic.com, OU=www.codesmagic.com, O=www.codesmagic.com, L=a, ST=a, C=a是否正确?
  [否]:  y
````
- 打包程序并启动。java -jar demo-0.0.1-SNAPSHOT.jar



## 知识点
- https配置
- 80转https
- springboot
