
/*宣言みたいなもの*/
@charset "utf-8";

/* bodyがセレクタ（htmlの要素から＜＞を取ったもの）。{}の中が宣言 */
/* セレクタ＝スタイルを変更する要素。宣言＝スタイルの見た目をどうしたいか */
body{
    background-color: red;
}

p {
    color: blue;
}

/* cssの色指定方法は3つ */
body{
    /* 色名 */
    color: red;
    /* 16進数 */
    color: #FF0000;
    /* RGB */
    columns: rgb(000,00,0);

    /* RGBAにすると透明度が追加される。透明度を付けたい場合はRGBAしかない。 */
    color: rgba(163, 54, 15, 0.604);
}

/* ulタグのリストマークを変更する */
ul{
    /* 黒丸 */
    list-style-type: disc; 
    /* 黒四角 */
    list-style-type: square;
    /* 白丸 */
    list-style-type: circle;
    /* なし */
    list-style-type: none
}

/* idセレクタ */
/* 一つのhtmlファイルには一つだけid属性を記載できる。その要素に適応するcss。 */
/* cssは#で始める */
html
<p id=abc> text </p>

#abc{
    font-size: 18px;
}

/* classセレクタ */
/* classは複数使える */
/* cssは.で始める */
html
<p class=def> text </p>

.def{
    font-size: 18px;
}

/* プロパティはかなり数がある */
p {
    /* 色 */
    color: red;
    /* 背景色 */
    background-color: red;
    /* 太字 */
    font-weight: bold;
    /* 余白 */
    margin-top: 20px;
    /* 文字サイズ */
    font-size: 30px;
    /* 幅 */
    /* %にしたらデバイスの幅いっぱいに変更して表示する */
    width: 1001px;
    /* 高さ */
    height: 100px;
    /* 行間 */
    line-height: 2;
    /* テキストの冒頭に全角１文字分のインデントをつけるプロパティ。単位はem。 */
    text-indent: 1em;

}


/* ショートハンド */
p{
    margin-top: 20px;
    margin-right: 20px;
    margin-bottom: 20px;
    margin-left: 20px;
    /* 上記は1行にまとめることができる */
    /* tpo,right,bottom,left */
    margin: 20px 20px 20px 20px;
    /* top, */

    /* 下記を */
    background-color: blue;
    background-repeat: no-repeat;
    /* こう */
    background: url("./css.md") blue no-repeat;


}

p{
    
}

/* 関数 */
div{
    /* 常に横幅100%から50px引いた分だけ適応するなど、値が違う物同士で演算ができるcalc関数。 */
    width: calc(100% - 50px);

    /* urlに画像名を入れると画像が表示できるようになるurl関数。 */
    background-image: url(""./001-oooooo.png"");

    /* X軸とY軸を指定して要素を動かすtaranslate関数。 */
    /* 下記の場合、X軸方向に-100px、Y軸方向に30px動かしている。 */
    transform: translate(-100px, 30px);

    /* 回転させるrotate関数。単位はdeg */
    transform: rotate(90deg)
    /* ゆがませるskew関数 */
    transform: skew(90deg)
}

/* 疑似クラスセレクタ */
/* :hover=マウスカーソルをあてた時だけcssをあてる。他にもいろいろある。 */
a:hover{
    color: red;
}

/* 子孫セレクタと子セレクタ */
<p>text text text text text text text </p>
<div class="parent">
    <div>
        <div>
            <p>text</p>
        </div>
    </div>
</div>

/* 子孫セレクタ */
/* このcssの場合、class=parentの中のpタグのtextにcssがあたる */
.parent p {
    color: red;
}
/* 子セレクタ */
.parent > p {
    color: red;
}
/* 親要素の直下にある<p>にcssがあたる。そのため上記のhtmlでは動かない */
<p>text text text text text text text </p>
<div class="parent">
    <p>text</p>（子セレクタ）
    <div>
        <div>
            <p>text</p>（子孫セレクタ）
        </div>
    </div>
</div>
/* 上記の記述で動く */

/* 複数のセレクタに同時にあてたいとき */
<p>text text text text text text text </p>
<div class="parent">
    <p>text</p>（子セレクタ）
    <div>
        <div>
            <p>text</p>（子孫セレクタ）
        </div>
    </div>
</div>
<div class="abc">text</div>
<div class="def">text</div>
<a href="">link</a>

/* カンマで区切ることで複数のセレクタにあてることができる */
/* カンマで区切らなかった場合は両方の鞍数が揃った時にスタイルすることになる。 */
.abc, .def{
    width: 30px;
    background-color: blue;
}

/* +でつなぐとそのクラスの隣のクラスにcssをあてることになる */
.abc + a{
    background-color: red;
}

.abc{
    color: red;
}

h1 .headline{
    color: red;
}

.abc > p {
    color: red;
}

.abc p + p {
    color:  red;
}

.abc a:hover{
    color:  red;
}
