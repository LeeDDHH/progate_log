# Sass

- [Intro](#intro)
- [Merit](#merit)
- [Nest](#nest)
- [&:](#andmark)
- [mixin](#mixin)
- [function](#function)
- [import](#import)

## Intro
- Sassとはcssをより便利に使うための一つの記法
- Sass,Scssがある

## Merit
- 記述量が減る
- 再利用できる（割と重要）

## Nest
```
.header {
	width:100%;
}

.header div {
	padding:15px;
}

.header div p {
        margin:10px;

}
```
↓

```
.header {
	width:100%
	
	div {
		padding:15px;
		p {
			margin:10px;
		}
	}
}
```
こんな感じ

## Andmark
### &を使うとセレクタも入れ子の中で使える

&は__親セレクタ参照__を意味する

```
.btn {
	display:inline-block;
	opacity:0.8;
	box-shadow:0 5px #e04893;

	&:hover {
		opacity:1;
	}

	&:active {
		position:relative;
		top:7px;
		box-shadow:none;
	}
}
```
### 要素内のcss指定

```
div {
	display:block;
	
	&.pikachu{
		background-color:yellow;
		color:red;
	}
}
```
## variable
変数として値を定義できる

```
$変数名:値;
```

ただし、変数の宣言よりまえに使うのはできない

```
+ $pikachu-color:yellow;

+ .pikachu {
+ 	background-color:$pikachu-color;
+ }

- .fushigidane {
- 	background-color:$fushigidane-color;
- }

- $fushigidane-color:green;
```

## mixin
### mixin定義と呼び出し
複数の箇所で同じCSS定義を使い回せる

- @mixin mixin名で定義
- @include mixin名で呼び出せる

```
@mixin monster-ball {
	width:400px;
	height:400px;
}

.satoshi {
	@include monster-ball;
}

.takeshi {
	@include monster-ball;
}

```

### mixinと引数
引数指定でクラスごとに異なる設定もできる

```
@mixin character-color($color) {
        width:400px;
        height:400px;
	background-color:$color;
}

.satoshi {
        @include character-color(red);
}

.takeshi {
        @include character-color(gray);
}

```

## Function
色、文字列、リストなど様々
「sass 組み込み関数」で検索するといい

```
.monsterball1 {
	background-color:darken(red,10%);
}

monsterball2 {
        background-color:lighten(blue,20%);
}
```

## Import
外部ファイルを読み込む際→　_(アンダーバー)を先頭に付けたファイル名である必要あり
ファイル名さえちゃんとしていれば、呼び出す際に_(アンダーバー)と拡張子なしでも呼べる

```
@import "_variables.scss";
@import "variables";
//どちらかを使ってOK

```

