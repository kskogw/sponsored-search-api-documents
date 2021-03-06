# DictionaryService
DictionaryServiceは、審査否認理由と地域情報の一覧を提供します。
#### WSDL
| environment | url |
|---|---|
| production  | https://ss.yahooapis.jp/services/Vx.x/DictionaryService?wsdl|
| sandbox  | https://sandbox.ss.yahooapis.jp/services/Vx.x/DictionaryService?wsdl|
#### Namespace
http://ss.yahooapis.jp/V6
#### サービス概要
EditorialReasonの一覧を提供します。
#### 操作
DictionaryServiceで提供される操作を説明します。
## getDisapprovalReason

EditorialReasonと推奨する対応方法の一覧を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [DisapprovalReasonSelector](../data/DisapprovalReasonSelector.md) | 取得するEditorialReason一覧の言語を指定します。 | 
＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDisapprovalReason>
            <ns1:selector>
                <ns1:lang>JA</ns1:lang>
            </ns1:selector>
        </ns1:getDisapprovalReason>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getDisapprovalReason>
            <ns1:selector>
                <ns1:lang>JA</ns1:lang>
            </ns1:selector>
        </ns1:getDisapprovalReason>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [DisapprovalReasonPage](../data/DisapprovalReasonPage.md) | EditorialReason一覧です。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:ResponseHeader>
            <ns1:service>DictionaryService</ns1:service>
            <ns1:remainingQuota>100</ns1:remainingQuota>
            <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
            <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
        </ns1:ResponseHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
    <ns1:getDisapprovalReasonResponse>
            <ns1:rval>
                <ns1:totalNumEntries>3</ns1:totalNumEntries>
                <ns1:Page.Type>DisapprovalReasonPage</ns1:Page.Type>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:disapprovalReason>
                        <ns1:disapprovalReasonCode>1<ns1:disapprovalReasonCode>
                        <ns1:lang>JA<ns1:lang>
                        <ns1:title>disapprovalReasonタイトル<ns1:title>
                        <ns1:description>disapprovalReason説明<ns1:description>
                        <ns1:recommend>対処方法<ns1:recommend>
                    </ns1:disapprovalReason>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:disapprovalReason>
                        <ns1:desapprovalReasonCode>2<ns1:disapprovalReasonCode>
                        <ns1:lang>JA<ns1:lang>
                        <ns1:title>disapprovalReasonタイトル2<ns1:title>
                        <ns1:description>disapprovalReason説明2<ns1:description>
                        <ns1:recommend>対処方法2<ns1:recommend>
                    </ns1:disapprovalReason>
                </ns1:values>
                <ns1:values>
                    <ns1:operationSucceeded>true</ns1:operationSucceeded>
                    <ns1:disapprovalReason>
                        <ns1:disapprovalReasonCode>3<ns1:disapprovalReasonCode>
                        <ns1:lang>JA<ns1:lang>
                        <ns1:title>disapprovalReasonタイトル3<ns1:title>
                        <ns1:description>disapprovalReason説明3<ns1:description>
                        <ns1:recommend>対処方法3<ns1:recommend>
                    </ns1:disapprovalReason>
                </ns1:values>
            </ns1:rval>
    </ns1:getDisapprovalReasonResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
## getGeographicLocation

地域情報の一覧を取得します。

### リクエスト
| パラメータ | 必須 | データ型 | 説明 | 
|---|---|---|---|
| selector | ○ | [GeographicLocationSelector](../data/GeographicLocationSelector.md) | 取得する地域情報一覧の言語を指定します。 | 
＜リクエストサンプル＞（標準認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getGeographicLocation>
            <ns1:selector>
                <ns1:lang>JA</ns1:lang>
            </ns1:selector>
        </ns1:getGeographicLocation>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

＜リクエストサンプル＞（代行認証）
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope 
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" 
 xmlns:ns1="http://ss.yahooapis.jp/V6">
    <SOAP-ENV:Header>
        <ns1:RequestHeader>
            <ns1:license>xxxx-xxxx-xxxx-xxxx</ns1:license>
            <ns1:apiAccountId>xxxx-xxxx-xxxx-xxxx</ns1:apiAccountId>
            <ns1:apiAccountPassword>passwd</ns1:apiAccountPassword>
            <ns1:accountId>1000000001</ns1:accountId>
            <ns1:onBehalfOfAccountId>xxxxxxxxxxxxxx</ns1:onBehalfOfAccountId>
            <ns1:onBehalfOfPassword>passwd2</ns1:onBehalfOfPassword>
        </ns1:RequestHeader>
    </SOAP-ENV:Header>
    <SOAP-ENV:Body>
        <ns1:getGeographicLocation>
            <ns1:selector>
                <ns1:lang>JA</ns1:lang>
            </ns1:selector>
        </ns1:getGeographicLocation>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### レスポンス
