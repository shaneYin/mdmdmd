*** BMW BABI SP6 CD Store部分echart图表代码保存

**图一：订单量&退款订单占比**

```javascript
  option = {
    tooltip: {
      trigger: 'axis',
      padding: [20],
      backgroundColor: 'rgba(0,0,0,.6)',
      formatter: function (params) {
        if (params[1]) {
          return params[0].name + "<br>" + params[0].marker + params[0].seriesName + "："
            + params[0].value.toLocaleString() + "<br>" + params[1].marker
            + params[1].seriesName + "：" + (params[1].value * 100) + "%";

        } else if (params[0].value > 100) {
          return params[0].name + "<br>" + params[0].marker + params[0].seriesName + "："
            + params[0].value.toLocaleString();
        } else {
          return params[0].name + "<br>" + params[0].marker
            + params[0].seriesName + "：" + (params[0].value * 100) + "%";
        }
      }
    },
    grid: {
      left: '50px',
      right: '50px',
      top: '34px',
      bottom: '94px',
      containLabel: false
    },
    legend: {
      type: 'plain',
      itemGap: 50,
      itemWidth: 22,
      bottom: '20',
      borderRadius: 20,
      left: 'center',
      align: 'left',
      textStyle: {
        color: '#333'
      },
      data: ['订单量', '退款订单占比']
    },
    xAxis: [{
      type: 'category',
      axisLabel: {
        textStyle: {
          color: '#999'
        },
        interval: 0,
        rotate: 45
      },
      axisLine: {
        show: false,
        lineStyle: {
          color: '#333'
        }
      },
      axisTick: {
        show: false
      },
      data: ['10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20',]
    }],
    yAxis: [{
      type: 'value',
      name: '订单量：个',
      nameTextStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      },
      nameGap: '15',
      position: 'left',
      axisLabel: {
        textStyle: {
          color: '#999'
        },
        formatter: function (value) {
          return value < 1000 ? 0 : (value / 1000000) + 'M';
        }
      },
      axisTick: {
        show: false
      },
      axisLine: {
        show: false,
        lineStyle: {
          color: "#333"
        }
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
      name: '退款占比',
      nameTextStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      },
      nameGap: '15',
      position: 'right',
      min: 0,
      max: 0.2,
      axisLabel: {
        textStyle: {
          color: '#999'
        },
        formatter: function (value) {
          return parseFloat(value.toFixed(4) * 100) + '%';
        }
      },
      axisLine: {
        show: false,
        lineStyle: {
          color: '#333'
        }
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
      name: '订单量',
      type: 'bar',
      itemStyle: {
        normal: {
          color: '#0072f8'
        }
      },
      label: {
        normal: {
          show: false,
          position: 'top',
          fontSize: 14,
          formatter: function (params) {
            return params.value.toLocaleString();
          },
          color: '#666'
        }
      },
      barWidth: '20',
      data: [],
      markLine: {
        lineStyle: {
          normal: {
            type: "solid",
            opacity: 0
          },
          emphasis: {
            width: 2
          }
        },
        label: {
          normal: {
            show: false,
            position: 'start',
            formatter: function (params) {
              return Math.round(params.value / 1000000) + 'M';
            }
          }
        },
        data: [
          { type: 'average', name: '平均值', symbol: "arrow" }
        ]
      }
    },
    {
      name: '退款订单占比',
      type: 'line',
      symbolSize: 6,
      label: {
        normal: {
          show: false,
          position: 'top',
          fontSize: 14,
          formatter: function (params) {
            return params.value.toLocaleString();
          },
          color: '#666'
        }
      },
      itemStyle: {
        normal: {
          color: '#21AC38'
        }
      },
      yAxisIndex: 1,
      data: [],
      markLine: {
        precision: 4,
        lineStyle: {
          normal: {
            type: "solid",
            opacity: 0
          },
          emphasis: {
            width: 2
          }
        },
        label: {
          normal: {
            show: false,
            position: 'end',
            formatter: function (params) {
              return params.value * 100 + "%";
            }
          }
        },
        data: [
          { type: 'average', name: '平均值', symbol: "arrow" }
        ]
      }
    }]
  }
```

