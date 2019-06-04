# SU120で作るOne Board Keypad

## 必要なパーツ
<!--- Bill Of Materials -->
| 名前 | 数 | 備考 | 
|:-|:-|:-|
| SU120 PCB | 1枚 | [入手方法](../common/pcb_order_guide.md) |
| Pro Micro | 1個 | スルーホールをZigzag仕様にしてあるのでコンスルーではなく普通の付属ピンヘッダを使います |
| 4本足のタクトスイッチ | 1個 | |
| ダイオード 1N4148 | 19個 | 表面実装タイプも可 |
| LEDテープ | お好みの長さ | WS2812Bを使用したもの |
| Kailh PCBソケット CherryMX用 または Choc用 | 19個 | あとで違うスイッチを試せるように両方付けておくこともできます|
| 5ピン仕様のキースイッチ CherryMX用 または Choc用 | 19個 | トッププレートがないので3ピン仕様だとガタガタになります |
| キーキャップ CherryMX用 または Choc用 | 19個 | 17個は1U、1個は1U～2.25U、1個は1U～2.75U |
| スタビライザー 2U用 | 2個 | PCBマウントのもの 2Uサイズ以上のキーキャップを付ける場合にお好みで |
| クッションゴム | 4個以上 | たわみが気になれば増やしてください 適当なものが見つからなければとりあえず100円ショップの滑り止めシートを敷いても |
| Micro USBケーブル | 1本 | |

## 使用する道具類

[SU120で使用する道具、消耗品](../common/tool_guide_jp.md)を参照ください。

## ビルドガイド

### Pro Microのもげ防止加工

エポキシ接着剤でもげ防止加工を施します。

参考:[ProMicroのモゲ防止ついでにQMK_Firmwareを書き込む - Qiita](https://qiita.com/hdbx/items/2f3e4ddfcadda2a5578e)

エポキシ接着剤の2液を混ぜます。つまようじを用意します。

![adhesive_prepare](adhesive_prepare.jpg)

Micro USBコネクタの側面には穴が開いています。この穴に接着剤が入ると端子が入らなかったり、入りにくくなってしまったりします。

![usb_side_hole](usb_side_hole.jpg)

この穴を避けて、つまようじで接着剤を付けていきます。

![promicro_pate](promicro_pate.jpg)

乾くまで置いておきます。


### ダイオードの取り付け

19箇所にダイオードを配置します。

基板の表と裏、どちら側に付けても構いません。
なお、キースイッチを配置する枠が描いてあるほうが表で、Kailh PCBソケットを配置する枠が描いてあるほうが裏です。

はじめに1つだけダイオードを曲げて穴に差し込んでみて、うまくいく曲げ具合を見つけて残りのダイオードを同じように曲げておくとやりやすいです。

![diode_bent](diode_bent.jpg)

ダイオードの黒くなっている側が、基板の図の二重線の側になるように差し込みます。

![diode_inserted](diode_inserted.jpg)

全てのダイオードを配置した後、マスキングテープで浮かないようにカバーしておきます。

![diode_taped](diode_taped.jpg)

基板を裏返して全てハンダ付けします。

![diode_soldered](diode_soldered.jpg)

ハンダから飛び出ている線を切ります。

### PCBソケットの取り付け

基板の裏の枠に合うようにPCBソケットを配置します。
CherryMX用のPCBソケットを置く場合は、間違った向きに置かないように注意してください。間違った向きに取り付けるとあとでキースイッチが入りません。

![socket_attached](socket_attached.jpg)
![socket_attached_all](socket_attached_all.jpg)

PCBソケット両端の金属部分をハンダ付けします。

![socket_soldered](socket_soldered.jpg)

### TRRSコネクタの取り付け

基板の表側の枠に合うようにTRRSコネクタを配置します。

![trrs_jack_attached](trrs_jack_attached.jpg)

裏返して金属部分をハンダ付けします。

![trrs_jack_attached](trrs_jack_attached.jpg)

### タクトスイッチの取り付け

基板の表側の枠に合うようにタクトスイッチを配置します。

裏返して金属部分をハンダ付けします。

### Pro Microの取り付け

基板の表側のPro Micro設置部分の2箇所に、Pro Microに付属している12ピンのピンヘッダの短い側を差し込みます。

![pin_header_attaching](pin_header_attaching.jpg)

スルーホールがジグザグになっているので、少し入れにくくなっています。ゆっくり押し込んでください。

基板とピンヘッダはジグザグのスルーホールで接触しているため、ハンダ付けしません。

ピンヘッダにPro Microを差し込みます。Rev.2以降はPro Microの裏面（平らなほう）が上になるようにします。

Pro Microとピンヘッダをハンダ付けします。

![promicro_soldered](promicro_soldered.jpg)

### スタビライザーの取り付け

![stabilizer_attached](stabilizer_attached.jpg)

基板の都合により、スタビライザーの片側はしっかり留まりません。

![stabilizer_loose](stabilizer_loose.jpg)

試用してみて使い続けられそうなら、エキポシ接着剤で固定するとよいかもしれません。

### キースイッチの取り付け

表側から19箇所に差し込みます。キースイッチの足が曲がっている場合はまっすぐにしてから差し込んでください。

![switch_attached](switch_attached.jpg)


### キーキャップの取り付け

キースイッチにキーキャップをはめます。

![keycap_attached](keycap_attached.jpg)

### ゴム足の取り付け

ゴム足を裏面に取り付けます。試打して基板のたわみが気になればゴム足を増やします。

### ファームウェアの書き込み

[Getting Started - QMK Firmware](https://docs.qmk.fm/#/newbs_getting_started)によりファームウェアを書き込む環境を用意します。

（ここからあとで書く）

