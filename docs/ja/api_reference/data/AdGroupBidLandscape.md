# AdGroupBidLandscape
AdGroupBidLandscapeオブジェクトは、広告グループに関する予測の結果を表します。
### Service
+ [BidLandscapeService](../services/BidLandscapeService.md)

| フィールド | データ型 | 説明 | 
|---|---|---|
| BidLandscape (inherited)|||
| campaignId| xsd:long| キャンペーンIDです。 |
| adGroupId| xsd:long| 広告グループIDです。 |
| startDate| xsd:string| 開始日です。 |
| endDate| xsd:string| 終了日です。 |
| landscapePoints[]| <a href="./LandscapePoints.md">LandscapePoints</a>| ランドスケープ点のリストです。 |
| BidLandscape.Type| xsd:string| ランドスケープのサブタイプを示します。 |
| AdGroupBidLandscape|||
| type| xsd:string| AdGroupLandscapeのタイプを示します。<br>UNIFORM: デフォルトの入札単価があらゆるクライテリアに適用されることを示します。<br>DEFAULT: クライテリアの入札単価がデフォルトの入札単価をオーバーライドすることを示します。<br>UNKNOWN: 不明です。|
| landscapeCurrent| boolean| 「LandscapeCurrent」の値を選択します。 |
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
