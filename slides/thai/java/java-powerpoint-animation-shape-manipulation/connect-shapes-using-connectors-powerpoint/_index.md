---
"description": "เรียนรู้วิธีการเชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java บทช่วยสอนแบบทีละขั้นตอนสำหรับผู้เริ่มต้น"
"linktitle": "เชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการเชื่อมต่อรูปทรงต่างๆ โดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วยความช่วยเหลือของ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อเชื่อมต่อรูปทรงต่างๆ อย่างมีประสิทธิภาพและสร้างสไลด์ที่ดึงดูดสายตา
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- ดาวน์โหลดและตั้งค่า Aspose.Slides สำหรับ Java แล้ว หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- โปรแกรมแก้ไขโค้ดเช่น Eclipse หรือ IntelliJ IDEA

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: สร้างตัวอย่างคลาสการนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสซึ่งแสดงถึงไฟล์ PPTX ที่คุณกำลังทำงานอยู่
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## ขั้นตอนที่ 2: เข้าถึงคอลเลกชันรูปทรง
เข้าถึงคอลเลกชันรูปทรงสำหรับสไลด์ที่เลือกซึ่งคุณต้องการเพิ่มรูปทรงและตัวเชื่อมต่อ
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## ขั้นตอนที่ 3: เพิ่มรูปร่าง
เพิ่มรูปร่างที่ต้องการลงในสไลด์ ในตัวอย่างนี้ เราจะเพิ่มวงรีและสี่เหลี่ยมผืนผ้า
```java
// เพิ่มวงรีรูปร่างอัตโนมัติ
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// เพิ่มรูปสี่เหลี่ยมผืนผ้ารูปร่างอัตโนมัติ
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## ขั้นตอนที่ 4: เพิ่มตัวเชื่อมต่อ
เพิ่มรูปร่างตัวเชื่อมต่อลงในคอลเล็กชั่นรูปร่างสไลด์
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## ขั้นตอนที่ 5: รวมรูปทรงเข้ากับตัวเชื่อมต่อ
เชื่อมต่อรูปทรงต่างๆ กับขั้วต่อ
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## ขั้นตอนที่ 6: เปลี่ยนเส้นทางตัวเชื่อมต่อ
เรียกเส้นทางใหม่เพื่อกำหนดเส้นทางที่สั้นที่สุดระหว่างรูปร่างโดยอัตโนมัติ
```java
connector.reroute();
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกการนำเสนอหลังจากเชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อ
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
สุดท้ายอย่าลืมกำจัดวัตถุการนำเสนอ
```java
if (input != null) input.dispose();
```
ตอนนี้คุณได้เชื่อมต่อรูปร่างโดยใช้ตัวเชื่อมต่อใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้สำเร็จแล้ว

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเชื่อมต่อรูปทรงโดยใช้ตัวเชื่อมต่อในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java โดยทำตามขั้นตอนง่ายๆ เหล่านี้ คุณสามารถปรับปรุงงานนำเสนอของคุณด้วยไดอะแกรมและผังงานที่น่าสนใจ
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งลักษณะของตัวเชื่อมต่อใน Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของขั้วต่อ เช่น สี สไตล์เส้น และความหนา เพื่อให้เหมาะกับความต้องการการนำเสนอของคุณได้
### Aspose.Slides สำหรับ Java สามารถใช้งานร่วมกับ PowerPoint ทุกเวอร์ชันได้หรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบ PowerPoint ต่างๆ รวมถึง PPTX, PPT และ ODP
### ฉันสามารถเชื่อมต่อรูปร่างมากกว่าสองรูปด้วยขั้วต่อตัวเดียวได้ไหม
ใช่ คุณสามารถเชื่อมต่อรูปทรงต่างๆ ได้โดยใช้ตัวเชื่อมต่อที่ซับซ้อนซึ่งจัดทำโดย Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java รองรับการเพิ่มข้อความลงในรูปร่างหรือไม่
แน่นอน คุณสามารถเพิ่มข้อความลงในรูปร่างและตัวเชื่อมต่อได้อย่างง่ายดายด้วยโปรแกรม Aspose.Slides สำหรับ Java
### มีฟอรัมชุมชนหรือช่องสนับสนุนสำหรับ Aspose.Slides สำหรับผู้ใช้ Java หรือไม่
ใช่ คุณสามารถค้นหาแหล่งข้อมูลที่มีประโยชน์ ถามคำถาม และมีส่วนร่วมกับผู้ใช้รายอื่นบนฟอรัม Aspose.Slides [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}