| フィールド | データ型 | 説明 | 
|---|---|---|
| rval | [GeographicLocationPage](../data/GeographicLocationPage.md) | 地域情報の一覧です。 | 
＜レスポンスサンプル＞
```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
 xmlns:ns1="http://ss.yahooapis.jp/V6"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <SOAP-ENV:Header>
    <ns1:ResponseHeader>
      <ns1:service>DictionaryService</ns1:service>
      <ns1:remainingQuota>100</ns1:remainingQuota>
      <ns1:quotaUsedForThisRequest>1</ns1:quotaUsedForThisRequest>
      <ns1:timeTakenMillis>0.0173</ns1:timeTakenMillis>
    </ns1:ResponseHeader>
  </SOAP-ENV:Header>
  <SOAP-ENV:Body>
    <ns1:getGeographicLocationResponse>
      <ns1:rval>
        <ns1:totalNumEntries>47</ns1:totalNumEntries>
        <ns1:Page.Type>GeographicLocationPage</ns1:Page.Type>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:geographicLocation>
            <ns1:code>JP-01</ns1:code>
            <ns1:name>北海道</ns1:name>
            <ns1:fullName>北海道</ns1:fullName>
            <ns1:order>0000000000</ns1:order>
            <ns1:status>ACTIVE</ns1:status>
            <ns1:child>
              <ns1:code>JP-01-0003</ns1:code>
              <ns1:parent>JP-01</ns1:parent>
              <ns1:name>旭川市</ns1:name>
              <ns1:fullName>北海道 旭川市</ns1:fullName>
              <ns1:order>0000000100</ns1:order>
              <ns1:status>ACTIVE</ns1:status>
            </ns1:child>
            <ns1:child>
              <ns1:code>JP-01-0005</ns1:code>
              <ns1:parent>JP-01</ns1:parent>
              <ns1:name>芦別市</ns1:name>
              <ns1:fullName>北海道 芦別市</ns1:fullName>
              <ns1:order>0000000200</ns1:order>
              <ns1:status>ACTIVE</ns1:status>
            </ns1:child>
            <ns1:child>
              <ns1:code>JP-01-0052</ns1:code>
              <ns1:parent>JP-01</ns1:parent>
              <ns1:name>札幌市</ns1:name>
              <ns1:fullName>北海道 札幌市</ns1:fullName>
              <ns1:order>0000002500</ns1:order>
              <ns1:status>ACTIVE</ns1:status>
            </ns1:child>
          </ns1:geographicLocation>
        </ns1:values>
        <ns1:values>
          <ns1:operationSucceeded>true</ns1:operationSucceeded>
          <ns1:geographicLocation>
            <ns1:code>JP-02</ns1:code>
            <ns1:name>青森県</ns1:name>
            <ns1:fullName>青森県</ns1:fullName>
            <ns1:order>0100000000</ns1:order>
            <ns1:status>ACTIVE</ns1:status>
            <ns1:child>
              <ns1:code>JP-02-0002</ns1:code>
              <ns1:parent>JP-02</ns1:parent>
              <ns1:name>青森市</ns1:name>
              <ns1:fullName>青森県 青森市</ns1:fullName>
              <ns1:order>0100000100</ns1:order>
              <ns1:status>ACTIVE</ns1:status>
            </ns1:child>
            <ns1:child>
              <ns1:code>JP-02-0004</ns1:code>
              <ns1:parent>JP-02</ns1:parent>
              <ns1:name>八戸市</ns1:name>
              <ns1:fullName>青森県 八戸市</ns1:fullName>
              <ns1:order>0100000700</ns1:order>
              <ns1:status>ACTIVE</ns1:status>
            </ns1:child>
          </ns1:geographicLocation>
        </ns1:values>
      </ns1:rval>
    </ns1:getGeographicLocationResponse>
  </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
<a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/"><img alt="クリエイティブ・コモンズ・ライセンス" style="border-width:0" src="https://i.creativecommons.org/l/by-nd/2.1/jp/88x31.png" /></a><br />この 作品 は <a rel="license" href="http://creativecommons.org/licenses/by-nd/2.1/jp/">クリエイティブ・コモンズ 表示 - 改変禁止 2.1 日本 ライセンスの下に提供されています。</a>
