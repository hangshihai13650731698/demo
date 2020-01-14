# 1. title

```js
title 标题组件（常用的配置项有）
title.id
title.show(显示或隐藏)
title.link（引入链接）
title.target
title.textStyle(包裹有颜色color，fontstyle字体风格，粗细fontWegiht，大小size)
tilte.textStyle.rich在 rich 里面，可以自定义富文本样式。利用富文本样式，可以在标签中做出非常丰富的效果。
如：
label: {
    // 在文本中，可以对部分文本采用 rich 中定义样式。
    // 这里需要在文本中使用标记符号：
    // `{styleName|text content text content}` 标记样式名。
    // 注意，换行仍是使用 '\n'。
    formatter: [
        '{a|这段文本采用样式a}',
        '{b|这段文本采用样式b}这段用默认样式{x|这段用样式x}'
    ].join('\n'),

    rich: {
        a: {
            color: 'red',
            lineHeight: 10
        },
        b: {
            backgroundColor: {
                image: 'xxx/xxx.jpg'
            },
            height: 40
        },
        x: {
            fontSize: 18,
            fontFamily: 'Microsoft YaHei',
            borderColor: '#449933',
            borderRadius: 4
        },
        ...
    }
}
```

# 2.legend（图例组件即图形的形状标题）

```js
常用的配置项(属性)
legend.type（图形类型）
'plain'：普通图例。缺省就是普通图例。
'scroll'：可滚动翻页的图例。当图例数量较多时可以使用。
参见 滚动图例（垂直） 或 滚动图例（水平）。

当使用 'scroll' 时，这些使用这些设置进行细节配置：

legend.scrollDataIndex
legend.pageButtonItemGap
legend.pageButtonGap
legend.pageButtonPosition
legend.pageFormatter
legend.pageIcons
legend.pageIconColor
legend.pageIconInactiveColor
legend.pageIconSize
legend.pageTextStyle
legend.animation
legend.animationDurationUpdate

legend.id(组件id 默认不指定。指定则可用于在 option 或者 API 中引用组件。)
```

# 3.grid(直角坐标系内绘图网格少用单个 grid 内最多可以放置上下两个 X 轴，左右两个 Y 轴。可以在网格上绘制折线图，柱状图，散点图（气泡图）。)

```js
属性：
grid. id
string
组件 ID。默认不指定。指定则可用于在 option 或者 API 中引用组件。

grid. show
boolean
是否显示直角坐标系网格。
```

# 4.xAxis yAxis(坐标的 x 轴 y 轴，xy 的属性对应)

```js
属性：
xAxis. type = 'category'
string
坐标轴类型。
可选：
'value' 数值轴，适用于连续数据。

'category' 类目轴，适用于离散的类目数据，为该类型时必须通过 data 设置类目数据。

'time' 时间轴，适用于连续的时序数据，与数值轴相比时间轴带有时间的格式化，在刻度计算上也有所不同，例如会根据跨度的范围来决定使用月，星期，日还是小时范围的刻度。

'log' 对数轴。适用于对数数据。

xAxis. name
string
坐标轴名称。

xAxis. nameLocation = 'end'
string 坐标轴名称显示位置。
```

# 5.polar(极坐标系，可以用于散点图和折线图。每个极坐标系拥有一个角度轴和一个半径轴。)

# 6.radiusAxis:极坐标的径向轴

```js
属性：radiusAxis. type = 'value'
string
坐标轴类型。

可选：
'value' 数值轴，适用于连续数据。
'category' 类目轴，适用于离散的类目数据，为该类型时必须通过 data 设置类目数据。
'time' 时间轴，适用于连续的时序数据，与数值轴相比时间轴带有时间的格式化，在刻度计算上也有所不同，例如会根据跨度的范围来决定使用月，星期，日还是小时范围的刻度。
'log' 对数轴。适用于对数数据。
```

# 7.angleAxis(极坐标的角度轴)

```js
属性：angleAxis. polarIndex
number
角度轴所在的极坐标系的索引，默认使用第一个极坐标系。
angleAxis. startAngle = 90
number
起始刻度的角度，默认为 90 度，即圆心的正上方。0 度为圆心的正右方。
```

# 8.radar（雷达图坐标系，只使用于雷达图）

```js
雷达图坐标系与极坐标系不同的是它的每一个轴（indicator 指示器）都是一个单独的维度，可以通过 name、axisLine、axisTick、axisLabel、splitLine、 splitArea 几个配置项配置指示器坐标轴线的样式。
```

# 9.dataZoom(用于区域缩放)

```js
内置型数据区域缩放组件（dataZoomInside）：内置于坐标系中，使用户可以在坐标系上通过鼠标拖拽、鼠标滚轮、手指滑动（触屏上）来缩放或漫游坐标系。

滑动条型数据区域缩放组件（dataZoomSlider）：有单独的滑动条，用户在滑动条上进行缩放或漫游。

框选型数据区域缩放组件（dataZoomSelect）：提供一个选框进行数据区域缩放。即 toolbox.feature.dataZoom，配置项在 toolbox 中。
```

# 10.visualMap(visualMap 是视觉映射组件，用于进行『视觉编码』，也就是将数据映射到视觉元素（视觉通道）。)

