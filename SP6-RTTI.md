### SP6 RTTI 业务分析部分echart图表代码保存

**图一：数据量趋势**

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
      data: ['数据量']
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
      name: '数据量：GB',
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
        name: '数据量',
        type: 'bar',
        label: {
          normal: {
            show: false,
            position: 'top',
            fontSize: 14,
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

**图二：已开通城市请求数据量排行**

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
			data: ['城市']
		},
		xAxis: [{
			data: ['上海', '广州', '北京', '天津', '重庆',
				'南京', '新疆', '云南', '河北', '辽宁'],
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
			name: '数据量：GB',
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
				name: '城市',
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
				data: [13, 41, 12, 53, 22, 32, 13, 41, 12, 23]
			}
		]
	}
```

**图三：未开通城市请求数据量排行**

echart代码图二。