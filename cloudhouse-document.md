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
	例子： api/banner/1, api/banner/2
  ```
- ##### 请求方式
  POST
- ##### 请求参数 `(路径参数)`
| 参数 | 类型 | 说明 |
| ---- | ---- | ---- |
| type | int  | URL参数 1：漫画、2：小说、 缺省：无数据    |
- ##### 响应参数
| 漫画参数  | 类型   | 说明                       |
|:-------- |:------ |:--------------------------|
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

| 小说参数  | 类型   | 说明                       |
|:--------- |:------ |:-------------------------- |
| id        | long   | 小说ID                     |
| fiType    | String | 小说类型                   |
| fiTags    | String | 小说标签                   |
| fiName    | String | 小说标题                   |
| fiAuthor  | String | 小说作者                   |
| fiReward  | long   | 小说打赏量                 |
| fiFlat    | String | 小说横版封面URL            |
| fiCover   | String | 小说封面URL                |
| fiNum     | String | 小说字数                   |
| fiJieshao | String | 小说简介                   |
| fiCreate  | long   | 发布时间                   |
| fiUpdate  | long   | 更新时间                   |
| fiHeat    | long   | 小说热度                   |
| fiCoNum   | long   | 小说收藏量                 |
| fiStatus  | String | 小说上架状态               |
| fiSource  | String | 小说来源                   |
| resType   | String | 资源类型  1：漫画、2：小说 |
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
  api/index/{type}
  ```
  	例子：api/index/1, api/index/2
  ```
- ##### 请求方式
  POST
  - ##### 请求参数 `(路径参数)`
  | 参数 | 类型 | 说明 |
  | ---- | ---- | ---- |
  | type | int  | URL参数 1：漫画、2：小说、 缺省：无数据    |
- ##### 响应参数
  | 小说参数  | 类型   | 说明               		|
  |:-------- |:------ |:--------------------------|
  | id       | long   | 小说ID               		 |
  | fiType   | String | 小说类型                    |
  | fiTags   | String | 小说标签                    |
  | fiName   | String | 小说标题                   |
  | fiAuthor | String | 小说作者                   |
  | fiReward | long   | 小说打赏量                 |
  | fiFlat   | String | 小说横版封面URL             |
  | fiCover  | String | 小说封面URL 			   |
  | fiNum    | String | 小说字数		            |
  | fiJieshao| String | 小说简介                   |
  | fiCreate | long	  | 发布时间                  |
  | fiUpdate | long   | 更新时间        		  |
  | fiHeat   | long   | 小说热度				  |
  | fiCoNum  | long   | 小说收藏量                 |
  | fiStatus | String | 小说上架状态               |
  | fiSource | String |	小说来源				 |
  | resType  | String | 资源类型  1：漫画、2：小说 |

  | 漫画参数   | 类型   | 说明               		|
  |:---------|:------ |:---------------------------|
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
    "data": [
        {
            "name": "收藏排行",
            "list": [
                {
                    "fiType": "穿越幻想",
                    "fiTags": "杀手，穿越重生，驱魔",
                    "fiSource": "万众",
                    "resType": "2",
                    "fiUpdate": 2017,
                    "fiReward": 0,
                    "fiHeat": 1050,
                    "fiFlat": "",
                    "fiStatus": "已上架",
                    "fiNum": 774464,
                    "fiCreate": 2017,
                    "fiName": "狂颜三小姐：风流驱魔师",
                    "fiAuthor": "御赐毒药",
                    "fiEnd": "1",
                    "fiCover": "http://cdn.dolulu.com.cn/fiction/wz/1508396309273316635.jpg",
                    "fiJieshao": "女人恨之入骨的妖精，男人趋之若鹜的毒药，她，堂堂顶级杀手竟命丧于缠绵游戏！一朝重生，她竟躺在一群无头丧尸中！尼玛！身处神魔异界，上有众妖缠身，下有群男夺心！那她顺从天意，化身为“魔”又如何？驱妖魔，驭神兽，泡美男，且看她现代女屌丝，如何生杀予夺，锋芒展露，仗剑天下……",
                    "id": 42,
                    "fiCoNum": 797
                }
            ]
        }
    ],
    "status": 10
}
```

### 3. 获取作品章节内容
- ##### url
  api/chapter
- ##### 请求方式
  POST
  - ##### 请求参数
  | 参数 | 类型   | 说明 |
  | ---- | ------| ---- |
  | type | int   | 请求数据类型 10：漫画、20：小说|
  | uid	 | String| 请求用户ID|
  | cid  | String| 章节ID|
  | pid  | String| 作品ID，即小说ID或者漫画ID|
