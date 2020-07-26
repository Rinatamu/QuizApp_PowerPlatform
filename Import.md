# インポート手順

## 1. Power Apps 

1. Power Apps を開く

https://make.powerapps.com/ にアクセスし、インポート先の環境を指定しておく。

![](pasteimage/2020-07-26-16-25-27.png)

2. ソリューションを開く

![](pasteimage/2020-07-26-16-26-03.png)

3. インポートをクリックする

![](pasteimage/2020-07-26-16-26-43.png)

4. 別ウィンドウが立ち上がるので、「chooce file」をクリックする

![](pasteimage/2020-07-26-16-27-49.png)

5. QuizApplication.Zip を選択する

![](pasteimage/2020-07-26-16-29-28.png)

6. 次へをクリックする

![](pasteimage/2020-07-26-16-30-11.png)

7. 引き続き次へをクリックする

![](pasteimage/2020-07-26-16-34-07.png)

※アンインストールができない旨の警告が出ているが、これはインポート先でも変更可能としているため表示されている。アンインストールはできないが、個別で削除することは可能。

8. インポートをクリックする

![](pasteimage/2020-07-26-16-35-10.png)

9. インポートが完了するまで待つ

![](pasteimage/2020-07-26-16-37-43.png)

10. インポートが完了したら、「すべてのカスタマイズの公開」をクリックする。

![](pasteimage/2020-07-26-16-39-15.png)

11. 公開が完了したら閉じるをクリックする。

12. Power Apps アプリに以下の2つが追加されていることを確認する。

![](pasteimage/2020-07-26-16-42-38.png)


# 2. Logic Apps

## 2-1. 前提条件

* Azure アカウントを持っていること
* インポート先のリソースグループを作成していること
* Azure Az モジュールがインストール済みであること

## 2-2. インポート

1. Power Shellを起動する

2. 以下のコマンドを実行する

```
Connect-AzAccount
Get-AzSubscription
Select-AzureRmSubscription -Subscription <インポート先のリソースグループが含まれるサブスクリプション名>
New-AzResourceGroupDeployment -ResourceGroupName <インポート先のリソースグループ名> -TemplateFile  <template.json のフルパス>
```

以降は作成途中
