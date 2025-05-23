---
"description": "เรียนรู้วิธีแยก รวม และจัดรูปแบบเซลล์ตาราง PowerPoint ด้วยโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java ออกแบบงานนำเสนออย่างมืออาชีพ"
"linktitle": "แบ่งเซลล์ในตาราง PowerPoint โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แบ่งเซลล์ในตาราง PowerPoint โดยใช้ Java"
"url": "/th/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แบ่งเซลล์ในตาราง PowerPoint โดยใช้ Java

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการจัดการตาราง PowerPoint ใน Java โดยใช้ Aspose.Slides ตารางเป็นส่วนประกอบพื้นฐานในงานนำเสนอ ซึ่งมักใช้เพื่อจัดระเบียบและนำเสนอข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides มอบความสามารถที่แข็งแกร่งในการสร้าง แก้ไข และปรับปรุงตารางด้วยโปรแกรม ซึ่งให้ความยืดหยุ่นในการออกแบบและเค้าโครง
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- JDK (Java Development Kit) ติดตั้งอยู่บนเครื่องของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Eclipse, IntelliJ IDEA หรืออื่นๆ ที่คุณเลือก

## แพ็คเกจนำเข้า
ในการเริ่มทำงานกับ Aspose.Slides สำหรับ Java คุณจะต้องนำเข้าแพ็กเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
ขั้นแรก ให้สร้างตัวอย่าง `Presentation` ชั้นเรียนเพื่อสร้างการนำเสนอ PowerPoint ใหม่
```java
// เส้นทางไปยังไดเรกทอรีที่คุณต้องการบันทึกงานนำเสนอผลลัพธ์
String dataDir = "Your_Document_Directory/";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 2: การเข้าถึงสไลด์และการเพิ่มตาราง
เข้าถึงสไลด์แรกและเพิ่มรูปร่างตารางลงไป กำหนดคอลัมน์ที่มีความกว้างและแถวที่มีความสูง
```java
try {
    // เข้าถึงสไลด์แรก
    ISlide slide = presentation.getSlides().get_Item(0);
    // กำหนดคอลัมน์ที่มีความกว้างและแถวที่มีความสูง
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // เพิ่มรูปร่างตารางลงในสไลด์
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 3: ตั้งค่ารูปแบบเส้นขอบสำหรับแต่ละเซลล์
ทำซ้ำผ่านแต่ละเซลล์ในตารางและตั้งค่าการจัดรูปแบบเส้นขอบ (สี ความกว้าง เป็นต้น)
```java
    // ตั้งค่ารูปแบบเส้นขอบสำหรับแต่ละเซลล์
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // ตั้งค่าการจัดรูปแบบที่คล้ายกันสำหรับเส้นขอบอื่นๆ (ด้านล่าง ซ้าย ขวา)
            // -
        }
    }
```
## ขั้นตอนที่ 4: การผสานเซลล์
รวมเซลล์ในตารางตามต้องการ ตัวอย่างเช่น รวมเซลล์ (1,1) กับ (2,1) และ (1,2) กับ (2,2)
```java
    // การรวมเซลล์ (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // การรวมเซลล์ (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## ขั้นตอนที่ 5: การแยกเซลล์
แบ่งเซลล์เฉพาะออกเป็นหลายเซลล์ตามความกว้าง
```java
    // เซลล์แยก (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในดิสก์
```java
    // เขียน PPTX ลงดิสก์
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // กำจัดวัตถุนำเสนอ
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
การจัดการตาราง PowerPoint ด้วยโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java เป็นวิธีที่มีประสิทธิภาพในการปรับแต่งการนำเสนออย่างมีประสิทธิภาพ เมื่อทำตามบทช่วยสอนนี้ คุณจะเรียนรู้วิธีแบ่งเซลล์ รวมเซลล์ และกำหนดขอบเขตเซลล์แบบไดนามิก ซึ่งจะช่วยเพิ่มความสามารถในการสร้างการนำเสนอที่น่าสนใจด้วยโปรแกรม

## คำถามที่พบบ่อย
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารประกอบได้ [ที่นี่](https://reference-aspose.com/slides/java/).
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลดได้จาก [ลิงค์นี้](https://releases-aspose.com/slides/java/).
### มี Aspose.Slides สำหรับ Java ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้จากที่ไหน
คุณสามารถรับการสนับสนุนจากฟอรั่ม Aspose.Slides [ที่นี่](https://forum-aspose.com/c/slides/11).
### ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}