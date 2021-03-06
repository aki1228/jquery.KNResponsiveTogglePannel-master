# JQuery.KNResponsiveTogglePanel

PCのクリック操作、スマホのタッチ操作、どちらでも快適に動作する開閉メニューを作りたくて自作してみました。JQueryのプラグインとして提供していますのでご自由にご利用ください。

## 設置方法

### (1) jQueryとjquery.KNResponsiveTogglePanel.jsを読み込む

jquery.KNResponsiveTogglePanel.jsをダウンロードして、任意のディレクトリにコピーしてください（jqueryは公式のサイトよりダウンロードしてください）。その後、HTMLのhead内にJQueryとjquery.KNResponsiveTogglePanel.jsを読み込みます。

	<script type="text/javascript" src="js/jquery.min.js"></script>
	<script type="text/javascript" src="js/jquery.KNResponsiveTogglePanel.js"></script>

### (2) jquery.KNResponsiveTogglePanelの初期設定

(1)のコードの次に続けて下記のコードを記述します。$(".neko_next")の部分（セレクタ部分）は好きなID名、クラス名にする事ができます。

	<script>
		$(function(){
			$(".neko_next").KNResponsiveTogglePanel();
		});
	</script>

### (3) HTMLの編集

下記のコードを記述します。セレクタで指定した要素をボタンとし、セレクタの次の要素が開閉できるようになります。

	<div class="neko_next">click</div>
	<ul>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
	</ul>

以上が基本の使い方となります。

## オプション（Options）

(2)の手順「jquery.KNResponsiveTogglePanelの初期設定」で記述したコードでは、初期設定としてセレクタの次の要素を開閉できるようになります。セレクタの次の要素以外に、セレクタの前の要素、セレクタの子要素を開閉できるオプションを用意しています。

### 前の要素を開閉する

#### jquery.KNResponsiveTogglePanelの初期設定

	<script>
		$(function(){
			$(".neko_next").KNResponsiveTogglePanel({
				position : 'prev'
			});
		});
	</script>

#### HTML記述例

	<ul>
		<li>bbb</li>
		<li>bbb</li>
		<li>bbb</li>
		<li>bbb</li>
		<li>bbb</li>
	</ul>
	<div class="neko_prev">click</div>

上記のコードの例では、クラス neko_prev の前の要素 \<ul>〜\</ul> が開閉できるようになります。

### 子要素を開閉する

#### jquery.KNResponsiveTogglePanelの初期設定

	<script>
		$(function(){
			$(".neko_next").KNResponsiveTogglePanel({
				position : 'children'
			});
		});
	</script>

#### HTML記述例

	<ul>
		<li class="neko_child">click
			<ul>
				<li><a href="">ddd</a></li>
				<li><a href="">ddd</a></li>
				<li><a href="">ddd</a></li>
				<li><a href="">ddd</a></li>
				<li><a href="">ddd</a></li>
			</ul>
		</li>
		<li>ccc</li>
		<li>ccc</li>
		<li>ccc</li>
		<li>ccc</li>
		<li>ccc</li>
	</ul>

上記のコードの例では、クラス neko_child の子要素 \<ul>〜\</ul> が開閉できるようになります。

### ボタン要素にテキスト（文字）を設定

#### jquery.KNResponsiveTogglePanelの初期設定

	<script>
		$(function(){
			$(".neko_label").KNResponsiveTogglePanel({
				closeLabel : '閉める',
				openLabel : '開く'
			});
		});
	</script>

#### HTML記述例

	<div class="button neko_label">click</div>
	<ul>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
	</ul>

上記のコードの例では、クラス neko_label の要素 click が「開く」に変わります。クリックして開いた時には「閉じる」となります。オプション値である closeLabel , openLabel を使用する場合はセレクタの中の要素は上書きされます。

### ボタン要素に画像を設定

#### jquery.KNResponsiveTogglePanelの初期設定

	<script>
		$(function(){
			$(".neko_labelImg").KNResponsiveTogglePanel({
				closeLabel : '<img src="close.png">',
				openLabel : '<img src="open.png">'
			});
		});
	</script>

#### HTML記述例

	<div class="button neko_labelImg"></div>
	<ul>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
		<li>aaa</li>
	</ul>

オプション値である closeLabel , openLabel にimg要素（HTMLタグ）を記述する事で画像を使用する事もできます。

### Demo

次のURLではDemoページをご用意しております。複数設置、リストの段階式な開閉、画像ボタンなども実現しています。参考程度にご覧ください。

jquery.KNResponsiveTogglePanel Demo  
[http://www.chara-de-nakata.com/dl/js/jquery.KNResponsiveTogglePanel-master/sample.html](http://www.chara-de-nakata.com/dl/js/jquery.KNResponsiveTogglePanel-master/sample.html)