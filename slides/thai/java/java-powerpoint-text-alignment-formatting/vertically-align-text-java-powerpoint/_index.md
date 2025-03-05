---
title: จัดแนวข้อความในแนวตั้งใน Java PowerPoint
linktitle: จัดแนวข้อความในแนวตั้งใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดแนวข้อความในงานนำเสนอ Java PowerPoint ในแนวตั้งโดยใช้ Aspose.Slides เพื่อการจัดรูปแบบสไลด์ที่ราบรื่น
type: docs
weight: 10
url: /th/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดแนวข้อความในแนวตั้งภายในเซลล์ตารางในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การจัดแนวข้อความในแนวตั้งเป็นส่วนสำคัญของการออกแบบสไลด์ เพื่อให้มั่นใจว่าเนื้อหาของคุณจะถูกนำเสนออย่างเรียบร้อยและเป็นมืออาชีพ Aspose.Slides มอบคุณสมบัติอันทรงพลังในการจัดการและจัดรูปแบบการนำเสนอโดยทางโปรแกรม ทำให้คุณควบคุมทุกแง่มุมของสไลด์ได้อย่างเต็มที่
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง JDK (Java Development Kit) บนเครื่องของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ติดตั้ง IDE (Integrated Development Environment) เช่น IntelliJ IDEA หรือ Eclipse แล้ว

## แพ็คเกจนำเข้า
ก่อนดำเนินการบทช่วยสอน โปรดแน่ใจว่าได้นำเข้าแพ็คเกจ Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโปรเจ็กต์ Java ของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides ลงในพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
 สร้างอินสแตนซ์ของ`Presentation` ชั้นเรียนเพื่อเริ่มทำงานกับงานนำเสนอ PowerPoint ใหม่:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
รับสไลด์แรกจากงานนำเสนอเพื่อเพิ่มเนื้อหาลงไป:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: กำหนดขนาดตารางและเพิ่มตาราง
กำหนดความกว้างของคอลัมน์และความสูงของแถวสำหรับตารางของคุณ จากนั้นเพิ่มรูปร่างตารางลงในสไลด์:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## ขั้นตอนที่ 5: ตั้งค่าเนื้อหาข้อความในเซลล์ตาราง
ตั้งค่าเนื้อหาข้อความสำหรับแถวเฉพาะในตาราง:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## ขั้นตอนที่ 6: เข้าถึงกรอบข้อความและจัดรูปแบบข้อความ
เข้าถึงกรอบข้อความและจัดรูปแบบข้อความภายในเซลล์เฉพาะ:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 7: จัดข้อความในแนวตั้ง
ตั้งค่าการจัดตำแหน่งแนวตั้งสำหรับข้อความภายในเซลล์:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## ขั้นตอนที่ 8: บันทึกงานนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุบนดิสก์ของคุณ:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 9: ทรัพยากรการล้างข้อมูล
 กำจัดของ`Presentation` คัดค้านการปล่อยทรัพยากร:
```java
if (presentation != null) presentation.dispose();
```

## บทสรุป
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดแนวข้อความในแนวตั้งภายในเซลล์ตารางในงานนำเสนอ Java PowerPoint ของคุณได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Slides ความสามารถนี้ช่วยเพิ่มความสวยงามและความชัดเจนให้กับสไลด์ของคุณ ทำให้มั่นใจได้ว่าเนื้อหาของคุณจะถูกนำเสนออย่างมืออาชีพ

## คำถามที่พบบ่อย
### ฉันสามารถจัดแนวข้อความในรูปร่างอื่นนอกเหนือจากตารางในแนวตั้งได้หรือไม่
ใช่ Aspose.Slides มีวิธีการจัดแนวข้อความในแนวตั้งในรูปทรงต่างๆ รวมถึงกล่องข้อความและตัวยึดตำแหน่ง
### Aspose.Slides รองรับการจัดแนวข้อความในแนวนอนด้วยหรือไม่
ใช่ คุณสามารถจัดแนวข้อความในแนวนอนได้โดยใช้ตัวเลือกการจัดตำแหน่งต่างๆ ที่ Aspose.Slides มอบให้
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับการสร้างงานนำเสนอที่เข้ากันได้กับ Microsoft PowerPoint เวอร์ชันหลักทั้งหมด
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยมชม[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำที่ครอบคลุม ข้อมูลอ้างอิง API และตัวอย่างโค้ด
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้อย่างไร
 สำหรับความช่วยเหลือด้านเทคนิคและการสนับสนุนชุมชน โปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).