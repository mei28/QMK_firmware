QMK_firmware

# キーマップの変更手順

-  QMK Firmwareをcloneする
- QMK Firmwareのビルド環境を整える
- Mint60のデフォルトのキーマップを確認する
- Mint60のデフォルトのキーマップをコピーして、カスタムのキーマップを定義する
- Mint60のカスタムのキーマップのファームウェアをビルドする
- 左右のProMicroにファームウェアを焼く

## QMK Firmwareをcloneする

 ```
$ git clone https://github.com/qmk/qmk_firmware
$ cd qmk_firmware
 ```

 ## ビルド環境を整える

 ```
 $ ./util/qmk_install.sh

 ```

 ## キーマップが置いてある場所

 ```
 $ ls keyboards/mint60/keymaps
 ```

 ## キーマップを変更する場所
 
 ```
 keyboards/mint60/keymaps/hogehoge/keymap.c
 ```

 - keymap.c の内容を書き換えるとキーマップを変更することができる．
 - マクロの定義はtmk_core/common/keycode.hの中にある．

## キーマップのビルド

```
$ make mint60:hogehoge
```

## ProMicro にファームウェアを焼く

```
$ make mint60:custom:avrdude
```

- 実行後にデバイスを探し始めたらデバイスのリセットボタンを押して焼き始まる．