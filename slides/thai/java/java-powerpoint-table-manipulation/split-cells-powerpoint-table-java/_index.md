---
title: แยกเซลล์ในตาราง PowerPoint โดยใช้ Java
linktitle: แยกเซลล์ในตาราง PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแยก ผสาน และจัดรูปแบบเซลล์ตาราง PowerPoint โดยทางโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java การออกแบบการนำเสนอระดับปริญญาโท
weight: 11
url: /th/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดการตาราง PowerPoint ใน Java โดยใช้ Aspose.Slides ตารางเป็นองค์ประกอบพื้นฐานในการนำเสนอ ซึ่งมักใช้เพื่อจัดระเบียบและนำเสนอข้อมูลอย่างมีประสิทธิภาพ Aspose.Slides มอบความสามารถที่แข็งแกร่งในการสร้าง แก้ไข และปรับปรุงตารางโดยทางโปรแกรม โดยให้ความยืดหยุ่นในการออกแบบและเค้าโครง
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนเครื่องของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- Integrated Development Environment (IDE) เช่น Eclipse, IntelliJ IDEA หรืออื่นๆ ที่คุณเลือก

## แพ็คเกจนำเข้า
หากต้องการเริ่มทำงานกับ Aspose.Slides สำหรับ Java คุณต้องนำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
 ขั้นแรก ให้ยกตัวอย่าง`Presentation` คลาสเพื่อสร้างงานนำเสนอ PowerPoint ใหม่
```java
// เส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอเอาต์พุต
String dataDir = "Your_Document_Directory/";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
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
    // เพิ่มรูปทรงตารางเพื่อสไลด์
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 3: การตั้งค่ารูปแบบเส้นขอบสำหรับแต่ละเซลล์
วนซ้ำแต่ละเซลล์ในตารางและตั้งค่าการจัดรูปแบบเส้นขอบ (สี ความกว้าง ฯลฯ)
```java
    // กำหนดรูปแบบเส้นขอบสำหรับแต่ละเซลล์
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // ตั้งค่าการจัดรูปแบบที่คล้ายกันสำหรับเส้นขอบอื่นๆ (ล่าง ซ้าย ขวา)
            // -
        }
    }
```
## ขั้นตอนที่ 4: การรวมเซลล์
ผสานเซลล์ในตารางตามต้องการ ตัวอย่างเช่น ผสานเซลล์ (1,1) ถึง (2,1) และ (1,2) ถึง (2,2)
```java
    // การรวมเซลล์ (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // การรวมเซลล์ (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## ขั้นตอนที่ 5: การแยกเซลล์
แบ่งเซลล์หนึ่งๆ ออกเป็นหลายเซลล์ตามความกว้าง
```java
    // แยกเซลล์ (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขลงในดิสก์
```java
    // เขียน PPTX ลงดิสก์
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // กำจัดวัตถุการนำเสนอ
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
การจัดการตาราง PowerPoint โดยทางโปรแกรมโดยใช้ Aspose.Slides สำหรับ Java มอบวิธีที่มีประสิทธิภาพในการปรับแต่งงานนำเสนออย่างมีประสิทธิภาพ เมื่อทำตามบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีแบ่งเซลล์ ผสานเซลล์ และตั้งค่าเส้นขอบเซลล์แบบไดนามิก ช่วยเพิ่มความสามารถในการสร้างงานนำเสนอที่ดึงดูดสายตาโดยทางโปรแกรม

## คำถามที่พบบ่อย
### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาเอกสาร[ที่นี่](https://reference.aspose.com/slides/java/).
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดได้จาก[ลิงค์นี้](https://releases.aspose.com/slides/java/).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจากฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้หรือไม่
 ใช่ คุณสามารถรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
