# sino-num.js

> 这是一个无聊的人在研究了一下午汉语计数方法后取得的成果。

---

中国人使用汉语计数的方法是很有意思的。

古代有万万为亿，亿亿为兆，兆兆为京，
这就是一种类似二进制的计数方法。
除了这种二进制，我们还发现十十不为百，百百不为千，千千不为万。
实际上，个十百千是另一种计数方法。
容易发现规律是：一个数所在位后面 0 的数量模 4 所得分别对应个、十、百和千。
通过这些信息，我们可以知道汉语中计数的规律。

---

这里可以举一个例子来从头寻找规律，比如`1234567890`这个数：
中国话就是`十二亿三千四百五十六万七千八百九十`。
我们来分析一下。

首先可以看万以上的单位，不难发现，他们把这个数分成了三部分：
`十二亿  三千四百五十六万  七千八百九十`

我们可以把万以上的单位叫做大单位。
之后，我们发现每个部分都有相同的规律，类似下方：
`甲千  乙百  丙十  丁  大单位`。
个十百千的规律果然不同于大单位！我们可以叫这四个为小单位。

于是，这个数字基本上就被拆完了：
它是由四个小单位所组成的四个小部分后面加上一个大单位组成一个大部分，
之后各个大部分连在一起组成的。

---

我们知道小单位的规律与大单位不同。
现在小单位的简单规律已经知道了，我们可以开始思考大单位的规律。

万后面是亿，这是我们的常识。那么亿后面是什么呢？
我们可以试着掰掰手指头，得到的答案是万亿。
那么万亿的后面又是什么呢？
根据我们的常识，应该是万万亿，也就是亿亿。而亿亿为京，所以万亿后面是京。
到这或许你已经理解了这个规律。如果还不理解，可以来把单位都列出来：

```
万 万万=亿
亿 万亿 万万亿=亿亿=京
京 万京 亿京 万亿京 亿亿京=京京=垓
垓 万垓 亿垓 万亿垓 京垓 万京垓 亿京垓 万亿京垓 亿亿京垓=京京垓=垓垓=杼
```

于是我们可以通过二进制的方法来判断一个大单位的名字叫什么。
比如我们知道一个大单位在整个数从右往左数的第13个部分，
那么我们或许可以叫这个大单位为第12位大单位
<table>
	<tr>
		<td></td>
		<td>垓</td>
		<td>京</td>
		<td>亿</td>
		<td>万</td>
	</tr>
	<tr>
		<td>12 =</td>
		<td>1</td>
		<td>1</td>
		<td>0</td>
		<td>0</td>
	</tr>
</table>
我们发现垓和京下面是 1 ，其余下面是 0 ，所以这个大单位就是京垓！
你可以数一数上方列出的大单位，看看是不是京垓。

真是太神奇啦！！

---

这只是基本的规律。
口语中还有其他规律。比如如果一个数开头是一十，会把一省掉，
还有复杂的二和两的用法之类的。
不过搞懂了这个主要的规律，其他特殊情况就不难解决了。

于是请愉快使用本脚本吧。^_^