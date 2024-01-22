---
title: Aspose.Slides for .NET を使用して C# でカスタム ジオメトリを作成する
linktitle: Aspose.Slides を使用してジオメトリ シェイプにカスタム ジオメトリを作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET でカスタム ジオメトリを作成する方法を学びます。ユニークな形状でプレゼンテーションを強化します。 C# 開発者向けのステップバイステップ ガイド。
type: docs
weight: 15
url: /ja/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---
## 導入
ダイナミックなプレゼンテーションの世界では、独自の形状やジオメトリを追加することでコンテンツを向上させ、より魅力的で視覚的に魅力的なものにすることができます。 Aspose.Slides for .NET は、図形内にカスタム ジオメトリを作成するための強力なソリューションを提供し、従来のデザインから自由になることができます。このチュートリアルでは、Aspose.Slides for .NET を使用して GeometryShape にカスタム ジオメトリを作成するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語の基本的な理解。
- 開発環境にインストールされている .NET ライブラリの Aspose.Slides。
- Visual Studio または任意の優先 C# 開発環境のセットアップ。
## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## ステップ 1: プロジェクトをセットアップする
好みの開発環境で新しい C# プロジェクトを作成します。 Aspose.Slides for .NET が適切にインストールされていることを確認してください。
## ステップ 2: ドキュメント ディレクトリを定義する
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## ステップ 3: 外側の星の半径と内側の星の半径を設定する
```csharp
float R = 100, r = 50; //星の外側と内側の半径
```
## ステップ 4: スター ジオメトリ パスを作成する
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## ステップ 5: プレゼンテーションを作成する
```csharp
using (Presentation pres = new Presentation())
{
    //新しい形状を作成する
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    //新しいジオメトリ パスをシェイプに設定します
    shape.SetGeometryPath(starPath);
    //プレゼンテーションを保存する
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## ステップ 6: CreateStarGeometry メソッドを定義する
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## 結論
おめでとう！ Aspose.Slides for .NET を使用して GeometryShape にカスタム ジオメトリを作成する方法を学習しました。これにより、ユニークで視覚的に素晴らしいプレゼンテーションを作成する可能性の世界が開かれます。
## よくある質問
### 1. Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
はい、Aspose.Slides はさまざまなプログラミング言語をサポートしていますが、このチュートリアルでは C# に焦点を当てています。
### 2. Aspose.Slides for .NET のドキュメントはどこで見つけられますか?
訪問[ドキュメンテーション](https://reference.aspose.com/slides/net/)詳細については。
### 3. Aspose.Slides for .NET に利用できる無料トライアルはありますか?
はい、探索できます[無料トライアル](https://releases.aspose.com/)機能を体験していただけます。
### 4. Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
支援を求め、コミュニティに参加してください。[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
### 5. Aspose.Slides for .NET はどこで購入できますか?
 Aspose.Slides for .NET を購入できます[ここ](https://purchase.aspose.com/buy).