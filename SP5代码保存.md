### SP5中的部分echarts图表配置代码

* 图一：服务请求量及请求成功率

```javascript
option = {
    tooltip: {
        trigger: 'axis',
        padding:[20],
        backgroundColor:'rgba(0,0,0,.6)'
    },
    grid: {
        left: '20px',
        right: '0',
        top: '34px',
        bottom: '64px',
        containLabel: true
    },
    grid: {
        left: '40px',
        right: '0',
        top: '34px',
        bottom: '94px',
        containLabel: true
    },
    legend: {
        type:'plain',
        itemGap: 50,
        itemWidth:22,
        bottom: '20',
        borderRadius: 20,
        left:'center',
        align:'left',
        textStyle: {
          color: '#333'
        },
        data:['请求量','请求成功率']
    },
    xAxis: [{
        type: 'category',
        axisLabel: {
          textStyle: {
            color: '#999'
          }
        },
        axisLine: {
          lineStyle: {
            color: '#999'
          }
        },
        axisTick: {
          show: false
        },
        data: ['10.20','10.21','10.22','10.23',
        '10.24','10.25','10.26','10.27','10.28',
        '10.29','10.30','10.31','11.01','11.02',
        '11.03','11.04','11.05','11.06','11.07',
        '11.08','11.09','11.10','11.11','11.12',
        '11.13','11.14']
    }],
    yAxis: [{
        type: 'value',
        name: '请求量：次',
        nameTextStyle:{
          color:'#999',
          fontSize:12,
          fontWeight:'normal'
        },
        nameGap:'10',
        position: 'left',
        axisLabel: {
          textStyle: {
            color: '#999'
          }
        },
        axisTick: {
          show: false
        },
        axisLine: {
          show: false
        },
        splitLine: {
          show: true,
          lineStyle: {
            color: '#999'
          }
        }
    },
    {
        type: 'value',
        name:'请求成功率',
        nameTextStyle:{
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        },
        nameGap:'10',
        position: 'right',
        axisLabel: {
            textStyle: {
                color: '#999'
            }
        },
        axisLine: {
            show: false
        },
        axisTick: {
            show: false
        },
        splitLine: {
            show: false,
            lineStyle: {
              color: '#999'
            }
        }
    }],
    series: [{
        name:'请求量',
        type:'bar',
        itemStyle:{
          normal:{
            color:'#0072f8'
          }
        },
        barWidth:'12',
        data:['180','260','190','200','130','230','220',
        '210','220','180','200','190','200','130','180',
        '260','190','180','200','190','200','180','200',
        '190','200','130']
    },
    {
        name:'请求成功率',
        type:'line',
        symbolSize:6,
        itemStyle:{
            normal:{
              color:'#21AC38'
            }
        },
        yAxisIndex: 1,
        data:['180','260','190','200','130','230','220',
        '210','220','180','200','190','200','130','180',
        '260','190','180','200','190','200','180','200',
        '190','200','130']
    }]
}; 
```

* 图二：服务请求成功率的趋势

```javascript
var yMax = 1;
var dataShadow = [];
for (var i = 0; i < 12; i++) {
    dataShadow.push(yMax);
}

option = {
    title: {
        text: '按月：最近12个月',
        textStyle: {
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        }
    },
    tooltip: {
        show: true,
        padding: [20],
        formatter: function (param) {
            // 如果鼠标指向背景柱状图就什么都不显示
            if (param.seriesName=='null') {
                return;
            }
            return param.seriesName + "： " + 
            (param.data*100).toFixed(2) + "%";
        }
    },
    grid: {
        left: '40px',
        right: '0',
        top: '34px',
        bottom: '94px',
        containLabel: true
    },
    legend: {
        type:'plain',
        itemWidth:20,
        bottom: 1,
        borderRadius: 20,
        left:'center',
        align:'left',
        textStyle: {
          color: '#9B9B9B'
        },
        data:['请求量']
    },
    xAxis: {
        data: ['1月','2月','3月','4月','5月','6月','7月',
        '8月','9月','10月','11月','12月'],
        axisLabel: {
            inside: false,
            textStyle: {
                color: '#9B9B9B'
            }
        },
        axisTick: {
            show: false
        },
        axisLine: {
            show: false
        },
        z: 10
    },
    yAxis: {
        name: '请求成功率',
        nameTextStyle:{
          color:'#999',
          fontSize:12,
          fontWeight:'normal'
        },
        nameGap:'15',
        axisLine: {
            show: false
        },
        axisTick: {
            show: false
        },
        axisLabel: {
            textStyle: {
                color: '#999'
            },
            formatter: function (value) {
                return (value*100) + '%';
            }
        }
    },
    
    series: [
        { // For shadow
            name: "null",
            type: 'bar',
            itemStyle: {
                normal: {color: 'rgba(28,105,212,0.2)'},
                emphasis: {color: 'rgba(28,105,212,0.2)'}
            },
            barGap:'-100%',
            barCategoryGap:'40%',
            data: dataShadow,
            animation: false,
            markArea: {
                silent: true
            }
        },
        {
            name: '请求量',
            type: 'bar',
            itemStyle: {
                normal: {
                    color: 'rgb(28,105,212)'
                },
                emphasis: {
                    color: '#0072F9'
                }
            },
            data: [0.22, 0.18, 0.19, 0.23, 0.29, 0.33,
            0.31, 0.12, 0.44, 0.32, 0, 0.23]
        }
    ]
};
```


