## [💐python版本，结合自然语言处理、深度学习识别，识别率更加准确](https://github.com/wzc570738205/smartParsePro-py)

<p align="center">
  <a href="https://www.npmjs.com/package/address-smart-parse"><img src="https://img.shields.io/npm/v/address-smart-parse.svg?sanitize=true" alt="Version"></a>
  <a href="https://github.com/wzc570738205/smartParsePro"><img src="https://img.shields.io/github/stars/wzc570738205/smartParsePro?style=social" alt="stars"></a>
  	  <a href="https://github.com/wzc570738205/smartParsePro"><img alt="GitHub forks" src="https://img.shields.io/github/forks/wzc570738205/smartParsePro?label=Fork&style=social"></a>
</p>

# 智能识别收货地址（支持省市区县街道/姓名/电话/邮编识别）

## 支持以下数据格式
>注意：地址、姓名、电话、邮编用空格或者特殊字符分开

### js支持地址格式
```
1. 广东省珠海市香洲区盘山路28号幸福茶庄,陈景勇，13593464918
2. 马云，陕西省西安市雁塔区丈八沟街道高新四路高新大都荟  13593464918
3. 陕西省西安市雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918
4. 西安市雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918
5. 雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918

6. 收货人: 李节霁
手机号码: 15180231234
所在地区: 浙江省金华市婺城区西关街道
详细地址: 金磐路上坞街

7. 收货人: 马云
手机号码: 150-3569-6956
详细地址: 河北省石家庄市新华区中华北大街68号鹿城商务中心6号楼1413室
```
## 使用方法

```sh
npm install address-smart-parse
```
> version: < 3.0
```js
/**
 * smart 解析地址
 * @param event-识别的地址
 * @returns <obj>
 */
import smart from 'address-smart-parse'

smart("陕西省西安市雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918 211381198512096810")
```

> version: >=3.0
smart(str) 新增参数 address

```js
/**
 * smart 解析地址
 * @param event-识别的地址
 * @param address-地址列表 数据格式请参考 https://github.com/modood/Administrative-divisions-of-China/blob/master/dist/streets.json
 * address 可不传，不传则默认识别到省/市/区县 三级信息
 * @returns <obj>
 */
// 使用包自带的地址数据
import  {smart, address} from 'address-smart-parse'
smart("陕西省西安市雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918 211381198512096810", address)

// 使用自己的数据
import  {smart} from 'address-smart-parse'
const myAddress = [...]// 数据格式请参考 https://github.com/modood/Administrative-divisions-of-China/blob/master/dist/streets.json
smart("陕西省西安市雁塔区丈八沟街道高新四路高新大都荟710061 刘国良 13593464918 211381198512096810", myAddress)
```


## 生成数据格式
```json
{
 "zipCode":"710061",

 "province":"陕西省",

 "provinceCode":"61",

 "city":"西安市",

 "cityCode":"6101",

 "county":"雁塔区",

 "countyCode":"610113",

 "street":"丈八沟街道",

 "streetCode":"610113007",

 "address":"高新四路高新大都荟",

 "name":"刘国良",

 "phone":"13593464918",

 "idCard":"211381198512096810"
}
```


##### 地址数据来源：[中华人民共和国行政区划](https://github.com/modood/Administrative-divisions-of-China)
##### 邮编数据来源：[中华人民共和国邮编](https://github.com/xieranmaya/china-city-area-zip-data/blob/master/china-city-area-zip.json)
#### LICENSE：[Apache License](https://github.com/wzc570738205/smartParsePro/blob/master/LICENSE)
#### IDE:致谢[JetBrains](https://www.jetbrains.com/?from=smartParsePro)为本项目提供免费license支持
[![JetBrains](http://cdn.wangzc.wang/LOGO-1.png)](https://www.jetbrains.com/?from=smartParsePro)


#### qq交流群

![WX20210922-091703.png](https://cdn.wangzc.wang/uPic/WX20210922-09170315%20.png)

#### Star History

[![Star History Chart](https://api.star-history.com/svg?repos=wzc570738205/smartParsePro&type=Date)](https://star-history.com/#wzc570738205/smartParsePro&Date)