**图三：各类型订单量**

```javascript

  option = {
    color: ['#5A74ED', '#00C482', '#FEB100'],
    title: {
      text: '最近1个月',
      textStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      }
    },
    tooltip: {
      trigger: 'item',
      formatter: "{b}: {c} ({d}%)",
      padding: [20]
    },
    grid: {
      left: '40px',
      right: '0',
      top: '34px',
      bottom: '64px',
      containLabel: false
    },
    legend: {

      x: 'center',
      bottom: '8%',
      data: [{ name: 'SINGLE_OFFER', icon: 'circle' }, { name: 'PACKAGE_OFFER', icon: 'circle' }, { name: 'DATAPLAN_OFFER', icon: 'circle' }]
    },
    series: [
      {
        name: '各类型订单量',
        type: 'pie',
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
        data: [
          { value: 335, name: 'SINGLE_OFFER' },
          { value: 310, name: 'PACKAGE_OFFER' },
          { value: 234, name: 'DATAPLAN_OFFER' },
        ]
      }
    ]
  };
```

**图四：各订单周期订单量**

```javascript
option = {
    color:['#5A74ED','#00C482','#FEB100'],
    tooltip : {
        trigger: 'axis',
        axisPointer : {            // 坐标轴指示器，坐标轴触发有效
            type : 'shadow'        // 默认为直线，可选为：'line' | 'shadow'
        }
    },
    legend: {
        x: 'center',
        bottom: '8',
        data:['SINGLE_OFFER','PACKAGE_OFFER','DATAPLAN_OFFER']
    },
    grid: {
        left: '40px',
        right: '0',
        top: '34px',
        bottom: '64px',
        containLabel: false
    },
    xAxis:  {
        type: 'category',
				axisLabel: {
					textStyle: {
						color: '#999'
					},
					interval: 0,
				},
				axisLine: {
					show: false,
					lineStyle: {
						color: '#333'
					}
				},
				axisTick: {
					show: false
				},
				data: ['3个月','6个月','12个月','24个月']
    },
    yAxis: {
        type: 'value',
				name: '订单量：个',
				nameTextStyle: {
					color: '#999',
					fontSize: 12,
					fontWeight: 'normal'
				},
				nameGap: '15',
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
					show: false,
					lineStyle: {
						color: "#333"
					}
				},
				splitLine: {
					show: true,
					lineStyle: {
						color: '#f6f6f6'
					}
				}
    },
    series: [
        {
            name: 'SINGLE_OFFER',
            type: 'bar',
            stack: '总量',
            label: {
                normal: {
                    show: false,
                    position: 'insideRight'
                }
            },
            data: [320, 302, 301, 334, 390, 330, 320]
        },
        {
            name: 'PACKAGE_OFFER',
            type: 'bar',
            stack: '总量',
            label: {
                normal: {
                    show: false,
                    position: 'insideRight'
                }
            },
            data: [120, 132, 101, 134, 90, 230, 210]
        },
        {
            name: 'DATAPLAN_OFFER',
            type: 'bar',
            stack: '总量',
            label: {
                normal: {
                    show: false,
                    position: 'insideRight'
                }
            },
            data: [220, 182, 191, 234, 290, 330, 310]
        },
        
    ]
};
```

**图五：各服务订单量排行**

