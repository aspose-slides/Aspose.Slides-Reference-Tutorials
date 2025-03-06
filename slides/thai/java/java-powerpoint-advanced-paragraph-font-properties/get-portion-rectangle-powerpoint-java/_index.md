---
title: รับสี่เหลี่ยมผืนผ้าส่วนใน PowerPoint ด้วย Java
linktitle: รับสี่เหลี่ยมผืนผ้าส่วนใน PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีรับสี่เหลี่ยมส่วนใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมบทช่วยสอนแบบละเอียดทีละขั้นตอนนี้ เหมาะสำหรับนักพัฒนา Java
weight: 12
url: /th/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับสี่เหลี่ยมผืนผ้าส่วนใน PowerPoint ด้วย Java

## การแนะนำ
การสร้างงานนำเสนอแบบไดนามิกใน Java เป็นเรื่องง่ายด้วย Aspose.Slides สำหรับ Java ในบทช่วยสอนนี้ เราจะเจาะลึกรายละเอียดสำคัญของการหาส่วนสี่เหลี่ยมใน PowerPoint โดยใช้ Aspose.Slides เราจะครอบคลุมทุกอย่างตั้งแต่การตั้งค่าสภาพแวดล้อมไปจนถึงการแจกแจงโค้ดทีละขั้นตอน เอาล่ะ มาเริ่มกันเลย!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะพูดถึงโค้ด เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่จำเป็นในการปฏิบัติตามได้อย่างราบรื่น:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 8 ขึ้นไปบนเครื่องของคุณ
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): Eclipse, IntelliJ IDEA หรือ Java IDE อื่นๆ ที่คุณเลือก
4. ความรู้พื้นฐานของ Java: ความเข้าใจในการเขียนโปรแกรม Java เป็นสิ่งสำคัญ
## แพ็คเกจนำเข้า
ก่อนอื่น เรามานำเข้าแพ็คเกจที่จำเป็นกันก่อน ซึ่งจะรวมถึง Aspose.Slides และอื่นๆ อีกสองสามรายการเพื่อจัดการงานของเราอย่างมีประสิทธิภาพ
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
ขั้นตอนแรกคือการสร้างงานนำเสนอใหม่ นี่จะเป็นผืนผ้าใบของเราในการทำงาน
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: การสร้างตาราง
ตอนนี้ เรามาเพิ่มตารางลงในสไลด์แรกของงานนำเสนอของเรากันดีกว่า ตารางนี้จะมีเซลล์ที่เราจะเพิ่มข้อความของเรา
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## ขั้นตอนที่ 3: การเพิ่มย่อหน้าลงในเซลล์
ต่อไป เราจะสร้างย่อหน้าและเพิ่มลงในเซลล์เฉพาะในตาราง ซึ่งเกี่ยวข้องกับการล้างข้อความที่มีอยู่แล้วเพิ่มย่อหน้าใหม่
```java
// สร้างย่อหน้า
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// เพิ่มข้อความลงในเซลล์ตาราง
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## ขั้นตอนที่ 4: การเพิ่มกรอบข้อความให้กับรูปร่างอัตโนมัติ
เพื่อให้การนำเสนอของเรามีไดนามิกมากขึ้น เราจะเพิ่มกรอบข้อความให้กับรูปร่างอัตโนมัติและตั้งค่าการจัดตำแหน่ง
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## ขั้นตอนที่ 5: การคำนวณพิกัด
เราจำเป็นต้องได้รับพิกัดที่มุมบนซ้ายของเซลล์ตาราง ซึ่งจะช่วยให้เราวางรูปทรงได้แม่นยำ
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## ขั้นตอนที่ 6: การเพิ่มเฟรมให้กับย่อหน้าและส่วนต่างๆ
 ใช้`IParagraph.getRect()` และ`IPortion.getRect()`เราสามารถเพิ่มเฟรมให้กับย่อหน้าและส่วนต่างๆ ของเราได้ ซึ่งเกี่ยวข้องกับการวนซ้ำย่อหน้าและส่วนต่างๆ การสร้างรูปร่างรอบๆ และปรับแต่งลักษณะที่ปรากฏ
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## ขั้นตอนที่ 7: การเพิ่มเฟรมให้กับย่อหน้ารูปร่างอัตโนมัติ
ในทำนองเดียวกัน เราจะเพิ่มเฟรมให้กับย่อหน้าในรูปร่างอัตโนมัติของเรา เพื่อเพิ่มความน่าดึงดูดทางสายตาของงานนำเสนอ
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
สุดท้าย เราจะบันทึกการนำเสนอของเราไปยังเส้นทางที่ระบุ
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 9: การทำความสะอาด
แนวทางปฏิบัติที่ดีคือการกำจัดออบเจ็กต์การนำเสนอเพื่อเพิ่มทรัพยากร
```java
if (pres != null) pres.dispose();
```
## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีรับสี่เหลี่ยมส่วนใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว ไลบรารีอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้ในการสร้างงานนำเสนอแบบไดนามิกและดึงดูดสายตาโดยทางโปรแกรม เจาะลึก Aspose.Slides และสำรวจคุณสมบัติเพิ่มเติมเพื่อปรับปรุงการนำเสนอของคุณให้ดียิ่งขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ได้ Aspose.Slides สำหรับ Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัม Aspose[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
