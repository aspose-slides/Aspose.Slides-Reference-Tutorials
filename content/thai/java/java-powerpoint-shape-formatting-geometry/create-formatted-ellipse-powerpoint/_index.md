---
title: สร้างวงรีที่จัดรูปแบบใน PowerPoint
linktitle: สร้างวงรีที่จัดรูปแบบใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างวงรีที่จัดรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดของเรา
type: docs
weight: 17
url: /th/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---
## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการสร้างวงรีที่จัดรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีที่ทรงพลังที่ช่วยให้นักพัฒนาสามารถจัดการไฟล์ PowerPoint โดยทางโปรแกรม ไม่ว่าคุณจะสร้างสไลด์อัตโนมัติหรือปรับปรุงการนำเสนอด้วยรูปร่างที่กำหนดเอง คู่มือนี้จะแนะนำคุณในทุกขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถเพิ่มวงรีที่มีรูปแบบสมบูรณ์แบบให้กับสไลด์ของคุณได้อย่างง่ายดาย มาเจาะลึกและดูว่าเราจะบรรลุเป้าหมายนี้ได้อย่างไร!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 1.6 ขึ้นไป
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse
4. ความรู้พื้นฐานของ Java: จำเป็นต้องมีความคุ้นเคยกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
หากต้องการเริ่มใช้ Aspose.Slides คุณจะต้องนำเข้าแพ็คเกจที่จำเป็น ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก คุณต้องมีไดเร็กทอรีเพื่อจัดเก็บไฟล์ PowerPoint ของคุณ
### สร้างไดเรกทอรี
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 ให้แน่ใจว่าคุณเปลี่ยน`"Your Document Directory"` ด้วยเส้นทางจริงที่คุณต้องการจัดเก็บไฟล์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ตอนนี้ สร้างอินสแตนซ์คลาสการนำเสนอซึ่งแสดงถึงไฟล์ PowerPoint
```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึง PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: รับสไลด์แรก
จากนั้น รับสไลด์แรกจากงานนำเสนอที่คุณจะเพิ่มวงรี
```java
// รับสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างวงรี
เพิ่มรูปร่างอัตโนมัติของประเภทวงรีลงในสไลด์
```java
// เพิ่มรูปร่างอัตโนมัติของประเภทวงรี
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 ที่นี่,`50, 150, 150, 50` คือพิกัดและขนาดของวงรี (ตำแหน่ง x, ตำแหน่ง y, ความกว้าง, ความสูง)
## ขั้นตอนที่ 5: ใช้การจัดรูปแบบกับวงรี
ตอนนี้ ใช้การจัดรูปแบบบางอย่างกับวงรี เราจะตั้งค่าสีเติมแบบทึบและสีของเส้น
### ตั้งค่าสีเติม
```java
// ใช้การจัดรูปแบบบางอย่างกับรูปร่างวงรี
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### กำหนดสีเส้นและความกว้าง
```java
// ใช้การจัดรูปแบบบางอย่างกับเส้นวงรี
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอลงในไดเร็กทอรีที่คุณระบุ
```java
// เขียนไฟล์ PPTX ลงดิสก์
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: กำจัดวัตถุการนำเสนอ
กำจัดวัตถุการนำเสนอเพื่อเพิ่มทรัพยากร
```java
finally {
    if (pres != null) pres.dispose();
}
```
## บทสรุป
ยินดีด้วย! คุณสร้างวงรีที่จัดรูปแบบแล้วในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว บทช่วยสอนนี้จะอธิบายการตั้งค่าโปรเจ็กต์ของคุณ การเพิ่มวงรี การใช้การจัดรูปแบบ และการบันทึกงานนำเสนอของคุณ ด้วยทักษะเหล่านี้ คุณสามารถปรับปรุงสไลด์ PowerPoint ของคุณโดยทางโปรแกรมได้ ทำให้การนำเสนอของคุณมีความไดนามิกและดึงดูดสายตามากขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ใด ๆ ได้หรือไม่
ได้ คุณสามารถใช้ Aspose.Slides สำหรับ Java กับ Java IDE ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### ฉันต้องมีใบอนุญาตสำหรับ Aspose.Slides หรือไม่
 ใช่ Aspose.Slides เป็นผลิตภัณฑ์เชิงพาณิชย์ และคุณต้องมีใบอนุญาตจึงจะใช้งานได้เต็มรูปแบบ คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถดูเอกสารโดยละเอียดได้ที่ Aspose.Slides สำหรับ Java[หน้าเอกสาร](https://reference.aspose.com/slides/java/).
### มีการรองรับ Aspose.Slides หรือไม่
 ใช่ Aspose ให้การสนับสนุนผ่านทางพวกเขา[ฟอรั่ม](https://forum.aspose.com/c/slides/11).