```javascipt
option = {
    tooltip: {
      trigger: 'axis',
      padding: [20],
      backgroundColor: 'rgba(0,0,0,.6)',
    },
    grid: {
      left: '50px',
      right: '50px',
      top: '34px',
      bottom: '64px',
      containLabel: false
    },
    legend: {
      type: 'plain',
      itemGap: 30,
      itemWidth: 20,
      bottom: '20',
      borderRadius: 20,
      left: 'center',
      align: 'left',
      textStyle: {
        color: '#9B9B9B'
      },
      data: ['I Call', 'RTTI', 'E Call']
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
          color: '#f6f6f6'
        }
      },
      axisTick: {
        show: false
      },
      data: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12']
    }],
    yAxis: [{
      type: 'value',
      name: '订单量：个',
      nameTextStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      },
      nameGap: '10',
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
          color: '#f6f6f6'
        }
      }
    }],
    series: [{
      name: 'I Call',
      type: 'line',
      itemStyle: {
        normal: {
          color: '#5A74ED'
        }
      },
      data: [320, 302, 301, 334, 390, 330, 320,
        320, 302, 301, 334, 390]
    },
    {
      name: 'RTTI',
      type: 'line',
      symbolSize: 6,
      itemStyle: {
        normal: {
          color: '#00C482'
        }
      },
      data: [120, 132, 101, 134, 90, 230,
        120, 132, 101, 134, 90, 230]
    },
    {
      name: 'E Call',
      type: 'line',
      itemStyle: {
        normal: {
          color: '#FEB100'
        }
      },
      data: [220, 182, 191, 234, 290, 330,
        220, 182, 191, 234, 290, 330]
    }]
  }
```

**图六：各经销商订单**

```javascript
option = {
color: ['#5A74ED', '#00C482'],
    title: {
      text: '最近1个月',
      textStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      }
    },
    tooltip: {
      trigger: 'item',
      formatter: "{b}: {c} ({d}%)",
      padding: [20]
    },
    grid: {
      left: '40px',
      right: '0',
      top: '34px',
      bottom: '64px',
      containLabel: false
    },
    legend: {
      itemGap:80,
      x: 'center',
      bottom: '20',
      data: [{ name: 'BBA', icon: 'circle' }, { name: 'NSC', icon: 'circle' }]
    },
    series: [
      {
        name: '各类型订单量',
        type: 'pie',
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
        data: [
          { value: 335, name: 'BBA' },
          { value: 310, name: 'NSC' }
        ]
      }
    ]
}
```

**图七：各车型订单量**

```javascript
option = {
    tooltip: {
      show: true,
      padding: [20],
      
    },
    grid: {
      left: '50px',
      right: '50px',
      top: '34px',
      bottom: '64px',
      containLabel: true
    },
    legend: {
      type: 'plain',
      itemWidth: 20,
      bottom: '20',
      borderRadius: 20,
      left: 'center',
      align: 'left',
      textStyle: {
        color: '#9B9B9B'
      },
      data: ['订单量']
    },
    xAxis: [{
      data: ['车型1','车型2','车型3','车型4','车型5','车型6'],
      axisLabel: {
        inside: false,
        textStyle: {
          color: '#999'
        }
      },
      axisTick: {
        show: false
      },
      splitLine: {
        show: false,
        lineStyle: {
          color: '#f6f6f6'
        }
      },
      axisLine: {
        show: false,
        lineStyle: {
          color: '#999'
        }
      },
      z: 10
    }],
    yAxis: [{
      name: '订单数：个',
      nameTextStyle: {
        color: '#999',
        fontSize: 12,
        fontWeight: 'normal'
      },
      splitLine: {
        show: true,
        lineStyle: {
          color: '#f6f6f6'
        }
      },
      axisTick: {
        show: false
      },
      axisLine: {
        show: false,
        lineStyle: {
          color: "#333"
        }
      },
      nameGap: '15',
      axisLabel: {
        textStyle: {
          color: '#999'
        }
      }
    }],
    series: [
      {
        name: '订单量',
        type: 'bar',
        label: {
          normal: {
            show: false,
            position: 'top',
            fontSize: 14,
            formatter: function (params) {
              return params.value * 100 + "%";
            },
            color: '#666'
          }
        },
        markLine: {
          lineStyle: {
            normal: {
              type: "solid",
              opacity: 0
            },
            emphasis: {
              width: 2
            }
          },
          label: {
            normal: {
              show: false,
              position: 'start',
              formatter: function (params) {
                return Math.round(params.value * 100) + '%';
              }
            }
          },
          data: [
            { type: 'average', name: '平均值', symbol: "arrow" }
          ]
        },
        itemStyle: {
          normal: {
            color: 'rgb(28,105,212)'
          },
          emphasis: {
            color: '#0072F9'
          }
        },
        data: [13,41,12,53,22,32]
      }
    ]
  }
```