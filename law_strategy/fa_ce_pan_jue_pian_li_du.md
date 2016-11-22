#法策判决结果偏离度
根据用户选择的标签或者上传的裁判文书，分析相似案例和偏离度。

#请求参数

##请求参数说明
```js
province_id:省份id,
start_time:开始时间,
end_time:结束时间,
amount:涉案金额，
amount_tag:涉案金额标签，
fine:罚金,
detention:拘役,
prison_term:有期徒刑,
probation:缓刑,
selectedTags:标签英文名列表,
source:来源,0 裁判文书 1：其他,
```

##请求参数示例

```js
selectedTags:["college", "new_methods","vehicles_and_components","public_facilities_equipment_and_components"]
detention:-1
amount:0
prison_term:8
fine:3000
probation:12
province_id:
amount_tag:30w_50w
```

#返回数据

##返回数据说明

```js
{
    code:0,
    msg:"",
    data:{
        time:'近一年',           //时间范围
        province:'浙江省',       //省份
        judge_count:314,        //法官数量
        case_count:25410,       //案件数量

        total_deviation:45,     //综合偏离度，范围0~100%
        judgement_term:{
            value:24,       //刑期（单位，月）
            deviation:↑14%,    //刑期的偏离度%    高于用向上箭头，低于用向下箭头
            style:'blue'        //偏离度高于10%为blue,低于-10%为red，在-10~10之间为green
        },
        fine:{
            value:1000,       //罚金（单位，元）
            deviation:↓-8%      //罚金的偏离度%
            style:'red'        //偏离度高于10%为blue,低于-10%为red，在-10~10之间为green
        },
        probation_term:{
            value:6,        //缓刑（单位，月）
            deviation:2%    //缓刑的偏离度%
            style:'green'        //偏离度高于10%为blue,低于-10%为red，在-10~10之间为green
        },

        map_judgement_term:[    //各个城市平均刑期
            {name: '舟山市',value: 111},
            {name: '杭州市',value: 467},
            {name: '宁波市',value: 45},
            {name: '台州市',value: 46},
            {name: '温州市',value: 78},
            {name: '丽水市',value: 111},
            {name: '衢州市',value: 45},
            {name: '金华市',value: 78},
            {name: '绍兴市',value: 265},
            {name: '嘉兴市',value: 52},
            {name: '湖州市',value: 1}
        ],
        map_deviation:{     //各个城市偏离度
            '舟山市': 11%,
            '杭州市': 12%,
            '宁波市': 30%,
            '台州市': -10%,
            '温州市': 24%,
            '丽水市': 32%,
            '衢州市': 70%,
            '金华市': 1%,
            '绍兴市': 8%,
            '嘉兴市': 16%,
            '湖州市': 11%,
        },
        map_max:{       //刑期最大的城市
            name:"杭州市",
            value:467
        }
        map_min:{       //刑期最小的城市
            name:"湖州市",
            value:1
        },
        max_deviation_city:宁波市,     //偏离度最大的城市
        min_deviation_city:台州市,     //偏离度最小的城市

        law_statistics:[    //这边要5个数据
            {
                law_name:《中华人民共和国婚姻法》第六十四条,      //法条名字
                count:132,                                      //法条引用次数
                percent:90                                      //法条引用比例0~100%
            },{
                law_name:《中华人民共和国婚姻法》第四条,      //法条名字
                count:82,                                      //法条引用次数
                percent:72                                      //法条引用比例0~100%
            },{
                law_name:《中华人民共和国婚姻法》第十条,      //法条名字
                count:62,                                      //法条引用次数
                percent:54                                      //法条引用比例0~100%
            },{
                law_name:《中华人民共和国婚姻法》第十四条,      //法条名字
                count:41,                                      //法条引用次数
                percent:34
            },{
                law_name:《中华人民共和国婚姻法》第三条,      //法条名字
                count:14,                                      //法条引用次数
                percent:10
            }
        ],

        party_education:[               //当事人学历
            {value:542, name:'大专以下'},
            {value:135, name:'本科'},
            {value:15, name:'硕士'},
            {value:2, name:'博士'}
        ],
        party_native_count:{    //当事人籍贯统计，取最高的5个城市
            citys:['衢州市','金华市','绍兴市','嘉兴市','湖州市'],
            values:[195.6, 182.2, 48.7, 18.8, 6.0]
        },
        party_record:[              //当事人前科统计
            {name:'强奸',value:30},
            {name:'抢劫',value:40},
            {name:'杀人',value:2}
        ]
    }
}
```

