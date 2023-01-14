####	python-json

```python
import json
data=[{"a":1,"b":2}]
data=json.dumps(data)	#python→json 
data=json.dumps(data,ensure_ascii=False)	#data中有中文时,不用ascii码转换中文
data=json.loads(data)	#json→python
```

ab173         json视图懒人工具

####	pyecharts（eg）

一堆图形代码的地方(https://gallery.pyecharts.org/#/)

#####	折线图

```python
from pyecharts.charts import  Line
from pyecharts.options import TitleOpts,LegendOpts,ToolboxOpts,VisualMapOpts
line=Line()
line.add_xaxis(["1","2","3"])
line.add_yaxis("GDP",[30,20,10])
line.set_global_opts(			#设置全局选项
    title_opts=TitleOpts(title="标题位置",pos_left="center",pos_bottom="1%"),
    legend_opts=LegendOpts(is_show=True),
    toolbox_opts=ToolboxOpts(is_show=True),
    visualmap_opts=VisualMapOpts(is_show=True)
)
line.render()
```

#####	地图

```python
from pyecharts.charts import Map
from pyecharts.options import VisualMapOpts
map=Map()
data=[
      ("北京市", 5),
      ("上海市", 19),
      ("湖南省", 299),
      ("台湾省", 599),
      ("广东省", 4999)
]
map.add("测试", data,"china")
map.set_global_opts(
    visualmap_opts=VisualMapOpts(
    is_show=True,
    is_piecewise=True,         #手动设置区间
    pieces=[
        {"min":1,"max":9,"label":"1-9人","color":"#CCFFFF"},#颜色代码可在ab173rgb灯光查询
        {"min":10,"max":99,"label":"10-99人","color":"#FFFF99"},
        {"min":100,"max":499,"label":"100-499人","color":"#FF9966"},
        {"min":500,"max":999,"label":"499-999人","color":"#FF6666"},
        {"min":1000,"max":9999,"label":"1000-9999人","color":"#CC3333"},
        {"min":10000,"label":"10000+","color":"#990033"},
    ] )
)
map.render()
```

#####	时间线柱状

```python
from pyecharts.charts import Bar,Timeline
from pyecharts.options import LabelOpts
bar1=Bar()
bar1.add_xaxis([1,2,3])
bar1.add_yaxis("啊",[10,20,30],label_opts=LabelOpts(position="right"))

bar2=Bar()
bar2.add_xaxis([1,2,3])
bar2.add_yaxis("行不行",[20,30,40],label_opts=LabelOpts(position="right"))
bar2.reversal_axis()

bar3=Bar()
bar3.add_xaxis([1,2,3])
bar3.add_yaxis("别这样",[50,60,70],label_opts=LabelOpts(position="right"))

timeline=Timeline()#构建时间线对象
#可用timeline=Timeline({"theme":ThemeType.LIGHT})来换个主题，主题名称内容见下边图
timeline.add(bar1,"d1")#添加柱状对象
timeline.add(bar2,"d2")
timeline.add(bar3,"d3")
timeline.add_schema(
    play_interval=1000,#自动播放的时间间隔，单位ms
    is_timeline_show=True, #是否在自动播放的时候显示时间线
    is_auto_play=True, #是否自动播放
    is_loop_play=True #是否循环自动播放
)
timeline.render("基础时间线柱状图.html")
```

![F(IO%C_MD$EV32]TPD1M_]V(1)](C:\Users\巨航\Desktop\python学习之路\F(IO%C_MD$EV32]TPD1M_]V(1).jpg)





