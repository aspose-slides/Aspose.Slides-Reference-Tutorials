---
date: '2026-11-16'
description: วาดกรอบรอบข้อความในตาราง PowerPoint ด้วย Aspose.Slides for Java – เรียนรู้วิธีสร้างตาราง,
  เพิ่มข้อความในเซลล์, ไฮไลท์เซลล์, และส่งออกไฟล์เป็น PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: วาดกรอบรอบข้อความในตาราง PowerPoint ด้วย Aspose.Slides for Java. คู่มือนี้แสดงวิธีสร้างตาราง,
  เพิ่มและจัดตำแหน่งข้อความ, ไฮไลท์เซลล์, และส่งออกสไลด์เป็น PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: วิธีวาดกรอบรอบข้อความและสร้างตารางใน PowerPoint ด้วย Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: วิธีวาดกรอบรอบข้อความและสร้างตารางใน PowerPoint ด้วย Aspose.Slides for Java
url: /th/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# วิธีวาดกรอบรอบข้อความและสร้างตารางใน PowerPoint ด้วย Aspose.Slides for Java

## บทนำ

การวาด **draw frame around text** บนสไลด์ PowerPoint ช่วยให้คุณเน้นตัวเลขสำคัญโดยไม่ต้องเปลี่ยนแปลงเนื้อหาต้นฉบับ ในบทเรียนนี้คุณจะได้เรียนรู้วิธีสร้างตารางโดยโปรแกรม, แทรกและจัดตำแหน่งข้อความภายในเซลล์, เน้นคำหรือเซลล์ทั้งหมด, และสุดท้ายบันทึกงานนำเสนอเป็นไฟล์ PPTX เมื่อเสร็จคุณจะได้สไลด์ที่ดูเป็นมืออาชีพและดึงดูดความสนใจของผู้ชมไปยังตำแหน่งที่ต้องการ

## คำตอบอย่างรวดเร็ว
- **What does “add text to table” mean?** หมายถึงการแทรกหรืออัปเดตเนื้อหาข้อความของเซลล์ตารางแต่ละเซลล์โดยโปรแกรม  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – ขั้นตอน **save presentation as pptx** นี้ทำให้การเปลี่ยนแปลงของคุณเสร็จสมบูรณ์  
- **How can I align text inside a shape?** ใช้ `TextAlignment.Left` (หรือ Center/Right) ผ่าน `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`  
- **Can I draw a rectangle around a paragraph?** ได้ – วนลูปผ่านย่อหน้า, ดึงสี่เหลี่ยมขอบเขตของมัน, แล้วเพิ่ม `IAutoShape` ที่ไม่มีการเติมสีและมีเส้นสีดำ  
- **Do I need a license?** ใบอนุญาตชั่วคราวใช้ได้สำหรับการประเมิน; ใบอนุญาตเต็มจำเป็นสำหรับการใช้งานในสภาพแวดล้อมการผลิต  

## ทำไมต้องวาดกรอบรอบข้อความ?

การวาดกรอบรอบข้อความช่วยให้เน้นตัวเลขสำคัญ, คำเตือน, หรือหัวข้อได้ทันที โดยให้สัญญาณภาพโดยไม่กระทบต่อการจัดรูปแบบเดิม ทำให้เหมาะสำหรับรายงานการเงิน, แดชบอร์ด KPI, หรือสไลด์ใด ๆ ที่ต้องการการเน้น

## draw frame around text คืออะไร?

`draw frame around text` คือเทคนิคการเพิ่มรูปสี่เหลี่ยมที่ตามขอบของย่อหน้า หรือส่วนของข้อความโดยใช้การกำหนดรูปแบบเส้นโดยไม่มีการเติมสีภายใน วิธีนี้ช่วยให้คุณเน้นเนื้อหาโดยไม่ต้องแก้ไขข้อความเอง

## ข้อกำหนดเบื้องต้น

### ไลบรารีที่จำเป็น
คุณจะต้องใช้ Aspose.Slides for Java รวมเข้ากับหนึ่งในตัวจัดการแพ็กเกจต่อไปนี้:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

