# ISO2ch

Chipanalog社のデジタルアイソレータ[CA-IS3642HW](https://www.lcsc.com/product-detail/Digital-Isolators-with-power_Chipanalog-CA-IS3642HW_C2890053.html)を使った2チャンネルのデジタルアイソレータです。電源と2本のデジタル信号線を電気的に絶縁（分離）することができます。使用しているCA-1364の仕様上、直流から150MHzまでのデジタル信号を伝送できます。

入出力はGroveコネクタで、出力側の電源電圧は5Vと3.3Vから選択でき、また2本のデジタル信号の向きを変更することができます。

<img src="https://github.com/akita11/ISO2Ch/blob/main/ISO2Ch.jpg" width="240px">


## 基本的な使い方

<img src="https://github.com/akita11/ISO2Ch/blob/main/ISO2Ch-f.jpg" width="240px">

<img src="https://github.com/akita11/ISO2Ch/blob/main/ISO2Ch-b.jpg" width="240px">

裏面で、2つのGroveコネクタの種別を確認します。一方が電源の給電側、もう1方が電源の受電側です。
給電側のGroveコネクタに、電源を供給する側の機器（M5Stack等）を接続します。
受電側のGroveコネクタに、電源を受ける側の機器（センサ等）を接続します。受電側には5Vの電源（または3.3Vにも設定可能）が供給されます。

Groveコネクタの2本の信号線の信号（デジタル信号）の向きは、初期状態では2本とも「給電側＝入力／受電側＝出力」となっています。なお入力信号が未接続のときは出力側は"H"となります。（信号の向き後述のように半田ジャンパで変更できます）※仕様上、I2Cのように双方向の通信が必要な場合には使用できません

給電側・受電側のGroveコネクタのピン配置は以下のとおりです。

- 1: B (デジタル信号線1)
- 2: A (デジタル信号線2)
- 3: VDD
- 4: GND


## 設定変更の方法

### 受電側の電源電圧

表面のJP5で、受電側の電源電圧を設定できます。

<img src="https://github.com/akita11/ISO2Ch/blob/main/ISO2Ch-f2.jpg" width="240px">

- 中央-△マークのある側をショート（初期状態）: 5V
- 中央-△マークのない側をショート: 3.3V （※中央-△マークのある側の基板パターンをカットしてください）


### デジタル信号の方向

裏面のJP1/2/3/4で、2本のデジタル信号線の信号の向きを設定できます。

<img src="https://github.com/akita11/ISO2Ch/blob/main/ISO2Ch-b2.jpg" width="240px">

- B（デジタル信号線1）
 - JP1とJP4の中央-△マークのある側をショート（初期状態）：給電側＝入力、受電側＝出力
 - JP1とJP4の中央-△マークのない側をショート：給電側＝出力、受電側＝入力（※中央-△マークのある側の基板パターンをカットしてください）

- A（デジタル信号線2）
 - JP2とJP3の中央-△マークのある側をショート（初期状態）：給電側＝入力、受電側＝出力
 - JP2とJP3の中央-△マークのない側をショート：給電側＝出力、受電側＝入力（※中央-△マークのある側の基板パターンをカットしてください）


## Author

Junichi Akita (@akita11, akita@ifdl.jp)
