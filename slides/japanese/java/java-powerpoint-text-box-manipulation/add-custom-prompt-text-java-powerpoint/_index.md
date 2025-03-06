---
title: Java PowerPoint にカスタム プロンプト テキストを追加する
linktitle: Java PowerPoint にカスタム プロンプト テキストを追加する
second_title: Aspose.Slides Java PowerPoint 処理 API
description: Aspose.Slides を使用して Java PowerPoint にカスタム プロンプト テキストを追加する方法を学びます。このチュートリアルを使用すると、ユーザー インタラクションが簡単に強化されます。
type: docs
weight: 12
url: /ja/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---
## 導入
今日のデジタル時代では、ダイナミックで魅力的なプレゼンテーションを作成することが、効果的なコミュニケーションに不可欠です。Aspose.Slides for Java は、スライド、図形、テキストなどをカスタマイズするための広範な機能を提供し、開発者が PowerPoint プレゼンテーションをプログラムで操作できるようにします。このチュートリアルでは、Aspose.Slides を使用して Java PowerPoint プレゼンテーションのプレースホルダーにカスタム プロンプト テキストを追加する手順を説明します。
## 前提条件
このチュートリアルに進む前に、次のものを用意してください。
- Java プログラミングの基礎知識。
- システムに JDK (Java Development Kit) がインストールされています。
-  Aspose.Slides for Javaがインストールされています。ここからダウンロードできます。[ここ](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA や Eclipse などの統合開発環境 (IDE) がセットアップされています。

## パッケージのインポート
まず、Java ファイルに必要な Aspose.Slides クラスをインポートします。
```java
import com.aspose.slides.*;
```

## ステップ1: プレゼンテーションを読み込む
まず、プレースホルダーにカスタム プロンプト テキストを追加する PowerPoint プレゼンテーションを読み込みます。
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## ステップ2: スライドシェイプを反復処理する
スライドにアクセスし、その図形を反復処理してプレースホルダーを見つけます。
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            //オートシェイププレースホルダーのみを処理する
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            //カスタムプロンプトテキストを設定する
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            //確認のためにプレースホルダーテキストを印刷します
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //変更したプレゼンテーションを保存する
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 結論
結論として、Aspose.Slides for Java は、PowerPoint プレゼンテーションをプログラムでカスタマイズするタスクを簡素化します。このチュートリアルに従うことで、プレースホルダーに意味のあるプロンプト テキストを簡単に追加して、ユーザー インタラクションを強化できます。
## よくある質問
### Aspose.Slides for Java を使用して、PowerPoint スライドの任意のプレースホルダーにプロンプト テキストを追加できますか?
はい、さまざまな種類のプレースホルダーにプログラムでカスタムプロンプトテキストを設定できます。
### Aspose.Slides for Java はすべてのバージョンの PowerPoint と互換性がありますか?
Aspose.Slides は幅広いバージョンの PowerPoint をサポートし、互換性と信頼性を保証します。
### Aspose.Slides for Java のその他の例やドキュメントはどこで入手できますか?
訪問[Aspose.Slides for Java ドキュメント](https://reference.aspose.com/slides/java/)包括的なガイドと例については、こちらをご覧ください。
### Aspose.Slides for Java の一時ライセンスを取得するにはどうすればよいですか?
あなたは[一時ライセンス](https://purchase.aspose.com/temporary-license/)Aspose.Slides の全機能を評価します。
### Aspose.Slides for Java はスライドへのカスタム アニメーションの追加をサポートしていますか?
はい、Aspose.Slides はスライド アニメーションをプログラムで管理するための API を提供します。