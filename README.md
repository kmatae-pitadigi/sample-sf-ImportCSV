# Salesforce Lightning Web Component Sample

## 概要
SalesforceのLightning Web ComponentでCSVファイルをインポートするサンプル
このサンプルでは、取引先の以下の項目をCSVとして取り込む
* Name
* 住所(請求先)-都道府県

## 役割

### importCSV LWC
* ```lightning-input type="file"```でファイルを選択する
* 選択されたファイルをShift_JIS形式で読み込む
* 改行コードで分割して、１行分ずつをApexクラスの引数に渡す

### importCSV Apex
* 1行分のパラメータを「,」で分割する
* [0]をName、[1]をBillingStateに設定する
* insertする

## 備考
MacのVisualStudio Codeで、Shift_JISのCSVファイルを作成するのに苦戦。
新しいファイルを作成したら、まず形式をShift_JIS、改行をCRLFに変更。CSVデータを書いたら保存する
再び開くと強引にUTF-8で開くので注意。
「"」などをreplaceで変換するときに、文字コードが合っていないと機能しない。

