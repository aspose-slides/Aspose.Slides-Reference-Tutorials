---
title: 在 Java PowerPoint 中向 SmartArt 新增助手節點
linktitle: 在 Java PowerPoint 中向 SmartArt 新增助手節點
second_title: Aspose.Slides Java PowerPoint 處理 API
description: 了解如何使用 Aspose.Slides 將輔助節點新增至 Java PowerPoint 簡報中的 SmartArt。提升您的 PowerPoint 編輯技能。
weight: 17
url: /zh-hant/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 介紹
在本教學中，我們將引導您完成使用 Aspose.Slides 在 Java PowerPoint 簡報中為 SmartArt 新增輔助節點的過程。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。您可以從以下位置下載並安裝最新的 JDK[這裡](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java：下載並安裝 Aspose.Slides for Java 函式庫[這個連結](https://releases.aspose.com/slides/java/).

## 導入包
首先，在 Java 程式碼中匯入必要的套件：
```java
import com.aspose.slides.*;
```
## 第 1 步：設定簡報
首先使用 PowerPoint 檔案的路徑建立一個簡報實例：
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## 第 2 步：遍歷形狀
遍歷簡報第一張投影片中的每個形狀：
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## 第 3 步：檢查 SmartArt 形狀
檢查形狀是否為 SmartArt 類型：
```java
if (shape instanceof ISmartArt)
```
## 第 4 步：遍歷 SmartArt 節點
遍歷 SmartArt 造型的所有節點：
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## 步驟5：檢查輔助節點
檢查該節點是否為輔助節點：
```java
if (node.isAssistant())
```
## 第六步：將輔助節點設定為正常
如果該節點是輔助節點，則將其設定為普通節點：
```java
node.setAssistant(false);
```
## 第 7 步：儲存簡報
儲存修改後的簡報：
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## 結論
恭喜！您已使用 Aspose.Slides 成功將助手節點新增至 Java PowerPoint 簡報中的 SmartArt。

## 常見問題解答
### 我可以為簡報中的 SmartArt 新增多個輔助節點嗎？
是的，您可以透過對每個節點重複該過程來新增多個輔助節點。
### 本教學適用於 PowerPoint 和 PowerPoint 範本嗎？
是的，您可以將本教學套用至 PowerPoint 簡報和範本。
### Aspose.Slides 與所有版本的 PowerPoint 相容嗎？
Aspose.Slides支援從97-2003到最新版本的PowerPoint版本。
### 我可以自訂輔助節點的外觀嗎？
是的，您可以使用 Aspose.Slides 提供的各種屬性和方法自訂外觀。
### SmartArt 中的節點數量有限制嗎？
PowerPoint 中的 SmartArt 支援大量節點，但建議保持合理以提高可讀性。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
