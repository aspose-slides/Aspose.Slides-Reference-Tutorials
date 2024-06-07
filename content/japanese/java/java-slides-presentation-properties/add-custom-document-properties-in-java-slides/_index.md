---
title: Java スライドにカスタム ドキュメント プロパティを追加する
linktitle: Java スライドにカスタム ドキュメント プロパティを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Java スライドのカスタム ドキュメント プロパティを使用して PowerPoint プレゼンテーションを強化する方法を学びます。Aspose.Slides for Java を使用したコード例を含むステップ バイ ステップ ガイド。
type: docs
weight: 13
url: /ja/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

## Java スライドでのカスタム ドキュメント プロパティの追加の概要

このチュートリアルでは、Aspose.Slides for Java を使用して PowerPoint プレゼンテーションにカスタム ドキュメント プロパティを追加する手順について説明します。カスタム ドキュメント プロパティを使用すると、参照または分類のためにプレゼンテーションに関する追加情報を保存できます。

## 前提条件

始める前に、Aspose.Slides for Java ライブラリが Java プロジェクトにインストールされ、設定されていることを確認してください。

## ステップ1: 必要なパッケージをインポートする

```java
import com.aspose.slides.*;
```

## ステップ2: 新しいプレゼンテーションを作成する

まず、新しいプレゼンテーション オブジェクトを作成する必要があります。これは次のように実行できます。

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";

//プレゼンテーションクラスをインスタンス化する
Presentation presentation = new Presentation();
```

## ステップ3: ドキュメントのプロパティを取得する

次に、プレゼンテーションのドキュメント プロパティを取得します。これらのプロパティには、タイトル、作成者などの組み込みプロパティと、追加できるカスタム プロパティが含まれます。

```java
//ドキュメントプロパティの取得
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## ステップ4: カスタムプロパティの追加

次に、プレゼンテーションにカスタム プロパティを追加しましょう。カスタム プロパティは名前と値で構成されます。カスタム プロパティを使用して、必要な情報を保存できます。

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## ステップ 5: 特定のインデックスでプロパティ名を取得する

特定のインデックスにあるカスタム プロパティの名前を取得することもできます。これは、特定のプロパティを操作する必要がある場合に便利です。

```java
//特定のインデックスのプロパティ名を取得する
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## ステップ 6: 選択したプロパティを削除する

カスタム プロパティを削除する場合は、その名前を指定して削除できます。ここでは、手順 5 で取得したプロパティを削除します。

```java
//選択したプロパティを削除しています
documentProperties.removeCustomProperty(getPropertyName);
```

## ステップ7: プレゼンテーションを保存する

最後に、追加および削除されたカスタム プロパティを含むプレゼンテーションをファイルに保存します。

```java
//プレゼンテーションを保存しています
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Java スライドにカスタム ドキュメント プロパティを追加するための完全なソース コード

```java
//ドキュメント ディレクトリへのパス。
String dataDir = "Your Document Directory";
//プレゼンテーションクラスをインスタンス化する
Presentation presentation = new Presentation();
//ドキュメントプロパティの取得
IDocumentProperties documentProperties = presentation.getDocumentProperties();
//カスタムプロパティの追加
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
//特定のインデックスのプロパティ名を取得する
String getPropertyName = documentProperties.getCustomPropertyName(2);
//選択したプロパティを削除しています
documentProperties.removeCustomProperty(getPropertyName);
//プレゼンテーションを保存しています
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 結論

Aspose.Slides を使用して Java で PowerPoint プレゼンテーションにカスタム ドキュメント プロパティを追加する方法を学習しました。カスタム プロパティは、プレゼンテーションに関連する追加情報を保存するのに便利です。この知識を拡張して、特定のユース ケースの必要に応じて、より多くのカスタム プロパティを含めることができます。

## よくある質問

### カスタム プロパティの値を取得するにはどうすればよいですか?

カスタムプロパティの値を取得するには、`get_Item`方法`documentProperties`オブジェクト。例:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### 異なるデータ型のカスタム プロパティを追加できますか?

はい、例に示すように、数値、文字列、日付など、さまざまなデータ型のカスタム プロパティを追加できます。Aspose.Slides for Java は、さまざまなデータ型をシームレスに処理します。

### 追加できるカスタム プロパティの数に制限はありますか?

追加できるカスタム プロパティの数に厳密な制限はありません。ただし、プロパティを過剰に追加すると、プレゼンテーション ファイルのパフォーマンスとサイズに影響する可能性があることに注意してください。

### プレゼンテーション内のすべてのカスタム プロパティを一覧表示するにはどうすればよいでしょうか?

すべてのカスタム プロパティをループして一覧表示することができます。これを行う方法の例を次に示します。

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

このコードは、プレゼンテーション内のすべてのカスタム プロパティの名前と値を表示します。