* 图三：请求热图及成功率

```javascript
option = {
    tooltip: {
        trigger: 'axis',
        padding:[20],
        backgroundColor:'rgba(0,0,0,.6)'
    },
    grid: {
        left: '20px',
        right: '0',
        top: '34px',
        bottom: '64px',
        containLabel: true
    },
    legend: {
        type:'plain',
        itemGap: 30,
        itemWidth:20,
        bottom: '20',
        borderRadius: 20,
        left:'center',
        align:'left',
        textStyle: {
          color: '#999'
        },
        data:['请求量','请求成功率']
    },
    xAxis: [{
        type: 'category',
        axisLabel: {
          textStyle: {
            color: '#999'
          }
    },
    axisLine: {
        lineStyle: {
            color: '#999'
        }
    },
    axisTick: {
        show: false
    },
    data: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,
          19,20,21,22,23,24]
    }],
    yAxis: [{
        type: 'value',
        name: '请求量：次',
        nameTextStyle:{
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        },
        nameGap:'10',
        position: 'left',
        axisLabel: {
            textStyle: {
                color: '#999'
            }
        },
        axisTick: {
            show: false
        },
        axisLine: {
            show: false
        },
        splitLine: {
            show: true,
            lineStyle: {
                color: '#999'
            }
        }
    },
    {
        type: 'value',
        name: '请求成功率',
        nameTextStyle:{
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        },
        nameGap:'10',
        position: 'right',
        offset: -8,
        min: 0,
        max: 50,
        axisLabel: {
            textStyle: {
                color: '#999'
            }
        },
        axisLine: {
            show: false
        },
        axisTick: {
            show: false
        },
        splitLine: {
            show: false,
            lineStyle: {
                color: '#999'
            }
        }
    }],
    series: [{
        name: '请求量',
        type:'scatter',
        itemStyle:{
            normal:{
                color:'#0072f8'
            }
        },  
        data:[0,0,0,43,0,3,4,5,10,1,2,0,0,15,0,2,1,5,4,15,
              1,2,2,2,]
    },
    {
        name:'请求成功率',
        type:'line',
        symbolSize:6,
        itemStyle:{
            normal:{
                color:'#EA6102'
            }
        },
        yAxisIndex: 1,
        data:[21,20,25,28,31,28,30,25,20,25,28,30,31,
             25,30,26,25,27,31,22,24,22,26,29  ]
    }]
}
```

* 图四：平均响应时长趋势

```javascript
option = {
    title: {
        text: '按月：最近12个月',
        textStyle: {
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        }
    },
    tooltip: {
        show: true,
        padding: [20],
        formatter: '{a}： {c}'
    },
    grid: {
        left: '40px',
        right: '0',
        top: '34px',
        bottom: '94px',
        containLabel: true
    },
    legend: {
        type:'plain',
        itemWidth:20,
        bottom: 1,
        borderRadius: 20,
        left:'center',
        align:'left',
        textStyle: {
          color: '#9B9B9B'
        },
        data:['平均响应时长']
      },
    xAxis: {
        data: ['1月','2月','3月','4月','5月','6月','7月',
        '8月','9月','10月','11月','12月'],
        axisLabel: {
            inside: false,
            textStyle: {
                color: '#9B9B9B'
            }
        },
        axisTick: {
            show: false
        },
        axisLine: {
            show: false
        },
        z: 10
    },
    yAxis: {
        name: '响应时长：秒',
        nameTextStyle:{
          color:'#999',
          fontSize:12,
          fontWeight:'normal'
        },
        nameGap:'20',
        axisLine: {
            show: false
        },
        axisTick: {
            show: false
        },
        axisLabel: {
            textStyle: {
                color: '#999'
            }
        }
    },
    
    series: [
        {
            name: '平均响应时长',
            type: 'bar',
            itemStyle: {
                normal: {
                    color: 'rgb(28,105,212)'
                },
                emphasis: {
                    color: '#0072F9'
                }
            },
            data: [12,16,17,10,19,14,17,12,8,14,12,16]
        }
    ]
};
```

