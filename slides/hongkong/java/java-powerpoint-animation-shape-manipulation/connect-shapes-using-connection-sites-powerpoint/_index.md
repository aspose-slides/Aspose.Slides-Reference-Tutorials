---
title: 使用 PowerPoint 中的連接站點連接形狀
linktitle: 使用 PowerPoint 中的連接站點連接形狀
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides for Java 在 PowerPoint 中連接形狀。輕鬆自動化您的簡報。
weight: 19
url: /zh-hant/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在本教學中，我們將探索如何使用 Aspose.Slides for Java 在 PowerPoint 中使用連線網站連線形狀。這個功能強大的函式庫使我們能夠以程式設計方式操作 PowerPoint 簡報，從而使連接形狀等任務無縫且有效率。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。您可以從以下位置下載並安裝它[網站](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java：從下列位置下載並安裝 Aspose.Slides for Java：[下載頁面](https://releases.aspose.com/slides/java/).
3. 整合開發環境 (IDE)：選擇用於 Java 開發的 IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。

## 導入包
首先，將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.slides.*;

```
## 第 1 步：存取形狀集合
存取所選投影片的形狀集合：
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//實例化表示 PPTX 檔案的簡報類
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## 第 2 步：新增連接器形狀
將連接器形狀新增至投影片形狀集合：
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 第 3 步：新增自選圖形
新增自動形狀，如橢圓形和矩形：
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 第 4 步：將形狀連接到連接器
將形狀連接到連接器：
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 步驟5：設定連線站台索引
設定形狀所需的連接站點索引：
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## 結論
在本教學中，我們學習如何使用 Aspose.Slides for Java 在 PowerPoint 中使用連線網站連線形狀。有了這些知識，您現在可以輕鬆自動化和自訂您的 PowerPoint 簡報。
## 常見問題解答
### Aspose.Slides for Java 可以用於其他 PowerPoint 操作任務嗎？
是的，Aspose.Slides for Java 提供了廣泛的用於建立、編輯和轉換 PowerPoint 簡報的功能。
### Aspose.Slides for Java 可以免費使用嗎？
 Aspose.Slides for Java 是一個商業庫，但您可以透過免費試用來探索其功能。訪問[這裡](https://releases.aspose.com/)開始。
### 如果在使用 Aspose.Slides for Java 時遇到任何問題，我可以獲得支援嗎？
是的，您可以從 Aspose 社群論壇獲得支持[這裡](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java 是否有臨時授權？
是的，臨時許可證可用於測試和評估目的。您可以獲得一個[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以購買 Aspose.Slides for Java 的授權？
您可以從 Aspose 網站購買許可證[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
