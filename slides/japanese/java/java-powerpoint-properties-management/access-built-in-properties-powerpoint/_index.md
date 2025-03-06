---
title: PowerPoint の組み込みプロパティにアクセスする
linktitle: PowerPoint の組み込みプロパティにアクセスする
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides for Java を使用して PowerPoint の組み込みプロパティにアクセスする方法を学びます。このチュートリアルでは、作成者、作成日などを取得する方法について説明します。
type: docs
weight: 10
url: /ja/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## 導入
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションの組み込みプロパティにアクセスする方法について説明します。Aspose.Slides は、Java 開発者が PowerPoint プレゼンテーションをプログラムで操作し、プロパティの読み取りや変更などのタスクをシームレスに実行できるようにする強力なライブラリです。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Java開発キット（JDK）：システムにJDKがインストールされていることを確認してください。ここからダウンロードできます。[ここ](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Javaをこちらからダウンロードしてインストールします。[このリンク](https://releases.aspose.com/slides/java/).

## パッケージのインポート
まず、Java プロジェクトに必要なパッケージをインポートする必要があります。Java ファイルの先頭に次のインポート ステートメントを追加します。
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## ステップ1: プレゼンテーションオブジェクトを設定する
まず、操作する PowerPoint プレゼンテーションを表すプレゼンテーション オブジェクトを設定します。手順は次のとおりです。
```java
//プレゼンテーションファイルを含むディレクトリへのパス
String dataDir = "path_to_your_presentation_directory/";
//プレゼンテーションクラスをインスタンス化する
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## ステップ2: ドキュメントのプロパティにアクセスする
Presentation オブジェクトを設定したら、IDocumentProperties インターフェイスを使用してプレゼンテーションの組み込みプロパティにアクセスできます。さまざまなプロパティを取得する方法は次のとおりです。
### カテゴリー
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### 現在のステータス
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### 作成日
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### 著者
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### 説明
```java
System.out.println("Description : " + documentProperties.getComments());
```
### キーワード
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### 最終更新者
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### スーパーバイザー
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### 更新日
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### プレゼンテーション形式
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### 最終印刷日
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### プロデューサー間で共有
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### 主題
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### タイトル
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## 結論
このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションの組み込みプロパティにアクセスする方法を学習しました。上記の手順に従うことで、作成者、作成日、タイトルなどのさまざまなプロパティをプログラムで簡単に取得できます。
## よくある質問
### Aspose.Slides for Java を使用してこれらの組み込みプロパティを変更できますか?
はい、Aspose.Slides を使用してこれらのプロパティを変更できます。IDocumentProperties インターフェイスによって提供される適切な setter メソッドを使用するだけです。
### Aspose.Slides はさまざまなバージョンの PowerPoint と互換性がありますか?
Aspose.Slides は幅広いバージョンの PowerPoint をサポートしており、さまざまなプラットフォーム間での互換性が確保されています。
### カスタムプロパティも取得できますか?
はい、組み込みプロパティの他に、Aspose.Slides for Java を使用してカスタム プロパティを取得および変更することもできます。
### Aspose.Slides はドキュメントとサポートを提供していますか?
はい、包括的なドキュメントやサポートフォーラムを見つけることができます。[Aspose ウェブサイト](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java の試用版はありますか?
はい、無料試用版は以下からダウンロードできます。[ここ](https://releases.aspose.com/).