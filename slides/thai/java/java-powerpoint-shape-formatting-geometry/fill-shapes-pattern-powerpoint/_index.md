---
title: เติมรูปร่างด้วยลวดลายใน PowerPoint
linktitle: เติมรูปร่างด้วยลวดลายใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้การเติมรูปร่างด้วยรูปแบบใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำง่ายๆ ทีละขั้นตอนของเราเพื่อปรับปรุงการนำเสนอของคุณด้วยภาพ
weight: 11
url: /th/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาเป็นสิ่งสำคัญในการดึงดูดผู้ชมของคุณ วิธีหนึ่งในการปรับปรุงสไลด์ PowerPoint ของคุณคือการเติมรูปร่างด้วยลวดลาย ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนต่างๆ เพื่อเติมรูปร่างด้วยรูปแบบโดยใช้ Aspose.Slides สำหรับ Java คู่มือนี้ได้รับการปรับแต่งสำหรับนักพัฒนาที่ต้องการใช้ประโยชน์จากคุณสมบัติอันทรงพลังของ Aspose.Slides เพื่อสร้างงานนำเสนอที่น่าทึ่งโดยทางโปรแกรม
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนเครื่องของคุณแล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นสำหรับตัวอย่างของเรากันก่อน
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนที่จะเขียนโค้ด ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณได้รับการตั้งค่าอย่างถูกต้อง สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ไปยังการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างไดเร็กทอรีเอกสาร
เพื่อจัดการไฟล์ของคุณอย่างมีประสิทธิภาพ มาสร้างไดเร็กทอรีที่เราจะบันทึกงานนำเสนอ PowerPoint ของเรากันดีกว่า
```java
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
ข้อมูลโค้ดนี้จะตรวจสอบว่ามีไดเร็กทอรีอยู่หรือไม่ และสร้างใหม่หากไม่มี
## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของคลาสการนำเสนอ
 ต่อไปเราต้องสร้างอินสแตนซ์ของ`Presentation` คลาสซึ่งแสดงถึงไฟล์ PowerPoint ของเรา
```java
Presentation pres = new Presentation();
```
นี่เป็นการเริ่มต้นวัตถุการนำเสนอใหม่ที่เราจะใช้เพื่อเพิ่มสไลด์และรูปร่าง
## ขั้นตอนที่ 4: เข้าถึงสไลด์แรก
ในการเริ่มต้น เราต้องเข้าถึงสไลด์แรกในการนำเสนอของเรา นี่คือที่ที่เราจะเพิ่มรูปร่างของเรา
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างสี่เหลี่ยมผืนผ้า
เพิ่มรูปทรงสี่เหลี่ยมให้กับสไลด์ของเรา สี่เหลี่ยมนี้จะเต็มไปด้วยลวดลาย
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
ข้อมูลโค้ดนี้จะเพิ่มสี่เหลี่ยมผืนผ้าลงในสไลด์ในตำแหน่งและขนาดที่ระบุ
## ขั้นตอนที่ 6: ตั้งค่าประเภทการเติมเป็นรูปแบบ
ตอนนี้ เราต้องตั้งค่าประเภทการเติมของสี่เหลี่ยมผืนผ้าเป็นการเติมรูปแบบ
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## ขั้นตอนที่ 7: เลือกสไตล์ลวดลาย
Aspose.Slides มีรูปแบบลวดลายที่หลากหลาย ในตัวอย่างนี้ เราจะใช้รูปแบบ "เทรลลิส"
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## ขั้นตอนที่ 8: ตั้งค่าสีลวดลาย
เราสามารถปรับแต่งสีของลวดลายของเราได้ มาตั้งค่าสีพื้นหลังเป็นสีเทาอ่อนและสีพื้นหน้าเป็นสีเหลือง
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## ขั้นตอนที่ 9: บันทึกการนำเสนอ
หลังจากตั้งค่ารูปร่างตามรูปแบบที่ต้องการแล้ว เราจำเป็นต้องบันทึกงานนำเสนอลงในไฟล์
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
วิธีนี้จะบันทึกการนำเสนอในไดเร็กทอรีที่ระบุด้วยชื่อไฟล์ "RectShpPatt_out.pptx"
## ขั้นตอนที่ 10: ทำความสะอาดทรัพยากร
แนวทางปฏิบัติที่ดีคือการกำจัดออบเจ็กต์การนำเสนอเพื่อเพิ่มทรัพยากร
```java
if (pres != null) pres.dispose();
```
## บทสรุป
ยินดีด้วย! คุณเติมรูปร่างด้วยลวดลายในสไลด์ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยให้คุณสร้างและจัดการการนำเสนอได้อย่างง่ายดาย เพิ่มความเป็นมืออาชีพให้กับโปรเจ็กต์ของคุณ
 ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณจะปรับปรุงการนำเสนอของคุณด้วยรูปแบบที่หลากหลาย ทำให้น่าสนใจและดึงดูดสายตามากขึ้น สำหรับคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม โปรดตรวจสอบที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ในแอปพลิเคชัน Java
### ฉันจะรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อจัดการการนำเสนอที่มีอยู่ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java ช่วยให้คุณสามารถเปิด แก้ไข และบันทึกงานนำเสนอ PowerPoint ที่มีอยู่ได้
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจาก[ฟอรั่มการสนับสนุน Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
