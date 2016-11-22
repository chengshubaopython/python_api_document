#识别案由


#请求参数

##请求参数说明

```js
content:问题内容,string
```

##请求参数示例

```js
content:丈夫家暴后我出轨了，离婚时我能提损害赔偿请求吗？
```

#返回数据

##返回数据说明

```js
{
    code:0,
    msg:"",
    data:{
       "case_cause_id":案由id,
    }
}
```

##返回数据示例

```js
{
  "msg": "返回成功",
  "code": 0,
  "data": {
    "case_cause_id": 9015,
    "related_point_ids": [],
    "law_tag_names": {},
    "law_tags": "",
    "related_case_ids": [],
    "similar_question_ids": [],
    "related_law_ids": [],
    "keywords": [],
    "related_guidance_ids": []
  }
}
```

#调用方法

##方法名:

##参数:

##返回值:

#备注



