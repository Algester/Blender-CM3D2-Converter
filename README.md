# Blender-CM3D2-Converter
　3Dアダルトゲーム「カスタムメイド3D2」で使用されるモデルファイル形式(.model)を  
　フリー3D統合環境である「Blender」で扱うためのアドオンです。  

## インストール (Installation)
　まず、Blender 2.7以上がインストールされており日本語化している事が前提です。  
　画面右の「Download ZIP」からファイルをダウンロード・解凍し、  
　Windows7なら「C:\Users\ユーザー名\AppData\Roaming\Blender Foundation\  
　Blender\2.75\scripts\addons\CM3D2 Converter\～.py」となるように配置してください。  
　![配置](http://i.imgur.com/QvbMDR1.jpg)  
　Blenderを起動しユーザー設定のアドオンタブで「cm3d」等で検索、  
　「Import-Export: CM3D2 Converter」をオンにすれば一時的に有効になります。  
　次回起動時からも有効にしておきたい場合は「ユーザー設定の保存」をクリックして下さい。  
　![有効化](http://i.imgur.com/6jmFWxQ.jpg)  
　一度インストールしてしまえば、アドオン設定画面からアップデート可能です。  
　![更新](http://i.imgur.com/4jQ358Q.jpg)  

## 使い方 (How to Use)
　読み込みは  
　ファイル => インポート => CM3D2 Model (.model)  
　書き出しも同じように  
　ファイル => エクスポート => CM3D2 Model (.model)  
　![手順](http://i.imgur.com/p2V7D5m.jpg)  

## メモ (Note)

### ボーン
　ボーン情報は「BoneData」と「LocalBoneData」というテキストデータ、  
　![テキスト](http://i.imgur.com/pvgSZy5.jpg)  
　もしくは、オブジェクトかアーマチュアデータ内のカスタムプロパティに保存されています。  
　![カスタムプロパティ](http://i.imgur.com/HHzvdAK.jpg)  
　テキストならボーン情報を編集しやすく、カスタムプロパティなら  
　1つのblendファイルに複数のボーン情報を保持できるというメリットがあります。  
　これらを編集すればボーン設定を変更することも可能ですが、慣れない内は変えない事をおすすめします。  
　エクスポート時にどれを参照するかを選ぶ事が可能です。  

### オブジェクト
　オブジェクト名は必ず「name.bone」のように、「.(ピリオド)」で区切った形式にして下さい。  
　前半がmodel名、後半がメッシュの位置のベースになるボーンの名前です。  
　![オブジェクト名エラー](http://i.imgur.com/lnLydVO.jpg)  

### メッシュ
　四角ポリゴンがあっても自動で三角ポリゴンに変換して出力しますが、手動で三角化した方が綺麗です。  
　ウェイト値の合計が1.0でなくても、エクスポート時に自動的に調整します。  
　ウェイトの数が5つ以上でも、自動的に割り当てが大きい順で4つ選ばれます。  

### マテリアル
　マテリアル情報は、マテリアルとテクスチャと画像の設定値によって保管しています。  
　シェーダー(CM3D2/Toony_Lighted_Outlineなど)は、  
　マテリアルのカスタムプロパティ「shader1」「shader2」で変更可能です。  
　![カスタムプロパティ](http://i.imgur.com/5fFEcw9.jpg)  
　  
　またマテリアル情報をテキストでも保管しているので(名前は「Material:0」等)、出力時にオプションを変えれば  
　そちらを参照する事も可能です。自分が編集しやすい方を活用して下さい。  
　  
　インポート時にマテリアルに色がつきますが、エクスポート時には関係ありません。  

### テクスチャ
　　![テクスチャ群](http://i.imgur.com/UNerNpl.jpg)  
#### 　テクスチャが有効
　　「tex」タイプの設定値です、「テクスチャ名」「画像名」  
　　「画像のパス」「デフォルトカラー」「カラー強度」などで変更。
#### 　テクスチャが無効で、「RGBを強度に変換」が有効
　　「col」タイプの設定値です、「テクスチャ名」「デフォルトカラー」「カラー強度」などで変更。
#### 　テクスチャが無効で、「RGBを強度に変換」が無効
　　「f」タイプの設定値です、「テクスチャ名」「カラー強度」などで変更。  
　　![テクスチャ設定](http://i.imgur.com/6WuW6jI.jpg)  

### その他
　元の.modelに上書きする必要はありません。  
　データ名が「○○.001」のように末尾に連番が付いていても自動的に削除されます。  

## 規約 (Agreement)
>・「カスタムメイド3D2」本体を正規にご購入頂いた方のみが作成・配布・利用することができます。  
>・「カスタムメイド3D2」上で表示する目的以外にツールの利用やデータの配布をすることはできません。  

>・MODデータや製作に関連する事柄に対して直接的な対価を得ることは禁止致します。  
>　Q.製作したMODデータをDLや即売会などで販売する。→不許可。  
>　Q.MOD製作を○○円で依頼する・受ける。→不許可。  

>・配布する場合は、利用者が目にする箇所に以下の記述を追記して下さい  
>　「MODはKISSサポート対象外です。」  
>　「MODを利用するに当たり、問題が発生しても製作者・KISSは一切の責任を負いかねます。」  
>　「カスタムメイド3D2を購入されている方のみが利用できます。」  
>　「カスタムメイド3D2上で表示する目的以外の利用は禁止します。」  
>　「カスタムメイド3D2」本体を正規にご購入頂いた方のみが作成・配布・利用することができます。  
>　「カスタムメイド3D2」上で表示する目的以外にツールの利用やデータの配布・利用をすることはできません。  
