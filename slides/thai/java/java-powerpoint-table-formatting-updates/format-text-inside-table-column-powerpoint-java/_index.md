---
title: จัดรูปแบบข้อความภายในคอลัมน์ตารางใน PowerPoint โดยใช้ Java
linktitle: จัดรูปแบบข้อความภายในคอลัมน์ตารางใน PowerPoint โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดรูปแบบข้อความภายในคอลัมน์ตารางใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนนี้ ปรับปรุงการนำเสนอของคุณโดยทางโปรแกรม
weight: 11
url: /th/java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดรูปแบบข้อความภายในคอลัมน์ตารางใน PowerPoint โดยใช้ Java

## การแนะนำ
คุณพร้อมที่จะดำดิ่งสู่โลกแห่งการนำเสนอ PowerPoint แต่มีการเปลี่ยนแปลงแล้วหรือยัง? แทนที่จะจัดรูปแบบสไลด์ด้วยตนเอง ลองใช้เส้นทางที่มีประสิทธิภาพมากขึ้นโดยใช้ Aspose.Slides สำหรับ Java กันดีกว่า บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการจัดรูปแบบข้อความภายในคอลัมน์ตารางในงานนำเสนอ PowerPoint โดยทางโปรแกรม รัดเข็มขัดไว้ เพราะนี่จะเป็นการเดินทางที่สนุก!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม มีบางสิ่งที่คุณต้องการ:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว หากไม่ใช่คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ของออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้เส้นทางการเขียนโค้ดของคุณราบรื่นยิ่งขึ้น
4.  การนำเสนอ PowerPoint: มีไฟล์ PowerPoint พร้อมตารางที่คุณสามารถใช้สำหรับการทดสอบ เราจะเรียกมันว่า`SomePresentationWithTable.pptx`.

## แพ็คเกจนำเข้า
ขั้นแรก มาตั้งค่าโปรเจ็กต์ของคุณและนำเข้าแพ็คเกจที่จำเป็น นี่จะเป็นรากฐานของเราสำหรับบทช่วยสอน
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
ขั้นตอนแรกในการเดินทางของเราคือการโหลดงานนำเสนอ PowerPoint ลงในโปรแกรมของเรา
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
 บรรทัดโค้ดนี้จะสร้างอินสแตนซ์ของ`Presentation` คลาสซึ่งแสดงถึงไฟล์ PowerPoint ของเรา
## ขั้นตอนที่ 2: เข้าถึงสไลด์และตาราง
ต่อไปเราต้องเข้าถึงสไลด์และตารางภายในสไลด์นั้น เพื่อความง่าย สมมติว่าตารางเป็นรูปร่างแรกในสไลด์แรก
### เข้าถึงสไลด์แรก
```java
ISlide slide = pres.getSlides().get_Item(0);
```
บรรทัดนี้จะดึงข้อมูลสไลด์แรกจากงานนำเสนอ
### เข้าถึงตาราง
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
ที่นี่ เรากำลังเข้าถึงรูปร่างแรกในสไลด์แรก ซึ่งเราถือว่าเป็นตารางของเรา
## ขั้นตอนที่ 3: ตั้งค่าความสูงของแบบอักษรสำหรับคอลัมน์แรก
ตอนนี้ เรามาตั้งค่าความสูงของแบบอักษรสำหรับข้อความในคอลัมน์แรกของตารางกันดีกว่า
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 ในบรรทัดเหล่านี้ เรากำหนด a`PortionFormat` วัตถุเพื่อตั้งค่าความสูงของแบบอักษรเป็น 25 พอยต์สำหรับคอลัมน์แรก
## ขั้นตอนที่ 4: จัดแนวข้อความไปทางขวา
การจัดแนวข้อความสามารถสร้างความแตกต่างอย่างมากในการอ่านสไลด์ของคุณ มาจัดข้อความชิดขวาในคอลัมน์แรกกัน

```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 ในที่นี้เราใช้ a`ParagraphFormat` วัตถุเพื่อตั้งค่าการจัดแนวข้อความไปทางขวาและเพิ่มระยะขอบขวา 20
## ขั้นตอนที่ 5: ตั้งค่าประเภทข้อความแนวตั้ง
เพื่อให้ข้อความมีการวางแนวที่ไม่ซ้ำใคร เราสามารถตั้งค่าประเภทแนวตั้งของข้อความได้
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
ตัวอย่างนี้ตั้งค่าการวางแนวข้อความเป็นแนวตั้งสำหรับคอลัมน์แรก
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย หลังจากทำการเปลี่ยนแปลงการจัดรูปแบบทั้งหมดแล้ว เราจำเป็นต้องบันทึกงานนำเสนอที่แก้ไข
```java
pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
 คำสั่งนี้จะบันทึกงานนำเสนอด้วยรูปแบบใหม่ที่ใช้กับไฟล์ชื่อ`result.pptx`.

## บทสรุป
ได้แล้ว! คุณเพิ่งจัดรูปแบบข้อความภายในคอลัมน์ตารางในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การทำงานเหล่านี้โดยอัตโนมัติจะช่วยประหยัดเวลาและรับประกันความสอดคล้องในการนำเสนอของคุณ ขอให้มีความสุขในการเขียนโค้ด!
## คำถามที่พบบ่อย
### ฉันสามารถจัดรูปแบบหลายคอลัมน์พร้อมกันได้หรือไม่
ได้ คุณสามารถใช้การจัดรูปแบบเดียวกันกับหลายคอลัมน์ได้โดยการวนซ้ำและตั้งค่ารูปแบบที่ต้องการ
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับรูปแบบ PowerPoint ที่หลากหลาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับเวอร์ชันส่วนใหญ่
### ฉันสามารถเพิ่มการจัดรูปแบบประเภทอื่นโดยใช้ Aspose.Slides ได้หรือไม่
อย่างแน่นอน! Aspose.Slides ช่วยให้มีตัวเลือกการจัดรูปแบบที่หลากหลาย รวมถึงลักษณะแบบอักษร สี และอื่นๆ
### ฉันจะทดลองใช้ Aspose.Slides ฟรีได้อย่างไร
 คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[กำหนดหน้าทดลองใช้ฟรี](https://releases.aspose.com/).
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 ตรวจสอบ[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับตัวอย่างและคำแนะนำโดยละเอียด
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
