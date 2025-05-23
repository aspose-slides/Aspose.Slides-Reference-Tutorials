---
"description": "เรียนรู้วิธีสร้างวงรีที่มีการจัดรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยคู่มือทีละขั้นตอนโดยละเอียดของเรา"
"linktitle": "สร้างวงรีที่มีรูปแบบใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างวงรีที่มีรูปแบบใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างวงรีที่มีรูปแบบใน PowerPoint

## การแนะนำ
ยินดีต้อนรับสู่บทช่วยสอนที่ครอบคลุมเกี่ยวกับการสร้างวงรีที่จัดรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถจัดการไฟล์ PowerPoint ได้ด้วยโปรแกรม ไม่ว่าคุณจะกำลังสร้างสไลด์อัตโนมัติหรือปรับปรุงการนำเสนอด้วยรูปร่างที่กำหนดเอง คู่มือนี้จะแนะนำคุณในทุกขั้นตอน เพื่อให้แน่ใจว่าคุณสามารถเพิ่มวงรีที่จัดรูปแบบอย่างสมบูรณ์แบบลงในสไลด์ของคุณได้อย่างง่ายดาย มาเริ่มกันเลยและดูว่าเราจะทำได้อย่างไร!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 1.6 ขึ้นไป
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides สำหรับ Java](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse
4. ความรู้พื้นฐานเกี่ยวกับ Java: ต้องมีความคุ้นเคยกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มใช้ Aspose.Slides คุณต้องนำเข้าแพ็คเกจที่จำเป็น โดยคุณสามารถทำได้ดังนี้:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก คุณต้องมีไดเร็กทอรีเพื่อจัดเก็บไฟล์ PowerPoint ของคุณ
### สร้างไดเรกทอรี
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
ให้แน่ใจว่าคุณเปลี่ยน `"Your Document Directory"` ด้วยเส้นทางที่แท้จริงที่คุณต้องการเก็บไฟล์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ตอนนี้ ให้สร้างอินสแตนซ์ของคลาส Presentation ซึ่งแสดงไฟล์ PowerPoint
```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดง PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: รับสไลด์แรก
ขั้นต่อไป ให้รับสไลด์แรกจากการนำเสนอที่คุณจะเพิ่มวงรี
```java
// รับสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปวงรี
เพิ่มรูปร่างอัตโนมัติของประเภทวงรีลงในสไลด์
```java
// เพิ่มรูปร่างอัตโนมัติของชนิดวงรี
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
ที่นี่, `50, 150, 150, 50` คือพิกัดและขนาดของวงรี (ตำแหน่ง x, ตำแหน่ง y, ความกว้าง, ความสูง)
## ขั้นตอนที่ 5: นำการจัดรูปแบบไปใช้กับวงรี
ตอนนี้ใช้การจัดรูปแบบบางอย่างกับวงรี เราจะตั้งค่าสีเติมแบบทึบและสีเส้น
### ตั้งค่าสีเติม
```java
// ใช้การจัดรูปแบบบางอย่างกับรูปร่างวงรี
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### ตั้งค่าสีเส้นและความกว้าง
```java
// ใช้การจัดรูปแบบบางอย่างกับบรรทัดของวงรี
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอไปยังไดเร็กทอรีที่คุณระบุ
```java
// เขียนไฟล์ PPTX ลงดิสก์
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: กำจัดวัตถุการนำเสนอ
กำจัดวัตถุที่นำเสนอเพื่อปลดปล่อยทรัพยากร
```java
finally {
    if (pres != null) pres.dispose();
}
```
## บทสรุป
ขอแสดงความยินดี! คุณได้สร้างวงรีที่จัดรูปแบบในงานนำเสนอ PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับการตั้งค่าโครงการ การเพิ่มวงรี การใช้รูปแบบ และการบันทึกงานนำเสนอของคุณ ด้วยทักษะเหล่านี้ คุณสามารถปรับปรุงสไลด์ PowerPoint ของคุณโดยใช้โปรแกรม ทำให้การนำเสนอของคุณมีชีวิตชีวาและน่าสนใจยิ่งขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ใดๆ ได้หรือไม่
ใช่ คุณสามารถใช้ Aspose.Slides สำหรับ Java ร่วมกับ Java IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans ได้
### ฉันต้องมีใบอนุญาตสำหรับ Aspose.Slides หรือไม่?
ใช่ Aspose.Slides เป็นผลิตภัณฑ์เชิงพาณิชย์ และคุณต้องมีใบอนุญาตจึงจะใช้งานได้เต็มรูปแบบ คุณสามารถขอใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารรายละเอียดเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ [หน้าเอกสาร](https://reference-aspose.com/slides/java/).
### มีการรองรับ Aspose.Slides หรือไม่
ใช่ Aspose เสนอการสนับสนุนผ่าน [ฟอรั่ม](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}