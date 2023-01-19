## ラボ環境の使用方法

- <a href="https://qualia906.github.io/skillsboost/how-to-login/" target=_blank>Cloud Skills Boost (Qwiklabs) へのログイン手順</a>
- <a href="https://qualia906.github.io/skillsboost/how-to-use-lab/" target=_blank>ラボの開始手順 (AWS / GCP)</a>

<br />    

## ラボ (演習)


### 演習 1：<a href="https://amazon.qwiklabs.com/focuses/55893?catalog_rank=%7B%22rank%22%3A3%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=21982049" target=_blank>Introduction to Amazon EC2 Auto Scaling (日本語版)</a>【AWS】

所要時間：40 分

- [ラボ手順](https://github.com/qualia906/cloudarch/blob/main/docs/lab1/index.md)（このラボ手順を使用してください）

- Qwiklabs へのサイドログインが必要になります。アカウントは同一です。
    

<br /> 

### 演習 2：<a href="https://www.qwiklabs.com/focuses/1029?catalog_rank=%7B%22rank%22%3A3%2C%22num_filters%22%3A1%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=4806504" target=_blank>Docker の概要</a>【Google Cloud】

所要時間：1 時間

-   初回にdocker buildコマンドを実行した際に、「Cloud Shell の承認」というダイアログが表示されることがありますが、そのまま承認してください。
    
-   「公開」で Docker イメージを Google Container Registry に push した後の手順では、Cloud Shell ではなく GCP コンソール (GUI) から [ナビゲーション  メニュー] > [Container Registry] をクリックします。
    
-   任意のエディタで内容を書き換える手順において、vi や nano の操作が不安な方は、次のコマンドをコピーして実行してください。  

    ```
    cp -p app.js app.js.org  
    sed -ie 's/Hello World/Welcome to Cloud/' app.js
    ```
  
<br />

### 演習 3：<a href="https://amazon.qwiklabs.com/focuses/51801?catalog_rank=%7B%22rank%22%3A1%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=19747351" target=_blank>Introduction to Amazon DynamoDB (日本語版)</a>【AWS】

所要時間：40分
    
- ラボが利用できない場合は、代替演習として <a href="https://www.qwiklabs.com/focuses/941?catalog_rank=%7B%22rank%22%3A5%2C%22num_filters%22%3A0%2C%22has_search%22%3Atrue%7D&parent=catalog&search_id=9212410" target=_blank>DataStore: Qwik Start</a> を実行してください。  
  Datastore (Firestore  の Datastore Mode) は、DynamoDB に相当する Google Cloud の NoSQL データベース サービスです。

<br />

### 演習 4：クラウドデザインパターンの適用

-   <a href="http://aws.clouddesignpattern.org/index.php/%E3%83%A1%E3%82%A4%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8" target=_blank>AWS クラウドデザインパターン</a>    
-   <a href="http://web.archive.org/web/20171008040110/http:/aws.clouddesignpattern.org/index.php/%E3%83%A1%E3%82%A4%E3%83%B3%E3%83%9A%E3%83%BC%E3%82%B8" target=_blank>AWS クラウドデザインパターン</a>（上記が表示されない場合はこちら）
    
<br />  

## Reference

- AWS
  -  <a href="https://aws.amazon.com/jp/architecture/well-architected/" target=_blank>AWS Well-Architected – 安全で効率的なクラウド対応アプリケーション</a> 

 
 - Microsoft Azure   
   -   <a href="https://docs.microsoft.com/ja-jp/azure/architecture/patterns/" target=_blank>Microsoft Azure クラウド設計パターン</a>  
   -   <a href="https://docs.microsoft.com/ja-jp/azure/architecture/framework/" target=_blank>Microsoft Azure Well-Architected Framework</a>    


- Google Cloud
  -  <a href="https://events.withgoogle.com/solution-design-pattern/" target=_blank>Google Cloud ソリューション デザインパターン</a>  
  -  <a href="https://cloud.google.com/architecture/framework" target=_blank>Google Cloud アーキテクチャ フレームワーク</a> 
  -  <a href="https://www.slideshare.net/GoogleCloudPlatformJP/cloud-onair-google-cloud-201927-133656441" target=_blank>ハイブリッドクラウドのパターン (ハイブリッドクラウドと Google Cloud)</a>  