- ##### 响应参数
  | 小说参数  | 类型   | 说明                       |
  |:--------- |:------ |:-------------------------- |
  | content   | String | 章节内容                   |
  | history   | int    | 用户阅读历史记录           |
  | isFree    | int    | 内容是否收费 0:免费 1:收费 |
  | name      | String | 章节名                   |
  | price     | int    | 收费价格                   |
  | words     | int    | 章节字数(对小说内容章节)    |
  | url       | String  | 章节内容文件URL|

  ``` json
  {
	"data": {
		"content": "更靠着她的身子，不知道谈成了多少笔大生意。",
		"history": 22,
		"isFree": 0,
		"name": "第376章 情侣",
		"price": 0,
		"words": 2010
	},
	"status": 10
  }
  ```

### 4. 获取手机短信验证码
- ##### url
	api/user/code
- ##### 请求方式
	POST
- ##### 请求参数
	| 参数 | 类型   | 说明 |
	| ---- | ------| ---- |
	| type | int   | 用户操作码 10：登陆操作、20：密码重置操作|
	| phone| String| 用户获取验证码的手机号|
- ##### 响应参数
	| 参数  | 类型    | 说明                       |
	|:--------- |:------ |:--------------------------|
	| status    | int    | 请求状态 10:请求成功、20请求失败|
	| msg	    | String | 结果提示			           |

  ``` json
	{
		"msg": "短信已经成功发送，请验收完成注册",
		"status": 10
	}
  ```

### 5. 验证短信验证码
  - ##### url
  	api/user/code/checker
  - ##### 请求方式
  	POST
  - ##### 请求参数
  	| 参数 | 类型   | 说明 |
  	| ---- | ------| ---- |
  	| type | int   | 用户操作码 10：登陆操作、20：密码重置操作|
  	| phone| String| 用户获取验证码的手机号|
	| code | String| 用户收到的短信验证码 |
  - ##### 响应参数
  	| 参数  | 类型    | 说明                       |
  	|:--------- |:------ |:--------------------------|
  	| status    | int    | 请求状态 10:请求成功、20请求失败|
  	| msg	    | String | 结果提示			           |

    ``` json
  	{
  		"msg": "短信已经成功发送，请验收完成注册",
  		"status": 10
  	}
    ```

### 6. 用户注册
- ##### url
	api/user/register
- ##### 请求方式
	POST
- ##### 请求参数
	| 参数 | 类型   | 说明 |
	| ---- | ------| ---- |
	| name | String| 用户昵称 |
	| phone| String| 用户获取验证码的手机号|
	| pwd  | String| 用户设置的密码|
- ##### 响应参数
	| 参数  | 类型    | 说明                       |
	|:--------- |:------ |:--------------------------|
	| status    | int    | 请求状态 10:请求成功、20请求失败|
	| msg	    | String | 结果提示			           |

    ``` json
	{
		"msg": "短信已经成功发送，请验收完成注册",
		"status": 10
	}
    ```

### 7. 用户登录
- ##### url
	api/user/login
- ##### 请求方式
	POST
- ##### 请求参数
	|   参数   | 类型   | 说明 |
	| :--------| ------| ---- |
	| account  | String| 用户登陆账号 |
	| pwd      | String| 用户密码|
- ##### 响应参数
	|     参数  | 类型    | 说明             |
	|:--------- |:------ |:-----------------|
	| status	| String | 用户昵称		|
	| msg		| String | 注册结果信息|

    ``` json
	{
		"msg": "完成注册",
		"status": 10
	}
    ```

### 8. 用户重置密码
- ##### url
	api/user/pwd/reset
- ##### 请求方式
	POST
- ##### 请求参数
	|   参数   | 类型   | 说明 |
	| :--------| ------| ---- |
	| phone	   | String| 用户手机号 |
	| code     | String| 用户收到的短信验证码|
	| pwd      | String| 用户密码|
- ##### 响应参数
	|     参数  | 类型    | 说明             |
	|:--------- |:------ |:-----------------|
	| status	| String | 用户昵称		|
	| msg		| String | 结果信息|

    ``` json
	{
		"msg": "完成修改",
		"status": 10
	}
    ```

### 9. 获取作品详情页信息
- ##### url
	api/work
- ##### 请求方式
	POST
- ##### 请求参数
	|   参数   | 类型   | 说明 |
	| :--------| ------| ---- |
	| uid	   | String| 用户手机号 |
	| wType    | int   | 作品类型 10：漫画、20：小说|
	| wId	   | String| 作品ID|
