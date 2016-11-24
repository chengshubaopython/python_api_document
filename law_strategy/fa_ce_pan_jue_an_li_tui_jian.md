#偏离度案例推荐
根据用户选择的标签或者上传的裁判文书，进行案例推荐


#请求参数

##请求参数说明

```js
province_id:省份id,
```

##请求参数示例

```js
amount_tag:30w_50w
```

#返回数据

##返回数据说明

```js
{
    code:0,
    msg:"",
    data:{
       "similarity_detail":--,
       "similarity":相似度，
       "id":案例id，

    }
}
```

##返回数据示例

```js
{
  "msg": "返回成功",
  "data": [
    {
      "similarity_detail": {},
      "similarity": 0.3388496396743211,
      "id": 134400000041283
    },
    {
      "similarity_detail": {},
      "similarity": -0.13822956917627702,
      "id": 137200000025107
    },
    {
      "similarity_detail": {},
      "similarity": 0.1780885052420005,
      "id": 134000000066463
    },
    {
      "similarity_detail": {},
      "similarity": -0.23183517686607746,
      "id": 137000000077572
    },
    {
      "similarity_detail": {},
      "similarity": 0.2412885923008038,
      "id": "138700000003081"
    },
    {
      "similarity_detail": {},
      "similarity": -0.006148408765378662,
      "id": 135400000056855
    },
    {
      "similarity_detail": {},
      "similarity": -0.3020889219141856,
      "id": 130900000038938
    },
    {
      "similarity_detail": {},
      "similarity": -0.09222757625066202,
      "id": "139800000026790"
    },
    {
      "similarity_detail": {},
      "similarity": -0.3658852118838888,
      "id": "139500000072556"
    },
    {
      "similarity_detail": {},
      "similarity": -0.14582417431263225,
      "id": "140000000040857"
    }
  ],
  "code": 0
}
```

#调用方法

##方法名:predict.predict

##参数:

```js
传入裁判文书，对新的数据进行预测，并返回相关数据
默认各参数的值为None，或者-1，表示该特征没有值
:param probation: 裁判文书里的缓刑
:param fine: 裁判文书里的罚金
:param prison_term: 裁判文书里的有期徒刑
:param detention: 裁判文书里的拘役
:param tags:输入的0-1特征
:param amount:输入的涉案金额
:return:
```

##返回值:

```js
{
'total_deviation': total_deviation,
'probation': {'value': _probation, 'deviation':probation_deviation},
'fine': {'value': _fine, 'deviation': fine_deviation},
'detention': {'value': _detention, 'deviation': detention_deviation},
'prison_term': {'value': _prison_term, 'deviation': prison_term_deviation},
'similar_cases': similar_cases
}
```

#备注

-1 值不考虑;


