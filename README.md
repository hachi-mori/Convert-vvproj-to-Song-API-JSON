# Convert-vvproj-to-Song-API-JSON

任意のVOICEVOXプロジェクトファイル（vvproj）をVOICEVOXの歌唱API（frame_synthesis）の仕様に合わせたJSONに変換するツールです。
## 使い方

【オフライン版】
1. アプリを起動します。（DLは[ここから](https://github.com/hachi-mori/Convert-vvproj-to-Song-API-JSON/releases/tag/v1.0)）
2. `🎵 入力ファイルを選択` ボタンをクリックして `.vvproj` ファイルを選択します。
3. `📂 出力フォルダを選択` ボタンをクリックして出力先のフォルダを指定します。
4. `✅ 変換` ボタンをクリックすると、選択された `.vvproj` ファイルが VOICEVOX の歌唱API仕様に対応した `.json` に変換され、出力先フォルダに保存されます。

![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3932802/67e89987-cd38-42b1-8954-ad24160b4ba8.png)

【WEB版】
1. ブラウザで[ページ](https://hachi-mori.github.io/Convert-vvproj-to-Song-API-JSON/)を開きます。
2. `ファイルを選択`ボタンをクリックして、`.vvproj`ファイルを選択します。
3. ファイルが選択されると 「変換してダウンロード」 ボタンが有効になります。
4. 「変換してダウンロード」 をクリックすると、選択された `.vvproj` ファイルが VOICEVOX の歌唱API仕様に対応した `.json` に変換され、ダウンロードされます。
   
![image.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3932802/0bd259df-96cd-4265-8d37-9266c6a9b688.png)

## 動作
この`ドレミ.vvproj`を
```JSON:ドレミ.vvproj
//省略
"notes": [
  {
    "id": "77b5e49d-09e7-4eba-8ea4-ebc71fab5794",
    "position": 0,
    "duration": 480,
    "noteNumber": 60,
    "lyric": "ド"
  },
  {
    "id": "5b1a39fa-203b-465d-a9c4-40bb2db1ecb0",
    "position": 480,
    "duration": 480,
    "noteNumber": 62,
    "lyric": "レ"
  },
  {
    "id": "b75f29cb-3575-47b3-9369-4e048111f4ba",
    "position": 960,
    "duration": 960,
    "noteNumber": 64,
    "lyric": "ミ"
  }
]
//省略
```
`ドレミ.json`（VOICEVOXの歌唱API（frame_synthesis）の仕様に合わせたJSON）に変換します。
```JSON:ドレミ.json
{
  "notes": [
    {
      "frame_length": 2,
      "key": null,
      "lyric": ""
    },
    {
      "frame_length": 47,
      "key": 60,
      "lyric": "ド"
    },
    {
      "frame_length": 47,
      "key": 62,
      "lyric": "レ"
    },
    {
      "frame_length": 94,
      "key": 64,
      "lyric": "ミ"
    }
    {
      "frame_length": 2,
      "key": null,
      "lyric": ""
    },
  ]
}
```
詳しくはQiitaの記事で書きました。
https://qiita.com/hachi_mori_/items/dc0813ad0635dfc8583e

## VOICEVOX
[VOICEVOX | 無料のテキスト読み上げ・歌声合成ソフトウェア](https://voicevox.hiroshiba.jp/)

## 制作
C++フレームワーク [Siv3D](https://siv3d.github.io/ja-jp/)