* 图五：响应时长分布状况

```javascript
option = {
    color: ['#5A74ED','#24A7D3','#00C482','#8ADC87','#FEB100'],
    title: {
        text: '最近1个月',
        textStyle: {
            color:'#999',
            fontSize:12,
            fontWeight:'normal'
        }
    },
    tooltip: {
        trigger: 'item',
        formatter: "{a} <br/>{b}: {c} ({d}%)"
    },
    grid: {
        left: '40px',
        right: '0',
        top: '34px',
        bottom: '64px',
        containLabel: true
    },
    legend: {
        
        x: 'center',
        bottom: '8%',   
        data:['5-10s','10-15s','15-20s','20-25s','25s以上']
    },
    series: [
        {
            name:'响应时长分布',
            type:'pie',
            radius: ['35%', '60%'],
            avoidLabelOverlap: false,
            label: {
                normal: {
                    show: false,
                    position: 'center'
                }
            },
            labelLine: {
                normal: {
                    show: false
                }
            },
            itemStyle: {
                normal: {
                    borderWidth: 4,
                    borderColor: '#fff'
                }
            },
            data:[
                {value:335, name:'5-10s'},
                {value:310, name:'10-15s'},
                {value:234, name:'15-20s'},
                {value:135, name:'20-25s'},
                {value:1548, name:'25s以上'}
            ]
        }
    ]
};
```

* 图六：各城市请求状况

```javascript
option = {
    title : {
        text: '各城市请求状况',
        x:'left'
    },
    tooltip : {
        padding: [20],
        trigger: 'item'
    },
    dataRange: {
        min: 0,
        max: 3500,
        x: 'left',
        y: 'center',
        color: ['#0653b6','#e8e8e8'],        // range 范围的颜色
        text:['3.5K','0'],                   // 文本，默认为数值文本
        calculable : false
    },
    
    series : [
        {
            name: '请求量',
            type: 'map',
            mapType: 'china',
            roam: false,
            itemStyle:{
                normal:{label:{show:true}},
                emphasis:{label:{show:true}}
            },
            data:[
                {name: '北京',value: Math.round(Math.random()*3500)},
                {name: '天津',value: Math.round(Math.random()*3500)},
                {name: '上海',value: Math.round(Math.random()*3500)},
                {name: '重庆',value: Math.round(Math.random()*3500)},
                {name: '河北',value: Math.round(Math.random()*3500)},
                {name: '河南',value: Math.round(Math.random()*3500)},
                {name: '云南',value: Math.round(Math.random()*3500)},
                {name: '辽宁',value: Math.round(Math.random()*3500)},
                {name: '黑龙江',value: Math.round(Math.random()*3500)},
                {name: '湖南',value: Math.round(Math.random()*3500)},
                {name: '安徽',value: Math.round(Math.random()*3500)},
                {name: '山东',value: Math.round(Math.random()*3500)},
                {name: '新疆',value: Math.round(Math.random()*3500)},
                {name: '江苏',value: Math.round(Math.random()*3500)},
                {name: '浙江',value: Math.round(Math.random()*3500)},
                {name: '江西',value: Math.round(Math.random()*3500)},
                {name: '湖北',value: Math.round(Math.random()*3500)},
                {name: '广西',value: Math.round(Math.random()*3500)},
                {name: '甘肃',value: Math.round(Math.random()*3500)},
                {name: '山西',value: Math.round(Math.random()*3500)},
                {name: '内蒙古',value: Math.round(Math.random()*3500)},
                {name: '陕西',value: Math.round(Math.random()*3500)},
                {name: '吉林',value: Math.round(Math.random()*3500)},
                {name: '福建',value: Math.round(Math.random()*3500)},
                {name: '贵州',value: Math.round(Math.random()*3500)},
                {name: '广东',value: Math.round(Math.random()*3500)},
                {name: '青海',value: Math.round(Math.random()*3500)},
                {name: '西藏',value: Math.round(Math.random()*3500)},
                {name: '四川',value: Math.round(Math.random()*3500)},
                {name: '宁夏',value: Math.round(Math.random()*3500)},
                {name: '海南',value: Math.round(Math.random()*3500)},
                {name: '台湾',value: Math.round(Math.random()*3500)},
                {name: '香港',value: Math.round(Math.random()*3500)},
                {name: '澳门',value: Math.round(Math.random()*3500)}
            ]
        }
    ]
};
```

*注：目前颜色问题还未能解决*

* 图七： 请求增长率城市状况

```javascript

```