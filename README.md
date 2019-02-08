# cptemp
competitive programming template

---

## おしながき  

### マクロ  
`int`は`long long`です．  

#### ループ系
repマクロあります．  
`REP(i,l,r)`は`for(int i = l;i < r;i++)`と等価です．  
`rep(i,n)`はf`for(int i = 0;i < n;i++)`と等価です．  
reverse方向のfor文が書きたい場合は`REPEAT()`マクロを使ってください．  
`REPEAT(i,l,r,cond)`マクロは`cond`が`false`の場合に，逆向きにループします．  
```cpp
rep(y,height){
    REPEAT(x,0,width,y%2==0){
        //dosomething
    }
}
```
のように書くことで「己」のような動き方で二次元空間を移動します．  

#### 短縮系
`all(e)`，`rall(e)`あります．  
`pb = push_back`，`fs = first`，`sc = second`あります．  

#### デバッグ系
`show(...)`関数があります．  
標準エラー出力に変数名、値を出します． vectorは直接受け取れます．  
`showlr(n,l,r)`関数はvectorの後半がまだ未使用で0だらけの時などにお使いください．  
[l, r)の空間のforループで順番に出力します．

#### 出力系
`YN(condition)`関数は`condition`が`true`の時に`"YES"`，`false`の時に`"NO"`を出力します．  
`Yn(condition)`は`"Yes" "No"`を出力．  
`yn(condition)`は`"yes" "no"`を出力．  
condなんかいらんわ！という時用に`YES` `Yes` `yes` `NO` `No` `no`でそれぞれの文字列を出力します．  
`case(i)`はCase番号の出力が必要な時に適宜どうぞ．

---
### 型
`vector<int>`は`vi`です．  
`pair<int, int>`は`pint`です．  

---
### 関数
~~`io()`関数にio高速化一式，coutの小数値出力桁数変更が入っています．~~  
構造体にio高速化一式を入れたので，呼ばなくても呼ばれるように(は？)なりました．  

`in(...)`関数に変数を渡すと標準入力から値を取ってきます．  
可変長引数対応なのでいくつでも渡せます．  
vectorも直接渡せます．

```
A B C
```
のような時に
```cpp
int a,b,c;
in(a,b,c);
```
や，
```
n
a_1 a_2 ... a_n
```
のような時に
```cpp
int n;
in(n);
vi v(n);
in(v);
```

といった感じです．

`out(...)`関数で標準出力を行えます．  
可変長引数対応で，それぞれの変数間は半角スペースが入ります．
vectorの出力フォーマットは`{elem, elem, elem}`です
```cpp
int n=3, a=5, b=2;
vi vec={2,4,6};
out(n,a,b);
out(vec);
```
```
3 5 2
{2, 4, 6}
```
のような出力になります．

`resz(n, ...)`関数で複数のvectorのsizeを同時にresize出来ます．  
```cpp
int n;
vi a, b, c;

in(n);
resz(n, a, b, c);
```
みたいな利用想定．  

`resize(v, ...)`関数で多次元vectorについて一気にresizeできます．(コンストラクタで頭こわれる人向け)  
```cpp
vector<vector<vi>> dp;
resize(dp, 100, 5, 3);
```
みたいな利用想定．  

---
### 定数
デフォルトでは，  
`INF`は`2^55`です．  
`MOD`は`1e9+7`です．  
`EPS`は`1e-8`です．  
問題に合わせて適宜変えてください．
