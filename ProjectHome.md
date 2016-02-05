您是否也曾被JWPlayer强大的功能所吸引？您是否也曾为播放器中不能加入自己的广告而烦恼？

Are you attracted by the powerful features of JW Player? Are you bothered by the specified player advertisement provider?

# Solution #

JWPlayer官方广告插件是一个收费软件，而且集成了各种其他广告联盟广告代码，不便于自主定制。
而dvmsad是一个替代解决方案，它可以支持使用一个XML来描述广告内容，来实现广告的定制。

Ad plugin from jwplayer is a payed software, published with other ad-union code. You cannot customize it. dvmsad is an alternative solution, which can be customized by specifying a XML data-source.

# How to use #

添加到您的播放器：

Embed to your JWPlayer：

```
<script type="text/javascript">
jwplayer("swfplayer").setup({
	autostart: true,
	flashplayer: "resource/swf/player.swf",
	file: your_file_path,
	height: 400,
	width: 960,
	domain: 'http://localhost/',
	plugins: {'resource/swf/dvmsad.swf':{}
	},
});
</script>
```

XML file 地址： domain + 'attachments/player\_ad.xml'

XML 文件格式(File formats):

```
<?xml version="1.0" encoding="utf-8" ?>
<root>
	<begin>
		<ad imgURL="http://localhost/start.png" clickURL="http://www.yipinmao.com/ad" duration="5" weight="100" w="544" h="272" cids="2,3"/>
		<ad imgURL="http://localhost/ad.flv" clickURL="http://www.yipinmao.com/ad" duration="5" weight="100" w="544" h="272" cids="2,3"/>
	</begin>
	<pause>
		<ad imgURL="http://localhost/pause.png" clickURL="http://www.yipinmao.com/ad" weight="100" w="220" h="250"/>
		<ad imgURL="http://localhost/ad.flv" clickURL="http://www.yipinmao.com/ad" weight="100" w="220" h="250"/>
	</pause>
	<end>
		<ad imgURL="http://localhost/end.png" clickURL="http://www.yipinmao.com/ad" duration="5" weight="100" w="544" h="272"/>
		<ad imgURL="http://localhost/ad.flv" clickURL="http://www.yipinmao.com/ad" duration="5" weight="100" w="544" h="272"/>
	</end>
</root>

```

# Questions & Feedback #

Email: eachcan@gmail.com