---
"date": "2025-04-18"
"description": "了解如何使用 Aspose.Slides for Java 自動建立簡報。動態自訂文字框架和字體樣式，非常適合商業宣傳或教育講座。"
"title": "Aspose.Slides for Java&#58;動態文字框架與字型自訂指南"
"url": "/zh-hant/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java：掌握動態文字框架與字體樣式

在當今的數位環境中，無論您是在進行商業推廣還是學術講座，製作引人注目的簡報對於有效溝通至關重要。使用 Java 自動執行和自訂這些任務可以提高您的工作效率。進入 **Aspose.Slides for Java**—一個強大的庫，讓開發人員可以輕鬆建立、修改和保存簡報。本教學將指導您使用 Aspose.Slides for Java 建立動態文字方塊和自訂簡報中的字體樣式。

## 您將學到什麼
- 使用 Aspose.Slides for Java 設定您的環境。
- 建立簡報並新增帶有文字方塊的自動形狀。
- 將部分文字新增至文字框架。
- 自訂預設文字樣式和段落字體高度。
- 設定特定部分的字體高度。
- 儲存最終的簡報。

讓我們探索如何有效地利用這些功能！

### 先決條件

在開始之前，請確保您的開發環境已準備就緒。你需要：

- **Java 開發工具包 (JDK)：** 版本 8 或更高版本
- **Maven/Gradle：** 用於依賴管理
- **選擇的IDE：** 例如 IntelliJ IDEA、Eclipse 或 NetBeans
- 對 Java 程式設計概念有基本的了解

### 設定 Aspose.Slides for Java

要開始使用 Aspose.Slides for Java，請將其包含在您的專案中。方法如下：

#### Maven 設定

將以下相依性新增至您的 `pom.xml` 文件：

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 設定

對於 Gradle，將其添加到您的 `build.gradle`：

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 直接下載

或者，從下載最新版本 [Aspose.Slides for Java 發布](https://releases。aspose.com/slides/java/).

**許可證取得：** 從免費試用開始或取得臨時許可證以無限制地探索全部功能。如需購買，請訪問 [Aspose 的購買頁面](https://purchase。aspose.com/buy).

### 實施指南

#### 功能 1：建立簡報並新增文字框架

若要建立簡報並新增帶有文字方塊的自動形狀：

**概述：** 此功能初始化一個新的簡報並為第一個投影片新增一個矩形，包括一個文字方塊。

```java
import com.aspose.slides.*;

public class Feature1 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            newShape.addTextFrame("");
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().clear();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 我們初始化一個 `Presentation` 物件並在第一張投影片中新增自動形狀。形狀設定為具有指定尺寸的矩形。

#### 功能 2：在文字方塊中新增部分內容

若要將文字部分新增至段落：

**概述：** 此功能示範如何在文字方塊的段落內新增多個文字部分。

```java
import com.aspose.slides.*;

public class Feature2 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            IPortion portion0 = new Portion("Sample text with first portion");
            IPortion portion1 = new Portion(" and second portion.");

            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 我們建立文字部分並將其新增到形狀文字方塊的第一段。

#### 功能3：設定預設文字樣式字體高度

若要為所有文字設定預設字體高度：

**概述：** 此功能可修改簡報中的預設字體大小。

```java
import com.aspose.slides.*;

public class Feature3 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 整個簡報的預設文字樣式字體高度設定為 24 點。

#### 功能4：設定段落預設字體高度

若要自訂特定段落內的字體高度：

**概述：** 此功能將自訂字體大小套用至特定段落的預設部分格式。

```java
import com.aspose.slides.*;

public class Feature4 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            newShape.getTextFrame().getParagraphs().get_Item(0)
                .getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 我們將形狀第一段所有文字的字體高度設定為 40 點。

#### 功能5：設定特定部分字體高度

要調整個別部分字體高度：

**概述：** 此功能允許自訂段落內特定部分的字體大小。

```java
import com.aspose.slides.*;

public class Feature5 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0)
                .getPortionFormat().setFontHeight(55);
            
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1)
                .getPortionFormat().setFontHeight(18);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 我們為段落內的特定文字部分設定自訂字體高度，並增強視覺層次。

#### 功能 6：儲存簡報

若要儲存您的簡報：

**概述：** 此功能示範如何將簡報儲存為您想要的文件格式和位置。

```java
import com.aspose.slides.*;

public class Feature6 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            String outputDir = "YOUR_OUTPUT_DIRECTORY"; // 確保將其替換為您的實際目錄路徑
            pres.save(outputDir + "SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**解釋：** 簡報以PPTX格式儲存到指定目錄。

### 實際應用

1. **公司介紹：** 自動產生具有動態文字和樣式的季度報告投影片。
2. **教育講座：** 透過自訂字體樣式和大小來提高教學材料的可讀性。
3. **商業推廣：** 透過精確控製文字元素來創建有影響力的演示文稿，以有效地吸引觀眾。

### 結論

透過掌握 Aspose.Slides for Java，您可以大幅改善簡報建立過程。自動化文字框架客製化不僅節省時間，還能確保不同幻燈片和項目之間的一致性。透過本教學所獲得的技能，您可以輕鬆滿足各種演示需求。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}