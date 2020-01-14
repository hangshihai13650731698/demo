# 1.通过 npm 获取 echats

```js
npm install echats --save
```

# 2 主要是多看官网的 demo 为主

# 3 多看官网的 api

# 4 数据的动态更新和主题的设置

```js
ECharts 由数据驱动，数据的改变驱动图表展现的改变，因此动态数据的实现也变得异常简单。

所有数据的更新都通过 setOption实现，你只需要定时获取数据，setOption 填入数据，而不用考虑数据到底产生了那些变化，ECharts 会找到两组数据之间的差异然后通过合适的动画去表现数据的变化。

主题设置：背景颜色的设置，或则图形颜色的设置

直接样式设置（itemStyle、lineStyle、areaStyle、label、...）
视觉映射（visualMap）内部包裹有（图形类别（symbol）、图形大小（symbolSize）
颜色（color）、透明度（opacity）、颜色透明度（colorAlpha）、
颜色明暗度（colorLightness）、颜色饱和度（colorSaturation）、色调（colorHue））
如：
 //直接样式设置
                label: {
                    normal: {
                        textStyle: {
                            color: 'rgba(255, 255, 255, 0.3)'
                        }
                    }
                },
                labelLine: {
                    normal: {
                        lineStyle: {
                            color: 'rgba(255, 255, 255, 0.3)'
                        }
                    }
                },
                itemStyle: {
                    normal: {
                        color: '#c23531',
                        shadowBlur: 200,
                        shadowColor: 'rgba(0, 0, 0, 0.5)'
                    }
                }
```
