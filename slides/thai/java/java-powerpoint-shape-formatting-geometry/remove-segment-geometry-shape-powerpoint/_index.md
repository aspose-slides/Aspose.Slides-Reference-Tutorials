---
title: ลบส่วนออกจากรูปทรงเรขาคณิตใน PowerPoint
linktitle: ลบส่วนออกจากรูปทรงเรขาคณิตใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีลบส่วนออกจากรูปทรงเรขาคณิตใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดของเรา
weight: 22
url: /th/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
คุณต้องการจัดการรูปร่างในงานนำเสนอ PowerPoint ของคุณโดยใช้ Java หรือไม่? คุณมาถูกที่แล้ว! Aspose.Slides for Java เป็น API ที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถสร้าง แก้ไข และจัดการสไลด์ในงานนำเสนอของคุณได้อย่างง่ายดาย ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการลบส่วนออกจากรูปทรงเรขาคณิตใน PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คู่มือนี้จะให้แนวทางแบบทีละขั้นตอนในการเรียนรู้งานนี้ให้เชี่ยวชาญ พร้อมที่จะดำน้ำแล้วหรือยัง? มาเริ่มกันเลย!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเขียนและรันโค้ด Java ของคุณ
4. ความรู้พื้นฐานของ Java: ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java จะช่วยให้คุณปฏิบัติตามบทช่วยสอนนี้
## แพ็คเกจนำเข้า
ในการเริ่มต้น เราต้องนำเข้าแพ็คเกจที่จำเป็นจากไลบรารี Aspose.Slides นี่คือวิธีการ:
```java
import com.aspose.slides.*;

```
เรามาแจกแจงขั้นตอนการลบส่วนออกจากรูปทรงเรขาคณิตในสไลด์ PowerPoint ออกเป็นหลายขั้นตอน
## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่
ขั้นแรก เราต้องสร้างวัตถุการนำเสนอใหม่ วัตถุนี้จะทำหน้าที่เป็นที่เก็บสไลด์และรูปร่างของเรา
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 2: เพิ่มรูปทรงเรขาคณิตให้กับสไลด์
จากนั้น เพิ่มรูปทรงเรขาคณิตให้กับสไลด์ สำหรับตัวอย่างนี้ เราจะใช้รูปหัวใจ
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## ขั้นตอนที่ 3: ดึงเส้นทางเรขาคณิตของรูปร่าง
เมื่อเพิ่มรูปร่างแล้ว เราจำเป็นต้องดึงข้อมูลเส้นทางเรขาคณิตของมัน เส้นทางเรขาคณิตมีส่วนที่กำหนดรูปร่าง
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## ขั้นตอนที่ 4: ลบส่วนออกจากเส้นทางเรขาคณิต
ตอนนี้ เราจะลบส่วนใดส่วนหนึ่งออกจากเส้นทางเรขาคณิต ในตัวอย่างนี้ เราลบส่วนที่ดัชนี 2 ออก
```java
path.removeAt(2);
```
## ขั้นตอนที่ 5: ตั้งค่าเส้นทางเรขาคณิตใหม่
หลังจากลบส่วนออกแล้ว ให้ตั้งค่าเส้นทางเรขาคณิตที่แก้ไขแล้วกลับไปเป็นรูปร่าง
```java
shape.setGeometryPath(path);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: ทำความสะอาดทรัพยากร
ตรวจสอบให้แน่ใจว่าคุณล้างทรัพยากรอยู่เสมอเพื่อป้องกันหน่วยความจำรั่ว
```java
if (pres != null) pres.dispose();
```
## บทสรุป
และคุณก็ได้แล้ว! ด้วย Aspose.Slides สำหรับ Java การจัดการรูปร่างในงานนำเสนอ PowerPoint ของคุณจึงตรงไปตรงมาและมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถลบส่วนต่างๆ ออกจากรูปทรงเรขาคณิตได้อย่างง่ายดาย ทำให้คุณควบคุมการออกแบบและฟังก์ชันการทำงานของสไลด์ได้ดียิ่งขึ้น ขอให้มีความสุขในการเขียนโค้ด!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพสำหรับการสร้าง ปรับเปลี่ยน และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับรูปทรงอื่นนอกเหนือจากรูปหัวใจได้หรือไม่
อย่างแน่นอน! Aspose.Slides สำหรับ Java รองรับรูปร่างที่หลากหลายซึ่งคุณสามารถจัดการได้
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณต้องมีใบอนุญาตเพื่อการใช้งานเต็มรูปแบบ คุณสามารถซื้อได้[ที่นี่](https://purchase.aspose.com/buy) หรือได้รับใบอนุญาตชั่วคราว[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 มีเอกสารประกอบครบถ้วน[ที่นี่](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
