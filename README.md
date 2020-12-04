# robosystem1

LEDを点灯させるデバイスドライバーでコマンド入力をするとLEDが点灯したり消灯するプログラムを書きました。

## 使用した材料
-  LED×３
- 抵抗（１００Ω）×３
- ジャンパ線（オスーメス）
-  ブレッドボード

## 環境
- ソフトウェア
Raspberry Pi4 MOdelB
- ハードウェア
ubuntu 18.04

## 使用した回路
gpio23,24,25にLEDのアノードをつなぎ、GNDには抵抗とLEDのカソードと順番にそれぞれつなぐ。

## 使い方
以下のコマンドを順番に入力していく。
```
$git clone https://github.com/keita8723/robosystem1.git
$make
$sudo insmod myled.ko
$sudo chmod 666 /dev/myled0
```
- LED３個を点灯させる。
```
$echo 1 > /dev/myled0 
```
- LED２個を点灯させる。
```
$echo 2 > /dev/myled0 
$echo 3 > /dev/myled0 
```
- LED１個を点灯させる。
```
$echo 4 > /dev/myled0 
```
- LEDを消灯させる。
```
$echo 0 > /dev/myled0 
```
- カーネルモジュールをアンインストールする場合
```
$sudo rmmod myled
```
## ライセンス
このリポジトリはGPLv3である。