- ##### 响应参数
	|     参数  | 类型    | 说明             |
	|:--------- |:------ |:-----------------|
	| id        | int    | 作品ID |
	| name		| String | 作品名			|
	| author	| String | 作品作者			|
	| category	| String | 分类|
	| tags		| String | 标签|
	| collection| long   | 收藏量|
	| heat 	    | long   | 热度 |
	| isEnd     | String | 是否完结|
	| isFree    | String | 是否收费|
	| reward    | long   | 打赏量|
	| score     | String | 评分|
	| totalScore| String | 总评分|
	| summary   | String | 作品简介|
	| reward.id | long   | 打赏记录ID|
	| reward.uAvatar | String   | 打赏用户头像|
 	| reward.uGold | int | 打赏金额 |
	| reward.uName | String | 打赏用户名 |
	| comments.cNum| int | 评论回复数 |
	| comments.coPraise| int | 评论点赞数|
	| comments.coType| long | 评论作品的类型 f: 小说 m: 漫画|
	| comments.createAt| long | 评论创建时间戳 |
	| comments.id| long | 该评论的ID |
	| comments.pId| int | 评论的作品的ID |
	| comments.uId| long | 评论用户的Id |
	| comments.uTouxiang| String | 评论用户头像 |
	| comments.uName| String | 评论用户昵称 |
	| comments.isReply| String | 当前查看用户是否评论过该条评论 0: 没有、1:有|
	| comments.isLike| String | 当前查看用户是否点赞过该条评论  0: 没有、1:有|
	| like.id| int | 猜你喜欢的作品ID |
	| like.name| String | 猜你喜欢的作品名称 |
	| like.cover| String | 猜你喜欢的作品的封面 |

    ``` json
	{
	    "data": {
	        "work": {
	            "author": "久鱼",
	            "category": "现代都市",
	            "collection": 1929,
	            "heat": 8125,
	            "id": 7,
	            "isEnd": "未完结",
	            "isFree": "收费",
	            "name": "罪恶青春",
	            "reward": 0,
	            "score": "9.3",
	            "summary": "辍学那年，我开启了自己的热血人生。夜场女王、公主萝莉、清纯学妹、黑道御姐一一找上门……",
	            "tags": "罪恶,青春,久鱼,夜场",
	            "totalScore": "0"
	        },
	        "reward": [
	            {
	                "id": 15,
	                "uAvatar": "http://res.dolulu.com.cn/mobile/images/assets/touxiang.png",
	                "uGold": 300,
	                "uName": "烈艳-于洁"
	            }
	        ],
			"like": [
			    {
				    "cover": "http://cdn.dolulu.com.cn/fiction/wz/20160521225742_xum1tn.jpg",
				    "id": 634,
				    "name": "总裁爹地霸王攻",
			    }
		    ],
	        "comments": [
	            {
					"uName": "1",
					"isLike": "1",
					"isReply": "1",
	                "cNum": 0,
	                "coPraise": 45,
	                "coType": "f",
	                "createAt": 1514438088000,
	                "id": 1,
	                "pId": 7,
	                "uId": 16,
	                "uTouxiang": "http://res.dolulu.com.cn/mobile/images/assets/touxiang.png"
	            }
	        ]
	    },
	    "status": 10
	}
    ```

### 10. 获取用户信息
- ##### url
	api/user/info
- ##### 请求方式
	POST
- ##### 请求参数
	|   参数   | 类型   | 说明 |
	| :--------| ------| ---- |
	| account  | String| 用户账号(手机号) |
- ##### 响应参数
    | 参数      | 类型   | 说明                  |
    |:--------- |:------ |:--------------------- |
    | id        | long   | 用户                  |
    | uAvatar   | String | 用户头像              |
    | uName     | String | 用户昵称              |
    | uPhone    | String | 用户手机号            |
    | uIsAuthor | String | 是否是作者 0:否、1:是 |
    | uCountry  | String | 国家                  |
    | uCity     | String | 城市                  |
    | uProvince | String | 省份                  |

    ``` json
	{
	    "data": {
	        "id": 1,
	        "uAvatar": "",
	        "uCity": "",
	        "uCountry": "",
	        "uGold": 4025,
	        "uIsAuthor": "0",
	        "uName": "Cloud59235125",
	        "uPhone": "17788704650",
	        "uProvince": ""
	    },
	    "status": 10
	}
    ```

### 11. 获取作品的章节目录信息
- ##### url
	api/work/table
- ##### 请求方式
	POST
- ##### 请求参数
    | 参数  | 类型   | 说明                        |
    |:----- | ------ | --------------------------- |
    | uid   | String | 用户账号(手机号)            |
    | wId   | String | 作品ID                      |
    | wType | int    | 作品类型 10：漫画、20：小说 |
    | sort  | String | 正反序 ("DESC"、"ASC")      |
- ##### 响应参数
    | 参数    | 类型   | 说明                    |
    |:------- |:------ |:----------------------- |
	| id      | int	   | 章节ID                  |
    | name    | String | 章节名                  |
	| order   | int    | 章节的自然顺序				|
    | isFree  | int    | 是否收费 0:免费、1:收费 |
    | isPay   | int    | 是否付费 0:未支付、1:已支付、2：未登录用户|
	| price   | int    | 收费价格				 |
    | history | String | 阅读记录                |

    ``` json
	{
	    "data": {
	        "history": "12470",
	        "chapters": [
	            {
	                "id": 12582,
	                "isFree": 1,
	                "isPay": 0,
	                "name": "第361章   我缺一个新娘",
	                "price": 39,
					"order": 361
	            }
	        ]
	    },
	    "status": 10
	}
    ```