## ラボ 1 - Introduction to Amazon EC2

こちらの手順を参照して演習を進めてください。

<br />

このラボでは以下のことを行います。

- 仮想マシンでウェブサーバーを作成する
- セキュリティ グループを変更し、HTTPアクセスを許可する

<br />

### タスク 1：仮想マシンを作成する

まずは、ウェブサーバーのセットアップを行った仮想マシンを作成します。

<br />

1.  画面左上の [**サービス**] で [**コンピューティング**] > [**EC2**] をクリックします    

<br />

2.  左側のナビゲーション ペインで [**インスタンス**] をクリックします

<br />

3.  右上の [**インスタンスを起動**] をクリックします
      
<br />

4.  「名前とタグ」で、次のように設定します

    - 名前：`Web Server`  

<br />
    
5.  [アプリケーションおよび OS イメージ (Amazon マシンイメージ) ] で、[**クイックスタートタブ**] を選択し、**Amazon Linux** を選択します（デフォルトで選択されています）  
      
<br />

6.  [**インスタンスタイプ**] で、ドロップダウンの一覧から **t3.micro** を選択します
      
<br />

7.  [**キーペア (ログイン)** ]で、キーペア名のドロップダウンをクリックし、[**キーペアなしで続行**] を選択します（今回の演習では仮想マシンにログインはしないので、この設定で問題ありません）  
      
<br />

8.  [**ネットワーク設定**] で、右上の [**編集**] をクリックします
      
<br />

9.  [**VPC**] のドロップダウン一覧から [**～ (Lab VPC)** ] と記載されている方のネットワークを選択します

<br />

10.  [**ファイアウォール (セキュリティ グループ)** ]で [**セキュリティ グループを作成**] を選択し (デフォルトで選択されています) 、以下のように設定します
      
     - セキュリティ グループ名：`Web Server security group`  
     - 説明：`Security group for my web server`
     - [**インバウンド セキュリティ グループ**] にある **ssh** のルールを、右横の [**削除**] をクリックして削除する  
  
<br />

11.  画面の下までスクロールし、[**高度な詳細**] をクリックして展開します
      
<br />

12.  さらに一番下までスクロールし、ユーザーデータに以下のコマンドをコピー & ペーストで貼り付けます

```
#!/bin/bash  
yum -y install httpd  
systemctl enable httpd  
systemctl start httpd  
echo '<html><h1>Hello From Your Web Server!</h1></html>' > /var/www/html/index.html
```  

このコマンドにより、仮想マシンの起動時にウェブサーバーがインストールされ、シンプルなウェブページを表示するように設定が行われます。  
  
<br />

13.  画面右（または最下部）にある [**インスタンスを起動**] をクリックします

<br />

14.  [**すべてのインスタンスを表示**] をクリックします

<br />

15.  仮想マシンの状態を確認できます。仮想マシンが起動したら、新しく作成した Web Server の上でクリックすると、下部に詳細が表示されます
      
<br />

<br />

### タスク 2：セキュリティ グループを更新してウェブサーバーにアクセスする

次に、作成した Web Server に http でアクセスしてみます。また、アクセスが成功するように AWS でのファイアウォール機能であるセキュリティ グループを更新します。

<br />

1.  仮想マシンの詳細の右上に、インターネットからのアクセスに必要な [パブリック IPv4 DNS名] が表示されています。コピーボタンのアイコンをクリックするとアドレスをコピーできるので、コピーして自分の Web ブラウザの別のタブの URL に貼り付けてアクセスしてみます

> **Note**      
> 上記のアクセスでは Web ページを表示することができません。セキュリティ グループで仮想マシンへの http 通信を許可していないためです。  
      
<br />

2.  左側のナビゲーション ペインで [**セキュリティ グループ**] をクリックします
      
<br />

3.  セキュリティ グループ名が **Web Server security group** となっている [**Security group ID**] にチェックを入れます   
    このセキュリティ グループにはルールが設定されていません

<br />

4.  [**インバウンドルール**] タブをクリックします

<br />

5.  [**インバウンドのルールを編集**] をクリックします

<br />

6.  [**ルールを追加**] をクリックし、以下のように設定します

    - タイプ：`HTTP`  
    - ソース：`Anywhere-IPv4`  

<br />

7.  [**ルールを保存**] をクリックします  

<br />

8.  先ほど開いたウェブサーバーのタブに戻り、ページを更新します
      
    今度は、「Hello From Your Web Server!」とウェブページが表示されるはずです。  
    (アクセスできない場合は、https でアクセスをしていないかどうか URL を確認してみてください。https でアクセスしている場合は http に URL を直して再度接続します。そのほか途中のユーザーデータの設定やセキュリティ グループの設定などを間違えているとウェブページが表示できません）  
      
<br />

ラボ１は以上です。お疲れ様でした。
