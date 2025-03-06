---
title: ผสานเซลล์ในตาราง PowerPoint ด้วย Java
linktitle: ผสานเซลล์ในตาราง PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีผสานเซลล์ในตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงเค้าโครงการนำเสนอของคุณด้วยคำแนะนำทีละขั้นตอนนี้
weight: 17
url: /th/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีผสานเซลล์ภายในตาราง PowerPoint อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม ด้วยการผสานเซลล์ในตาราง คุณสามารถปรับแต่งเค้าโครงและโครงสร้างของสไลด์การนำเสนอของคุณได้ เพิ่มความชัดเจนและดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนเครื่องของคุณ
- IDE (สภาพแวดล้อมการพัฒนาแบบรวม) เช่น IntelliJ IDEA หรือ Eclipse
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่ม Aspose.Slides สำหรับไลบรารี Java ไปยังการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์ PPTX ที่คุณกำลังทำงานด้วย:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์
เข้าถึงสไลด์ที่คุณต้องการเพิ่มตาราง ตัวอย่างเช่น หากต้องการเข้าถึงสไลด์แรก:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: กำหนดขนาดตาราง
 กำหนดคอลัมน์และแถวสำหรับตารางของคุณ ระบุความกว้างของคอลัมน์และความสูงของแถวเป็นอาร์เรย์ของ`double`-
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างตารางเพื่อเลื่อน
เพิ่มรูปร่างตารางลงในสไลด์โดยใช้ขนาดที่กำหนด:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 6: ปรับแต่งเส้นขอบเซลล์
กำหนดรูปแบบเส้นขอบสำหรับแต่ละเซลล์ในตาราง ตัวอย่างนี้ตั้งค่าเส้นขอบทึบสีแดงที่มีความกว้าง 5 สำหรับแต่ละเซลล์:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // กำหนดรูปแบบเส้นขอบให้กับแต่ละด้านของเซลล์
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## ขั้นตอนที่ 7: รวมเซลล์ในตาราง
 หากต้องการผสานเซลล์ในตาราง ให้ใช้`mergeCells` วิธี. ตัวอย่างนี้จะผสานเซลล์จาก (1, 1) ถึง (2, 1) และจาก (1, 2) ถึง (2, 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ PPTX บนดิสก์ของคุณ:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณได้เรียนรู้วิธีผสานเซลล์ภายในตาราง PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้สำเร็จ เทคนิคนี้ช่วยให้คุณสร้างงานนำเสนอที่ซับซ้อนและดึงดูดสายตามากขึ้นโดยทางโปรแกรม ซึ่งช่วยเพิ่มประสิทธิภาพการทำงานและตัวเลือกการปรับแต่งของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java คือ Java API สำหรับการสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากฟอรัมชุมชน Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