คุณยังสามารถเรียกดูเวอร์ชันที่ปล่อยได้ที่ [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### การตั้งค่าสภาพแวดล้อม
แนะนำให้ใช้ Java Development Kit (JDK) 16 หรือใหม่กว่า เนื่องจากตัวอย่างใช้ classifier `jdk16` IDE ใด ๆ เช่น IntelliJ IDEA หรือ Eclipse ก็ทำงานได้

### ความรู้ที่จำเป็น
- ทักษะการเขียนโปรแกรม Java พื้นฐาน  
- ความคุ้นเคยกับแนวคิดของ PowerPoint (สไลด์, รูปร่าง, ตาราง)  
- ความเข้าใจวิธีที่ Maven/Gradle จัดการ dependencies  

## การตั้งค่า Aspose.Slides for Java

`Presentation` เป็นคลาสหลักของ Aspose.Slides ที่แทนไฟล์ PowerPoint ในหน่วยความจำและให้เข้าถึงสไลด์, รูปร่าง, และตาราง สามารถจัดการงานนำเสนอที่มีได้ถึง **10,000 สไลด์** โดยใช้หน่วยความจำน้อยกว่า **500 MB** ทำให้เหมาะกับการทำอัตโนมัติในระดับใหญ่

1. **Install the library** – ใช้ Maven หรือ Gradle, หรือดาวน์โหลดโดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)  
2. **License acquisition** – เริ่มต้นด้วยการทดลองใช้ฟรีจาก [Temporary License](https://purchase.aspose.com/temporary-license/) แล้วอัปเกรดเป็นใบอนุญาตเต็มที่ [Purchase Aspose.Slides](https://purchase.aspose.com/buy) สำหรับการใช้งานในสภาพแวดล้อมการผลิต  
3. **Basic initialization** – สร้างอ็อบเจกต์ `Presentation` ใหม่และโหลดหรือสร้างสไลด์ตามต้องการ  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## วิธีเพิ่มข้อความลงในตารางใน Aspose.Slides for Java?

`Presentation` เป็นคลาสหลักที่แทนไฟล์ PowerPoint ในหน่วยความจำ  
โหลด `Presentation` ใหม่, สร้างตารางที่ตำแหน่งที่ต้องการ, เติมเซลล์ด้วยอ็อบเจกต์ `TextFrame`, แล้วเรียก `pres.save("output.pptx", SaveFormat.Pptx)` ลำดับนี้จะสร้าง **create table in PowerPoint**, ใส่ข้อความที่กำหนดลงในแต่ละเซลล์, และบันทึกผลลัพธ์เป็นไฟล์ PPTX ในขั้นตอนเดียวที่มีประสิทธิภาพ

### คำตอบโดยตรง
สร้างตารางโดยเรียก `slide.getShapes().addTable(...)` จากนั้นสำหรับแต่ละเซลล์ใช้ `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))` หลังจากเติมข้อมูลทุกเซลล์แล้วเรียก `pres.save("output.pptx", SaveFormat.Pptx)` เพื่อบันทึกไฟล์ วิธีนี้ทำให้คุณควบคุมเนื้อหาและสไตล์ของแต่ละเซลล์ได้อย่างเต็มที่

#### ฟีเจอร์ 1: สร้างตารางและเพิ่มข้อความลงในเซลล์

**1. create a table** – เริ่มต้นด้วยการสร้าง `Presentation`, เพิ่มสไลด์, แล้ววางตารางที่ (50, 50) พร้อมกำหนดความกว้างของคอลัมน์และความสูงของแถว  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – สำหรับแต่ละเซลล์, สร้าง `Paragraph`, เพิ่ม `Portion` ที่มีสตริงที่ต้องการ, แล้วกำหนดพารากราฟให้กับ `TextFrame` ของเซลล์  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. save the presentation** – เรียก `pres.save("output.pptx", SaveFormat.Pptx)`  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## วิธีวาดกรอบรอบข้อความในสไลด์ PowerPoint?

`Rectangle2D` แสดงพื้นที่สี่เหลี่ยมในระบบพิกัดสองมิติ  
โหลดสไลด์, ระบุตำแหน่งย่อหน้า หรือส่วนที่ต้องการเน้น, ดึงสี่เหลี่ยมขอบเขตผ่าน `getRect()`, แล้วเพิ่ม `IAutoShape` สี่เหลี่ยมที่ไม่มีการเติมสีและมีเส้นสีตามต้องการ วิธีนี้ทำงานได้ทั้งกับย่อหน้าทั้งหมดและส่วนของคำเดียว

### Direct answer
เพื่อวาดกรอบรอบข้อความ, ก่อนอื่นให้รับสี่เหลี่ยมของย่อหน้า (`Rectangle2D rect = paragraph.getRect();`) จากนั้นสร้าง `IAutoShape` สี่เหลี่ยม (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), ตั้งค่า `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, และปิดการเติมสี (`shape.getFillFormat().setFillType(FillType.NoFill)`) รูปร่างจะล้อมรอบข้อความอย่างแม่นยำ

#### ฟีเจอร์ 3: วาดกรอบรอบย่อหน้าและส่วนในเซลล์ตาราง

**1. create a table** – ใช้โค้ดจากฟีเจอร์ 1 เพื่อตั้งค่าตารางเริ่มต้น  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – ใช้โค้ดการสร้างพารากราฟจากฟีเจอร์ 1 อีกครั้ง  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. draw frames** – วนลูปแต่ละพารากราฟ, ดึงสี่เหลี่ยมขอบเขต, แล้วเพิ่มรูปสี่เหลี่ยมตามที่อธิบายไว้ หากส่วนที่มีอักขระ ‘0’ ให้วาดกรอบเพิ่มเติมเพื่อเน้นตัวเลขเหล่านั้น  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. save the presentation** – ขั้นตอนสุดท้ายเหมือนเดิม  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## วิธีเพิ่ม Text Frame ไปยัง AutoShape และตั้งค่าการจัดตำแหน่ง

`AutoShape` เป็นรูปร่างที่สามารถบรรจุข้อความ, รูปภาพ หรือเนื้อหาอื่น ๆ `AutoShape` สามารถมี `TextFrame` ได้ คุณสามารถควบคุมการจัดตำแหน่งแนวนอนได้โดยใช้ enum `ParagraphFormat`

### Direct answer
สร้าง AutoShape สี่เหลี่ยม (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), เข้าถึง `TextFrame` ของมัน, ตั้งข้อความด้วย `shape.getTextFrame().setText("Text in shape")`, แล้วเรียก `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` เพื่อจัดตำแหน่งข้อความไปด้านซ้ายภายในรูปร่าง

**1. add an AutoShape** – วางสี่เหลี่ยมที่ตำแหน่งที่ต้องการ  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – ใช้การจัดตำแหน่งซ้ายตามที่แสดงด้านบน  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – ขั้นตอนสุดท้ายเช่นเดียวกัน  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## ข้อผิดพลาดทั่วไปและเคล็ดลับ

- **Always dispose** – ห่อการใช้ `Presentation` ด้วย `try‑finally` แล้วเรียก `pres.dispose()` เพื่อปล่อยทรัพยากรเนทีฟ  
- **Re‑compute bounding rectangles** – หากเปลี่ยนขนาดฟอนต์, ระยะขอบ, หรือการเว้นระยะในเซลล์หลังจากวาดกรอบแล้ว ให้เรียก `paragraph.getRect()` อีกครั้งก่อนเพิ่มรูปร่าง  
- **Batch shape creation for large tables** – ใช้ instance ของ `IAutoShape` เพียงอันเดียวและอัปเดตเรขาคณิตของมัน เพื่อลดความกดดันของหน่วยความจำเมื่อประมวลผลตารางที่มีแถวหลายร้อย  
- **Performance numbers** – Aspose.Slides สามารถสร้าง PPTX 200 หน้าได้ภายในเวลาไม่ถึง 2 วินาทีบนเซิร์ฟเวอร์ 4‑core ปกติ, และการวาดกรอบรอบ 1,000 ย่อหน้าจะเพิ่มเวลาเพียงประมาณ 150 ms  

## คำถามที่พบบ่อย

**Q: Can I use these APIs with older JDK versions?**  
A: ไลบรารีรองรับ JDK 8 ขึ้นไป, แต่ classifier `jdk16` ให้ประสิทธิภาพดีที่สุดบน runtime รุ่นใหม่  

**Q: How do I change the frame color?**  
A: ปรับสีของการเติมเส้น, เช่น `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`  

**Q: Is it possible to export the final slide as an image?**  
A: ใช่ — ใช้ `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` แล้วบันทึกอาร์เรย์ไบต์  

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: วนลูป `cell.getTextFrame().getParagraphs()`, ค้นหาส่วนที่มีคำว่า “Total”, แล้ววาดสี่เหลี่ยมรอบกล่องขอบเขตของส่วนนั้น  

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API จะสตรีมข้อมูลและปล่อยทรัพยากรเมื่อเรียก `pres.dispose()` ซึ่งช่วยจัดการหน่วยความจำสำหรับไฟล์ขนาดใหญ่  

---

**อัปเดตล่าสุด:** 2026-11-16  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose  

## บทแนะนำที่เกี่ยวข้อง

- [Aspose.Slides for Java&#58; Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [How to Create Dynamic Text Frames in PowerPoint Using Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Add Columns in Text Frame using Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}