```js
属性元素特性有：视觉元素可以是
symbol: 图元的图形类别。
symbolSize: 图元的大小。
color: 图元的颜色。
colorAlpha: 图元的颜色的透明度。
opacity: 图元以及其附属物（如文字标签）的透明度。
colorLightness: 颜色的明暗度，参见 HSL。
colorSaturation: 颜色的饱和度，参见 HSL。
colorHue: 颜色的色调，参见 HSL。
visualMap 组件可以定义多个，从而可以同时对数据中的多个维度进行视觉映射。
visualMap 组件可以定义为 分段型（visualMapPiecewise） 或 连续型（visualMapContinuous），通过 type 来区分
```

# 11.tooltip(提示框组件即滑动过有提示信息)

```js
相关属性介绍：
提示框组件可以设置在多种地方：

可以设置在全局，即 tooltip

可以设置在坐标系中，即 grid.tooltip、polar.tooltip、single.tooltip

可以设置在系列中，即 series.tooltip

可以设置在系列的每个数据项中，即 series.data.tooltip
（更详细请看官网介绍）

```

# 12.axispointer(坐标轴指示器配合 tooptip 使用)

```js
坐标轴指示器是指示坐标轴当前刻度的工具。
```

# 13.toolbox（工具栏，内置有导出图片，数据视图，动态类型切换，数据区域缩放，重置五个工具。）

```js
属性：toolbox.show=true;(是否显示工具栏组件)
toolbox.orient= 'horizontal'(工具栏的图标布局朝向，有两个可选方向：'horizontal'
'vertical')
更具体看官网介绍
```

# 14.brush:选择区域组件（用户可以选择图中一部分数据，从而便于向用户展示被选中数据，或者他们的一些统计计算结果）

```js
刷子的类型和启动按钮

目前 brush 组件支持的图表类型：scatter、bar、candlestick（parallel 本身自带刷选功能，但并非由 brush 组件来提供）。

点击 toolbox 中的按钮，能够进行『区域选择』、『清除选择』等操作。
```

# 15.geo:地理坐标系组件（地理坐标系组件用于地图的绘制，支持在地理坐标系上绘制散点图，线集）

```js
属性：geo. show = true
boolean
是否显示地理坐标系组件。

geo. map = ''
string
地图类型。
ECharts 中提供了两种格式的地图数据，一种是可以直接 script 标签引入的 js 文件，引入后会自动注册地图名字和数据。还有一种是 JSON 文件，需要通过 AJAX 异步加载后手动注册。

下面是两种类型的使用示例：

JavaScript 引入示例

<script src="echarts.js"></script>
<script src="map/js/china.js"></script>
<script>
var chart = echarts.init(document.getElementById('main'));
chart.setOption({
    series: [{
        type: 'map',
        map: 'china'
    }]
});
</script>
JSON 引入示例

$.get('map/json/china.json', function (chinaJson) {
    echarts.registerMap('china', chinaJson);
    var chart = echarts.init(document.getElementById('main'));
    chart.setOption({
        series: [{
            type: 'map',
            map: 'china'
        }]
    });
});
geo. roam
booleanstring
是否开启鼠标缩放和平移漫游。默认不开启。如果只想要开启缩放或者平移，可以设置成 'scale' 或者 'move'。设置成 true 为都开启（其余请看官网）
```

# 16.parallel：平行坐标系（ 是一种常用的可视化高维数据的图表）

```js
需要涉及到三个组件：parallel、parallelAxis、series-parallel
```

# 17.singleAxis:单轴（应用到散点图中展现一维数据）

# 18.timeline 组件：提供了在啊多个 Echarts option 间进行切换播放等操作的功能

# 19.graphic：原生图形元素组件

```js
可以支持的图形元素包括：

image, text, circle, sector, ring, polygon, polyline, rect, line, bezierCurve, arc, group,
```

# 20.日历坐标系组件

```js
可以在热力图散点图使用日历坐标系。
calendar. zlevel
number
所有图形的 zlevel 值。

zlevel用于 Canvas 分层，不同zlevel值的图形会放置在不同的 Canvas 中，Canvas 分层是一种常见的优化手段。
```

# 21.dataset 数据集：（用于单独的数据集声明，从而数据可以单独管理，被多个组件复用，并且可以自由指定数据到视觉的映射。）

```js
dataset. source
ArrayObject
原始数据。一般来说，原始数据表达的是二维表。可以用如下这些格式表达二维表：
二维数组，其中第一行/列可以给出 维度名，也可以不给出，直接就是数据：

dataset. dimensions
Array
使用 dimensions 定义 series.data 或者 dataset.source 的每个维度的信息。
注意：如果使用了 dataset，那么可以在 dataset.source 的第一行/列中给出 dimension 名称。于是就不用在这里指定 dimension。但是，如果在这里指定了 dimensions，那么 ECharts 不再会自动从 dataset.source 的第一行/列中获取维度信息。
```

# 22.aria:W3C 制定了无障碍富互联网应用规范集（WAI-ARIA，the Accessible Rich Internet Applications Suite），致力于使得网页内容和网页应用能够被更多残障人士访问。

# 23.seres：系列列表（每个系列通过 type 决定自己的图表类型）

# 其余（color，backgroundColor,textStyle,animation）
