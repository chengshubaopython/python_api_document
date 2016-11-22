#接口名称
接口描述。


#请求参数

##请求参数说明
```js
amount_tag:数额区间标签,
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
    }
}
```

##返回数据示例

```js
{
  "code": 状态码,
  "msg": "状态码描述",
  "data": "返回数据",
}
```

#调用方法

##方法名:predict_judgement

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


