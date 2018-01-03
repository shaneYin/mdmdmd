### SP6中 news online导航的 浏览分析

**新闻浏览量**

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
      containLabel: false
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
      data: ['浏览量']
    },
    xAxis: [{
      data: ['10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20', '10.20', '10.20',
        '10.20', '10.20', '10.20', '10.20'],
      axisLabel: {
        inside: false,
        textStyle: {
          color: '#999'
        },
        rotate: 45
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
      name: '浏览量：个',
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
        name: '浏览量',
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
        data: [13, 41, 12, 53, 22, 32, 13, 41, 12, 53, 22, 32, 13, 41, 12,
          13, 41, 12, 53, 22, 32, 13, 41, 12, 53, 22, 32, 53, 22, 32]
      }
    ]
  }
```

**新闻类型分布**

```javascript
 option = {
    color: ['#5A74ED', '#24A7D3', '#00C482', '#8ADC87', '#FEB100'],
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
      data: [{ name: '财经', icon: 'circle' },
      { name: '科技', icon: 'circle' },
      { name: '娱乐', icon: 'circle' },
      { name: '体育', icon: 'circle' },
      { name: '国际', icon: 'circle' }]
    },
    series: [
      {
        name: '响应时长分布',
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
          { value: 335, name: '财经' },
          { value: 310, name: '科技' },
          { value: 234, name: '娱乐' },
          { value: 135, name: '体育' },
          { value: 1548, name: '国际' }
        ]
      }
    ]
  };
```

**新闻内容趋势**

```javascript
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
      data: ['组图', '文字']
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
      name: '浏览次数：次',
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
      name: '组图',
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
      name: '文字',
      type: 'line',
      symbolSize: 6,
      itemStyle: {
        normal: {
          color: '#00C482'
        }
      },
      data: [120, 132, 101, 134, 90, 230,
        120, 132, 101, 134, 90, 230]
    }]
  }
```

**24小时新闻浏览热图**

```javascript
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
      data: ['浏览次数']
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
      data: ['1', '2', '3', '4', '5', '6', '7',
        '8', '9', '10', '11', '12', '13', '14', '15', '16',
        '17', '18', '19', '20', '21', '22', '23', '24']
    }],
    yAxis: [{
      type: 'value',
      name: '浏览次数：次',
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
      name: '浏览次数',
      type: 'scatter',
      itemStyle: {
        normal: {
          color: '#5A74ED'
        }
      },
      data: [20, 42, 41, 34, 90, 30, 20,
        20, 42, 41, 34, 90, 20, 42, 41, 34,
        90, 30, 20, 20, 42, 41, 34, 90]
    }]
  }
```