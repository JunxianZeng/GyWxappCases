GyWxappCases 微信小程序案例
==========================

## 微信小程序

 * 微信小程序开发文档   https://mp.weixin.qq.com/debug/wxadoc/dev/index.html
 * 微信小程序设计指南   https://mp.weixin.qq.com/debug/wxadoc/design/index.html
 * 微信小程序开发者工具 https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html


## 开源协议

本项目依据MIT开源协议发布，允许任何组织和个人免费使用。
=========================================================================================================

编码文件在enhance中
=========================================================================================================
node-uuid可以快速地生成符合 RFC4122 规范 version 1 或者 version 4 的 UUID。js-base64可以实现Base64编码和解码，支持UTF-8编码。crypto-js 可以非常方便地在 JavaScript 进行 MD5、SHA1、SHA2、SHA3、RIPEMD-160 哈希散列，进行 AES、DES、Rabbit、RC4、Triple DES 加解密。SJCL是一个由斯坦福大学计算机安全实验室创立的项目，旨在创建一个安全、快速、短小精悍、易使用、跨浏览器的JavaScript加密库。

node-uuid
node-uuid可以快速地生成符合 RFC4122 规范 version 1 或者 version 4 的 UUID（Universally Unique IDentifier, 标识符）。

UUID的出现，是为了在一个复杂的系统中，唯一的标识每个信息实体，同时不需要有一个集中的id管理。也就是说，根据某种规则来为一个信息实体分配一个唯一的id，而且不需要一个id管理器来保证这个id的唯一性。

UUID是128位的全局唯一标识符，通常由32字节的字符串表示。它通过MAC地址、时间戳、命名空间、随机数、伪随机数来保证生成ID的唯一性。version 1 是基于时间戳生成（time-based）；version 1 是随机生成（random（

version 1：

    var uuidv1 = require('../../lib/uuid/we-uuidv1');    console.log(uuidv1()); // 输出：70d47fd0-d250-11e6-9816-45a4888ae4f：
version 4：

    var uuidv4 = require('../../lib/uuid/we-uuidv4');    console.log(uuidv4()); // 输出：d839476c-ce27-4d24-a431-e96123c1916b
可以设定产生参数

    var v1 = uuidv1({
        node: [0x01, 0x23, 0x45, 0x67, 0x89, 0xab],
        clockseq: 0x1234,
        msecs: new Date().getTime(),
        nsecs: 5678
    });    console.log(v1); // 输出：908e3a9e-d250-11e6-9234-0123456789ab
js-base64
js-base64可以实现Base64编码和解码，支持UTF-8编码。

Base64是一种基于64个可打印字符来表示二进制数据的表示方法。由于2的6次方等于64，所以每6个比特为一个单元，对应某个可打印字符。三个字节有24个比特，对应于4个Base64单元，即3个字节需要用4个可打印字符来表示。它可用来作为电子邮件的传输编码。在Base64中的可打印字符包括字母A-Z、a-z、数字0-9 ，这样共有62个字符，此外两个可打印符号在不同的系统中而不同

Base64其实是一种简单的置换加密方式，但是BASE64的用处往往并不是为了防止信息泄露，而且为了方便传输，进过BASE64编码后的信息会比原始信息长，大概是4/3倍。

编码：

    console.log(Base64.encode('Wechat')); // 输出：V2VjaGF0
    console.log(Base64.encode('微信')); // 输出：5b6u5L+h
解码：

    console.log(Base64.decode('V2VjaGF0')); // 输出：Wechat
    console.log(Base64.decode('5b6u5L+h')); // 输出：微信
crypto-js
crypto-js 可以非常方便地在 JavaScript 进行 MD5、SHA1、SHA2、SHA3、RIPEMD-160 哈希散列，进行 AES、DES、Rabbit、RC4、Triple DES 加解密。

CryptoJS (crypto.js) 为 JavaScript 提供了各种各样的加密算法，目前已支持的算法包括：

MD5
SHA-1
SHA-256
AES
Rabbit
MARC4
HMAC
HMAC-MD5
HMAC-SHA1
HMAC-SHA256
PBKDF2
MD5：

    console.log(CryptoJS.MD5('Wechat').toString()); // 输出：98ffdc1f1a326c9f73bbe0b78e1d180e
SHA1：

    console.log(CryptoJS.SHA1('Wechat').toString()); // 输出：42989457d716a8b89f99c687a41779d4102b5491
SHA256：

    console.log(CryptoJS.SHA256('Wechat').toString()); // 输出： 885e2deda21a6c752f05e9c3ac95c90de31bce4b25ce38c330feee389906c83f
SJCL
SJCL（斯坦福大学Javascript加密库简称），是一个由斯坦福大学计算机安全实验室创立的项目，旨在创建一个安全、快速、短小精悍、易使用、跨浏览器的JavaScript加密库。

SJCL使用了行业标准的AES 128, 192, 256位加密；SHA256 哈希函数；HMAC验证码；PBKDF2密码加强器；CCM和OCB认证加密模式。

加密：

    var enStr = sjcl.encrypt("password", "Wechat");    console.log(enStr);
解密：

    var deStr = sjcl.decrypt("password", enStr);    console.log(deStr);
参考资料
node-uuid@github
js-base64@github
crypto-js@github
SJCL
SJCL@github
JavaScript Crypto-JS 使用手册
SJCL：斯坦福大学JS加密库
