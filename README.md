生命值与状态效果显示 使用说明

简单版：
安装数据包至datapacks，同时使所有用户安装附属的资源包即可。
安装数据包后，你可以将记分板dah.belowName安排至任意槽位：

例如：
显示在玩家名称下面：
/scoreboard objectives setdisplay below_name dah.belowName

显示在Tab页面
/scoreboard objectives setdisplay list dah.belowName

我在压缩包内放了两个效果图以供参考


就这些。你不需要继续往下看也可以使用本数据包。它会自动运行。



高级版：

你可以调整以下选项：

该显示器默认每10刻（半秒）刷新一次。更改#fqt在记分板dah.Bcalc上的分数来调整刷新频率
不建议调太高。一方面感觉不出来，另一方面在玩家数量像蚂蚁一样多的情况下每次刷新可能会花费大概几毫秒的时间（只要没有30多玩家就可以忽略性能消耗）
调低会使得显示器的反应变迟钝，但或许可以节省微不足道的性能。本来耗费的性能也不多就是了。

目前会显示以下状态效果：
# 虚弱
# 缓慢
# 挖掘疲劳
# 力量
# 反胃
# 黑暗
# 抗火
# 失明
# 急迫
# 饥饿
# 跳跃提升
# 夜视
# 抗性
# 潮涌
# 速度

你可以加入新的效果，或者禁用一些效果显示。这需要你更改函数dah.below:effects
想要让UI不显示一个效果，只需要注释掉或者删掉对应的一行即可。比如若不想要展示抗火效果，只需要删除
execute if data storage dah.below:m t.ram[{id:"minecraft:fire_resistance"}] run function dah.below:below_name/append {new:"P"}

想要加入新效果也是可以的。你甚至可以加入并非状态效果的其他自定义状态。自己写execute if条件，满足时运行函数
function dah.below:below_name/append {new:"?"}
即可。上面的?应该替换为一个dah.below:icon字体文件中规定的字符（当然，你需要自己修改资源包的字体文件）。