---
title: เชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อใน PowerPoint
linktitle: เชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java บทช่วยสอนทีละขั้นตอนสำหรับผู้เริ่มต้น
weight: 18
url: /th/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วยความช่วยเหลือของ Aspose.Slides สำหรับ Java ทำตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อเชื่อมต่อรูปร่างและสร้างสไลด์ที่ดึงดูดสายตาอย่างมีประสิทธิภาพ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  ดาวน์โหลดและตั้งค่า Aspose.Slides สำหรับ Java หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- โปรแกรมแก้ไขโค้ดเช่น Eclipse หรือ IntelliJ IDEA

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของชั้นเรียนการนำเสนอ
 ยกตัวอย่าง`Presentation`คลาสซึ่งแสดงถึงไฟล์ PPTX ที่คุณกำลังทำงานอยู่
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงคอลเลกชันรูปร่าง
เข้าถึงคอลเลกชันรูปร่างสำหรับสไลด์ที่เลือกซึ่งคุณต้องการเพิ่มรูปร่างและตัวเชื่อมต่อ
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## ขั้นตอนที่ 3: เพิ่มรูปร่าง
เพิ่มรูปร่างที่ต้องการลงในสไลด์ ในตัวอย่างนี้ เราจะเพิ่มวงรีและสี่เหลี่ยม
```java
// เพิ่มวงรีรูปร่างอัตโนมัติ
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// เพิ่มรูปสี่เหลี่ยมผืนผ้าอัตโนมัติ
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## ขั้นตอนที่ 4: เพิ่มตัวเชื่อมต่อ
เพิ่มรูปร่างตัวเชื่อมต่อให้กับคอลเลกชันรูปร่างสไลด์
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## ขั้นตอนที่ 5: เข้าร่วมรูปร่างกับตัวเชื่อมต่อ
เชื่อมต่อรูปร่างเข้ากับตัวเชื่อมต่อ
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## ขั้นตอนที่ 6: เปลี่ยนเส้นทางตัวเชื่อมต่อ
โทรเปลี่ยนเส้นทางเพื่อกำหนดเส้นทางที่สั้นที่สุดโดยอัตโนมัติระหว่างรูปร่าง
```java
connector.reroute();
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอหลังจากเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อ
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
สุดท้ายอย่าลืมกำจัดวัตถุการนำเสนอ
```java
if (input != null) input.dispose();
```
ตอนนี้คุณเชื่อมต่อรูปร่างได้สำเร็จโดยใช้ตัวเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนง่ายๆ เหล่านี้ คุณจะปรับปรุงการนำเสนอของคุณด้วยไดอะแกรมและผังงานที่สวยงามดึงดูดสายตาได้
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งรูปลักษณ์ของตัวเชื่อมต่อใน Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของตัวเชื่อมต่อได้ เช่น สี ลักษณะของเส้น และความหนา เพื่อให้เหมาะกับความต้องการในการนำเสนอของคุณ
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบ PowerPoint หลากหลาย รวมถึง PPTX, PPT และ ODP
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปร่างด้วยตัวเชื่อมต่อเดียวได้หรือไม่
ได้ คุณสามารถเชื่อมต่อรูปร่างต่างๆ ได้โดยใช้ตัวเชื่อมต่อที่ซับซ้อนที่ Aspose.Slides สำหรับ Java มอบให้
### Aspose.Slides สำหรับ Java รองรับการเพิ่มข้อความลงในรูปร่างหรือไม่
แน่นอน คุณสามารถเพิ่มข้อความลงในรูปร่างและตัวเชื่อมต่อโดยใช้โปรแกรม Aspose.Slides สำหรับ Java ได้อย่างแน่นอน
### มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับ Aspose.Slides สำหรับผู้ใช้ Java หรือไม่
 ใช่ คุณสามารถค้นหาแหล่งข้อมูลที่เป็นประโยชน์ ถามคำถาม และมีส่วนร่วมกับผู้ใช้รายอื่นได้ในฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
