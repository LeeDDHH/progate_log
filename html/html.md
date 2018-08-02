# HTML

## トップ部分で左右にのびる背景画像をおきたい
```
<!--css-->
.top {
  margin: 0 auto;
}

.top .top-img {
  padding: 500px 0 500px 0;//余白は各自
  background: url("../hope2.jpg");
  background-size: cover;
}

<!--html-->
<div class="top">
	<div class="top-img"></div>
</div>
```
