# Eink 11.6
## Overview
[Goodisplay GDEY116F91](https://www.good-display.com/product/447.html)で利用できる，任意の画像を表示するための変換スクリプト，および表示するサンプルコードです．`ESP32`上で動作しますが，他のサンプルを利用することで，`STM32`や`Arduino`などでも動作可能です．[Goodisplay公式サンプル](https://github.com/gooddisplayshare/ESP32epdx)を利用しています．

![cat_img](doc/cat.png)

## Prerequisites
[GIMP](https://www.gimp.org/)などを利用して，あらかじめ画像を白黄赤黒の4色のインデックスカラーに変換しておきます．スクリプトを動かすため，依存関係をインストールします．

### Windows
```sh
python -m venv .venv
.venv/Scripts/activate
pip install -r requirements.txt
```

### Linux/Mac
```sh
python3 -m venv .venv
.venv/bin/activate
pip3 install -r requirements.txt
```

コンパイルおよび書き込みのため`Arduino IDE`を利用します．ボードマネージャで`ESP32`のインストール，および，ライブラリマネージャで`ESP32epdx`をインストールします．

## Usage
スクリプトを使用してC配列に変換します．配列変数名，幅，高さも引数により変更可能ですが，特にいじる必要はありません．それぞれデフォルトで`gImage_1`，`960`，`640`となっています．また出力ファイル名を変更する場合は，`.ino`内で`IMAGE.h`のインクルードを消し，新たに出力ファイルをインクルードする必要があります．
### Windows
```sh
python img_to_epd.py [input.png] [output.h] [var_name(option)] [width(option)] [hight(option)]
```

例：
```sh
python img_to_epd.py apple.png IMAGE.h
```

### Linux/Mac
```sh
python3 img_to_epd.py [input.png] [output.h] [var_name(option)] [width(option)] [hight(option)]
```

例：
```sh
python3 img_to_epd.py lemon.png IMAGE.h
```

## License
**Eink11.6** is licensed under the MIT License (see LICENSE).
