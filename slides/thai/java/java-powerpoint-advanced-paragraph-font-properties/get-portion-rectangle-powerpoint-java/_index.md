---
"description": "เรียนรู้วิธีการรับส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนแบบทีละขั้นตอนโดยละเอียดนี้ เหมาะสำหรับนักพัฒนา Java"
"linktitle": "รับส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint ด้วย Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รับส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint ด้วย Java"
"url": "/th/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รับส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint ด้วย Java

## การแนะนำ
การสร้างงานนำเสนอแบบไดนามิกใน Java เป็นเรื่องง่ายด้วย Aspose.Slides สำหรับ Java ในบทช่วยสอนนี้ เราจะเจาะลึกรายละเอียดเกี่ยวกับการสร้างส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint โดยใช้ Aspose.Slides เราจะครอบคลุมทุกอย่างตั้งแต่การตั้งค่าสภาพแวดล้อมไปจนถึงการแยกย่อยโค้ดทีละขั้นตอน ดังนั้นมาเริ่มกันเลย!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นเขียนโค้ด เรามาตรวจสอบก่อนว่าคุณมีทุกสิ่งที่จำเป็นเพื่อให้ทำตามได้อย่างราบรื่น:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 8 ขึ้นไปบนเครื่องของคุณ
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): Eclipse, IntelliJ IDEA หรือ Java IDE อื่น ๆ ที่คุณเลือก
4. ความรู้พื้นฐานเกี่ยวกับ Java: ความเข้าใจในการเขียนโปรแกรม Java เป็นสิ่งสำคัญ
## แพ็คเกจนำเข้า
ขั้นแรกเลย เรามาทำการนำเข้าแพ็คเกจที่จำเป็นกันก่อน ซึ่งรวมถึง Aspose.Slides และแพ็คเกจอื่นๆ อีกสองสามตัวเพื่อจัดการงานของเราอย่างมีประสิทธิภาพ
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
ขั้นตอนแรกคือการสร้างงานนำเสนอใหม่ ซึ่งจะเป็นพื้นที่สำหรับการทำงานของเรา
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: การสร้างตาราง
ตอนนี้เรามาเพิ่มตารางลงในสไลด์แรกของการนำเสนอกัน ตารางนี้จะมีเซลล์ที่เราจะเพิ่มข้อความลงไป
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## ขั้นตอนที่ 3: การเพิ่มย่อหน้าลงในเซลล์
ขั้นต่อไป เราจะสร้างย่อหน้าและเพิ่มย่อหน้าเหล่านี้ลงในเซลล์เฉพาะในตาราง ซึ่งต้องล้างข้อความที่มีอยู่แล้ว จากนั้นจึงเพิ่มย่อหน้าใหม่
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
## ขั้นตอนที่ 4: การเพิ่มกรอบข้อความลงในรูปร่างอัตโนมัติ
เพื่อให้การนำเสนอของเรามีความไดนามิกมากขึ้น เราจะเพิ่มกรอบข้อความลงใน AutoShape และตั้งค่าการจัดตำแหน่ง
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## ขั้นตอนที่ 5: การคำนวณพิกัด
เราจำเป็นต้องได้รับพิกัดของมุมซ้ายบนของเซลล์ตาราง ซึ่งจะช่วยให้เราวางรูปทรงต่างๆ ได้อย่างแม่นยำ
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## ขั้นตอนที่ 6: การเพิ่มเฟรมให้กับย่อหน้าและส่วนต่างๆ
การใช้ `IParagraph.getRect()` และ `IPortion.getRect()` วิธีการนี้ เราสามารถเพิ่มกรอบให้กับย่อหน้าและส่วนต่างๆ ได้ ซึ่งเกี่ยวข้องกับการวนซ้ำผ่านย่อหน้าและส่วนต่างๆ การสร้างรูปร่างรอบๆ ย่อหน้าและส่วนต่างๆ และการปรับแต่งลักษณะที่ปรากฏของย่อหน้าและส่วนต่างๆ
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
## ขั้นตอนที่ 7: การเพิ่มเฟรมลงในย่อหน้า AutoShape
ในทำนองเดียวกันเราจะเพิ่มเฟรมให้กับย่อหน้าใน AutoShape ของเรา เพื่อเพิ่มความน่าสนใจทางภาพของงานนำเสนอ
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
สุดท้ายเราจะบันทึกการนำเสนอของเราไปยังเส้นทางที่ระบุ
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 9: การทำความสะอาด
ถือเป็นแนวทางปฏิบัติที่ดีในการกำจัดวัตถุการนำเสนอเพื่อปลดปล่อยทรัพยากร
```java
if (pres != null) pres.dispose();
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการรับส่วนสี่เหลี่ยมผืนผ้าใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ไลบรารีอันทรงพลังนี้เปิดโลกแห่งความเป็นไปได้ในการสร้างการนำเสนอแบบไดนามิกและดึงดูดสายตาด้วยโปรแกรม เจาะลึก Aspose.Slides และสำรวจฟีเจอร์เพิ่มเติมเพื่อปรับปรุงการนำเสนอของคุณให้ดียิ่งขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ คุณสามารถซื้อใบอนุญาตได้จาก [ที่นี่](https://purchase-aspose.com/buy).
### มี Aspose.Slides สำหรับ Java ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
เอกสารประกอบมีให้ใช้งาน [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถรับการสนับสนุนจากฟอรั่ม Aspose [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}