### 云朵屋App接口文档
- #### 接口域名地址
  - 请求地址:`http://192.168.1.123`
  - 请求端口: `8888`
- #### 接口协议
  http请求，统一使用PSOT请求方式访问，请求参数使用DES加密，响应实体亦使用DES加密返回，由客户端解密使用
- #### 请求响应码说明
  - 10 请求成功
  - 0  请求失败
  - -10 无效请求

### 具体接口
#### 1. 获取漫画Banner列表
- ##### url
  api/banner/{type}
  ```
	api/banner/1, api/banner/2
  ```
- ##### 请求方式
  POST
- ##### 请求参数 `(路径参数)`
| 参数 | 类型 | 说明 |
| ---- | ---- | ---- |
| type | int  | URL参数 1：漫画、2：小说、 缺省：无数据    |
- ##### 响应参数
| 参数     | 类型   | 说明                       |
|:-------- |:------ |:-------------------------- |
| id       | long   | 漫画ID                     |
| mTxtAh   | String | 文作者                     |
| mImgAh   | String | 图作者                     |
| mAuthor  | String | 作者笔名                   |
| mName    | String | 漫画名称                   |
| mHear    | long   | 热度                       |
| mThumb   | String | 缩略图绝对路径             |
| mThumbB  | String | 缩略图相对路径             |
| mFlat    | String | 漫画横版图绝对路径         |
| mFlatB   | String | 漫画横版图相对路径         |
| mJieshao | String | 漫画简介                   |
| mNotice  | String | 漫画公告                   |
| mUptime  | String | 漫画更新时间说明           |
| mCoNum   | long   | 漫画收藏量                 |
| mStatus  | String | 漫画上架状态               |
| resType  | String | 资源类型  1：漫画、2：小说 |

  ``` json
  {
	  "data":[{
		  "id": 1,
		  "mAuthor": "开源动漫",
		  "mCoNum": 121,
		  "mFlat": "http://cdn.dolulu.com.cn/uploads/manhua/1/flat/5a376e40814f7.jpg",
		  "mFlatB": "uploads/manhua/1/flat/5a376e40814f7.jpg",
		  "mHeat": 880,
		  "mImgAh": "eng",
		  "mJieshao": "他紧扣住她的手，将她压在身下。 她被长辈算计，送上了前未婚夫表哥的床。 他是A市的顶级首富，身价千亿，冷漠禁欲，第一次被“坏”女人算计，更可恶得是算计了他，她竟然还敢带球跑。 “女人，吃了敢不负责？”五年后再见，她的双手被他的领带绑起，捆在了钢管上。 她心生恐惧。 ...",
		  "mName": "总裁的蜜宠娇妻",
		  "mNotice": "求收藏，求月票，粉丝群号565132192，商务合作QQ：2394211953",
		  "mStatus": "已上架",
		  "mThumb": "http://cdn.dolulu.com.cn/uploads/manhua/1/thumb/5a376e4081142.jpg",
		  "mThumbB": "uploads/manhua/1/thumb/5a376e4081142.jpg",
		  "mTxtAh": "澄澄",
		  "mUptime": "每周五",
		  "resType": "1"
		  }],
	  "status": 10
  }
  ```

#### 2. App首页数据
- ##### url
  api/index
- ##### 请求方式
  POST
- ##### 请求参数
  无
- ##### 响应参数
  | 参数      | 类型   | 说明               |
  |:--------- |:------ |:------------------ |

``` json
  {
  	"status": 10,

  }
```