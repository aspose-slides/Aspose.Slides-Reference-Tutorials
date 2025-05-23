---
"date": "2025-04-22"
"description": "了解如何使用 Aspose.Slides 和 Python 修改 PowerPoint 中的 TextBox 文字、按鈕標題和圖片。利用互動元素增強您的簡報效果。"
"title": "掌握 Python 的 Aspose.Slides&#58;輕鬆修改 PowerPoint ActiveX 控制項"
"url": "/zh-hant/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 掌握 Aspose.Slides for Python：修改 PowerPoint ActiveX 控制項

在當今動態的數位環境中，自訂 Microsoft PowerPoint 簡報對於創建引人入勝的內容至關重要。無論您是開發互動式培訓模組還是透過使用者輸入功能增強商業演示，修改 PowerPoint ActiveX 控制項都可以顯著增強簡報的功能。本教學探討如何使用 Aspose.Slides for Python 變更 TextBox 文字和按鈕標題、取代圖片、重新定位或從投影片中刪除 ActiveX 控制項。

## 您將學到什麼
- 如何修改 PowerPoint 簡報中的文字方塊文字和按鈕標題。
- 在 ActiveX 控制項中替換影像的技術。
- 有效地重新定位或刪除 ActiveX 控制項的方法。
- 這些功能在現實場景中的實際應用。

在深入研究 Aspose.Slides for Python 之前，讓我們先回顧一下先決條件。

## 先決條件
要遵循本教程，請確保您已具備：
- **Python**：您的系統上安裝了 3.6 或更高版本。
- **透過.NET 實現 Python 的 Aspose.Slides**：可以使用 pip 安裝。
- 對 Python 程式設計有基本的了解，並熟悉 PowerPoint 的結構。

### 環境設定要求
1. **安裝 Aspose.Slides**：
   使用以下命令透過 .NET 安裝 Aspose.Slides for Python：

   ```bash
   pip install aspose.slides
   ```

2. **許可證獲取**： 
   首先獲得 [免費試用許可證](https://releases.aspose.com/slides/python-net/) 或申請臨時許可證以不受限制地探索全部功能。

3. **基本初始化**：
   匯入必要的模組並載入您的 PowerPoint 文檔，如下所示：

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # 您的程式碼將放在這裡。
   ```

## 實施指南
### 功能：更改文字方塊文字和替換圖像
#### 概述
此功能可讓您更新 TextBox ActiveX 控制項內的文字並取代其關聯圖像，這對於個人化簡報或動態更新內容很有用。

##### 逐步指南
1. **載入簡報**：
   首先載入包含 ActiveX 控制項的 PowerPoint 簡報。

   ```python
def change_textbox_and_image（）：
    使用 slides.Presentation(“YOUR_DOCUMENT_DIRECTORY/activex_master.pptm”) 作為簡報：
        投影片 = 簡報.投影片[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **創建替代圖像**：
   ActiveX啟動時產生影像替換原有內容。

   ```python
            import aspose.pydrawing as drawing

            # 建立具有指定尺寸的影像
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # 添加邊框線以獲得精緻的外觀
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### 功能：更改按鈕標題和替換圖像
#### 概述
更新簡報的 ActiveX 控制項中的按鈕標題，提供動態使用者互動的可能性。

##### 逐步指南
1. **載入簡報**：
   與以前一樣，首先載入 PowerPoint 文件。

   ```python
def change_button_caption_and_image（）：
    使用 slides.Presentation(“YOUR_DOCUMENT_DIRECTORY/activex_master.pptm”) 作為簡報：
        投影片 = 簡報.投影片[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **創建替代圖像**：
   產生用於視覺替換的圖像。

   ```python
            # 為按鈕的尺寸建立點陣圖
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # 添加邊框線以增加美觀
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### 功能：向下移動 ActiveX 控制項並儲存簡報
#### 概述
了解如何在投影片中重新定位 ActiveX 控件，增強佈局靈活性。

##### 逐步指南
1. **載入簡報**：
   開啟您的 PowerPoint 文件進行編輯。

   ```python
def move_active_x_controls_and_save()：
    使用 slides.Presentation(“YOUR_DOCUMENT_DIRECTORY/activex_master.pptm”) 作為簡報：
        投影片 = 簡報.投影片[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**結論：**
透過遵循本指南，您可以使用 Aspose.Slides for Python 有效地修改 PowerPoint ActiveX 控制項。這增強了簡報的互動性和客製化性，使其更能吸引觀眾。

## 關鍵字推薦
- “修改 PowerPoint ActiveX 控制項”
- “Aspose.Slides for Python”
- “在 PowerPoint 中更改文字方塊文字”
- “在 ActiveX 控制項中替換圖片”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}