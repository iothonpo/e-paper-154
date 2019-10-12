# e-paper-154

## 説明
電子ペーパーモジュールをPythonでRaspberry Piから制御するサンプルプログラムです。

## 必要要件
- Python3
- SPI通信
- 5Vもしくは3.3VのGPIO

## 使い方
ラズパイと電子ペーパーモジュールを状態した状態で`test.py`を実行します。
黒単色版は`1.54-black-white`、赤黒の２色版は`1.54-red`です。

```
cd ./e-paper-154/1.54-red/
python3 test.py
```

## インストール
raspi-configでSPIを有効化します。
```
sudo raspi-config
# メニューから[5 Interfacing Options] > [P4 SPI]を選択して有効化
```

Pythonの画像処理ライブラリ`python3-pil`をインストールします。
```
sudo apt install python3-pil
```

電子ペーパーモジュールのサンプルプログラムを`e-paper-154`にまとめています。
```
git clone https://github.com/harukaze-co/e-paper-154
```

ラズパイと電子ペーパーモジュールの各ピンを下表の通り接続します。

| e-Paper | BCM番号 | 物理ピン |
|---------|---------|----------|
| VCC | 3.3V | 3.3V |
| GND | GND | GND |
| DIN | MOSI | 19 |
| CLK | SCLK | 23 |
| CS | CE0 | 24 |
| DC | 25 | 22 |
| RST | 17 | 11 |
| BUSY | 24 | 18 |

##  解説
より詳しい情報は[電子ペーパーをラズパイからPythonで制御する方法](https://hrkz.tokyo/e-ink-ctrl-rpi/)をご覧ください。
