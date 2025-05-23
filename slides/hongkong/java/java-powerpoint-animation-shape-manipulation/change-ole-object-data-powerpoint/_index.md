---
"description": "了解如何使用 Aspose.Slides for Java 變更 PowerPoint 中的 OLE 物件資料。高效、輕鬆更新的逐步指南。"
"linktitle": "在 PowerPoint 中更改 OLE 物件數據"
"second_title": "Aspose.Slides Java PowerPoint 處理 API"
"title": "在 PowerPoint 中更改 OLE 物件數據"
"url": "/zh-hant/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 PowerPoint 中更改 OLE 物件數據

## 介紹
當您需要更新嵌入的內容而無需手動編輯每張投影片時，更改 PowerPoint 簡報中的 OLE 物件資料可能是一項至關重要的任務。本綜合指南將引導您完成使用 Aspose.Slides for Java 的過程，這是一個專為處理 PowerPoint 簡報而設計的強大函式庫。無論您是經驗豐富的開發人員還是剛起步，您都會發現本教學很有幫助且易於遵循。
## 先決條件
在深入研究程式碼之前，讓我們確保您擁有開始所需的一切。
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從下載 [Oracle 的網站](https://www。oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java：從下載最新版本 [Aspose.Slides下載頁面](https://releases。aspose.com/slides/java/).
3. 整合開發環境 (IDE)：您可以使用任何 Java IDE，例如 IntelliJ IDEA、Eclipse 或 NetBeans。
4. Aspose.Cells for Java：這是修改 OLE 物件內的嵌入資料所必需的。從下載 [Aspose.Cells下載頁面](https://releases。aspose.com/cells/java/).
5. 簡報文件：準備好嵌入 OLE 物件的 PowerPoint 文件。在本教程中，我們將其命名為 `ChangeOLEObjectData。pptx`.
## 導入包
首先，讓我們在您的 Java 專案中匯入必要的套件。
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

現在，讓我們將這個過程分解為簡單、易於管理的步驟。
## 步驟 1：載入 PowerPoint 簡報
首先，您需要載入包含 OLE 物件的 PowerPoint 簡報。
```java
// 文檔目錄的路徑。
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## 步驟 2：存取包含 OLE 物件的幻燈片
接下來，取得嵌入了 OLE 物件的幻燈片。
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 步驟 3：在投影片中尋找 OLE 對象
遍歷投影片中的形狀來定位 OLE 物件。
```java
OleObjectFrame ole = null;
// 遍歷 Ole 框架的所有形狀
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## 步驟 4：從 OLE 物件中提取嵌入的數據
如果找到 OLE 對象，則提取其嵌入的資料。
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## 步驟5：使用Aspose.Cells修改嵌入數據
現在，使用 Aspose.Cells 讀取和修改嵌入的數據，在本例中，嵌入的數據很可能是一個 Excel 工作簿。
```java
    Workbook wb = new Workbook(msln);
    // 修改工作簿數據
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## 步驟 6：將修改後的資料儲存回 OLE 對象
進行必要的變更後，將修改後的工作簿儲存回 OLE 物件。
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## 步驟 7：儲存更新後的簡報
最後，儲存更新後的 PowerPoint 簡報。
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 結論
一旦將其分解為簡單的步驟，使用 Aspose.Slides for Java 更新 PowerPoint 簡報中的 OLE 物件資料就是一個簡單的過程。本指南將引導您載入簡報、存取和修改嵌入的 OLE 資料以及儲存更新的簡報。透過這些步驟，您可以以程式設計方式有效地管理和更新 PowerPoint 投影片中嵌入的內容。
## 常見問題解答
### PowerPoint 中的 OLE 物件是什麼？
OLE（物件連結和嵌入）物件允許將其他應用程式（如 Excel 電子表格）的內容嵌入到 PowerPoint 投影片中。
### 我可以將 Aspose.Slides 與其他程式語言一起使用嗎？
是的，Aspose.Slides 支援多種語言，包括 .NET、Python 和 C++。
### 我需要 Aspose.Cells 來修改 PowerPoint 中的 OLE 物件嗎？
是的，如果 OLE 物件是 Excel 電子表格，則需要 Aspose.Cells 來修改它。
### Aspose.Slides 有試用版嗎？
是的，你可以得到 [免費試用](https://releases.aspose.com/) 測試 Aspose.Slides 的功能。
### 在哪裡可以找到 Aspose.Slides 的文檔？
您可以找到有關 [Aspose.Slides 文件頁面](https://reference。aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}