##返回数据说明

```js
{
  "code": 0,
  "msg": "返回成功",
  "data": {
    "map_max": {
      "value": 9,
      "name": "嘉兴市"
    },
    "fine": {
      "value": 5490,
      "style": "blue",
      "deviation": "↓-45%"
    },
    "probation_term": {
      "value": 13,
      "style": "red",
      "deviation": "↓-10%"
    },
    "map_judgement_term": [
      {
        "value": 0,
        "name": "舟山市"
      },
      {
        "value": 4,
        "name": "衢州市"
      },
      {
        "value": 5,
        "name": "宁波市"
      },
      {
        "value": 6,
        "name": "杭州市"
      },
      {
        "value": 0,
        "name": "温州市"
      },
      {
        "value": 9,
        "name": "嘉兴市"
      },
      {
        "value": 5,
        "name": "湖州市"
      },
      {
        "value": 4,
        "name": "绍兴市"
      },
      {
        "value": 0,
        "name": "金华市"
      },
      {
        "value": 0,
        "name": "台州市"
      },
      {
        "value": 8,
        "name": "丽水市"
      }
    ],
    "time": "近一年",
    "party_record": [
      {
        "value": 45,
        "name": "刑满释放"
      },
      {
        "value": 23,
        "name": "行政拘留"
      },
      {
        "value": 8,
        "name": "劳动教养"
      },
      {
        "value": 7,
        "name": "前科"
      },
      {
        "value": 3,
        "name": "强制"
      },
      {
        "value": 1,
        "name": "罚款"
      }
    ],
    "map_deviation": {
      "衢州市": "-4%",
      "丽水市": "-3%",
      "宁波市": "1%",
      "温州市": "0%",
      "舟山市": "0%",
      "绍兴市": "-3%",
      "嘉兴市": "-15%",
      "台州市": "0%",
      "湖州市": "-2%",
      "金华市": "0%",
      "杭州市": "-13%"
    },
    "max_deviation_city": "宁波市",
    "law_statistics": [
      {
        "count": 85,
        "percent": 25,
        "law_name": "《中华人民共和国刑法》盗窃罪第二百六十四条"
      },
      {
        "count": 55,
        "percent": 16,
        "law_name": "《中华人民共和国刑法》适用条件第七十二条"
      },
      {
        "count": 48,
        "percent": 14,
        "law_name": "《中华人民共和国刑法》自首第六十七条"
      },
      {
        "count": 32,
        "percent": 9,
        "law_name": "《中华人民共和国刑法》罚金数额的裁量第五十二条"
      },
      {
        "count": 29,
        "percent": 8,
        "law_name": "《中华人民共和国刑法》考验期限第七十三条"
      }
    ],
    "min_deviation_city": "杭州市",
    "judgement_term": {
      "value": 28,
      "style": "blue",
      "deviation": "0%"
    },
    "province": "浙江省",
    "party_education": [
      {
        "value": 45,
        "name": "初中文化"
      },
      {
        "value": 33,
        "name": "小学文化"
      },
      {
        "value": 7,
        "name": "文盲"
      },
      {
        "value": 3,
        "name": "大专"
      }
    ],
    "total_deviation": -42,
    "case_count": 97,
    "map_min": {
      "value": 0,
      "name": "台州市"
    },
    "judge_count": 7,
    "party_native_count": {
      "values": [
        195.6,
        182.2,
        48.7,
        18.8,
        6
      ],
      "citys": [
        "衢州市",
        "金华市",
        "绍兴市",
        "嘉兴市",
        "湖州市"
      ]
    }
  }
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


