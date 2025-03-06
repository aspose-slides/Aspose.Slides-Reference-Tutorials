---
title: สร้างสี่เหลี่ยมผืนผ้าที่จัดรูปแบบใน PowerPoint
linktitle: สร้างสี่เหลี่ยมผืนผ้าที่จัดรูปแบบใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างและจัดรูปแบบสี่เหลี่ยมผืนผ้าใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนนี้
weight: 18
url: /th/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างสี่เหลี่ยมผืนผ้าที่จัดรูปแบบในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะแจกแจงแต่ละขั้นตอนเพื่อให้แน่ใจว่าคุณสามารถปฏิบัติตามและนำไปใช้ในโครงการของคุณเองได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกโค้ด เรามาพูดถึงข้อกำหนดเบื้องต้นกันก่อน คุณจะต้องมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2. Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Slides สำหรับไลบรารี Java ในโปรเจ็กต์ของคุณ
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้ประสบการณ์การเขียนโค้ดของคุณราบรื่นยิ่งขึ้น
4. ความรู้พื้นฐานของ Java: ความคุ้นเคยกับการเขียนโปรแกรม Java จะช่วยให้คุณปฏิบัติตามบทช่วยสอนนี้
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นจากไลบรารี Aspose.Slides ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
การนำเข้าเหล่านี้มีความสำคัญเนื่องจากเป็นการนำคลาสที่จำเป็นในการสร้างและจัดรูปแบบรูปร่างในงานนำเสนอ PowerPoint ของคุณเข้ามา
## ขั้นตอนที่ 1: การตั้งค่าไดเรกทอรีโครงการ
ขั้นแรก คุณต้องสร้างไดเร็กทอรีสำหรับโปรเจ็กต์ของคุณ ไดเร็กทอรีนี้จะเก็บไฟล์ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
รหัสนี้จะตรวจสอบว่ามีไดเร็กทอรีอยู่หรือไม่และสร้างใหม่หากไม่มี แนวทางปฏิบัติที่ดีในการจัดระเบียบไฟล์โครงการของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของคลาสการนำเสนอ
 ต่อไป คุณจะยกตัวอย่าง`Presentation` คลาสซึ่งแสดงถึงไฟล์ PowerPoint ของคุณ
```java
Presentation pres = new Presentation();
```
บรรทัดโค้ดนี้จะสร้างงานนำเสนอใหม่ที่ว่างเปล่าซึ่งคุณสามารถเริ่มเพิ่มเนื้อหาได้
## ขั้นตอนที่ 3: เพิ่มสไลด์ในการนำเสนอ
ตอนนี้ มาเพิ่มสไลด์ในการนำเสนอของคุณกันดีกว่า ตามค่าเริ่มต้น งานนำเสนอใหม่จะมีหนึ่งสไลด์ ดังนั้นเราจะดำเนินการตามนั้น
```java
ISlide sld = pres.getSlides().get_Item(0);
```
ข้อมูลโค้ดนี้จะได้สไลด์แรกจากการนำเสนอ
## ขั้นตอนที่ 4: เพิ่มรูปร่างสี่เหลี่ยมผืนผ้า
ตอนนี้เราจะเพิ่มสี่เหลี่ยมให้กับสไลด์
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
ที่นี่ เรากำลังเพิ่มสี่เหลี่ยมผืนผ้าที่มีขนาด (ความกว้าง ความสูง) และตำแหน่ง (x, y) ที่ระบุลงในสไลด์
## ขั้นตอนที่ 5: จัดรูปแบบสี่เหลี่ยมผืนผ้า
ลองใช้การจัดรูปแบบเพื่อทำให้สี่เหลี่ยมผืนผ้าดูน่าดึงดูด
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
รหัสนี้ตั้งค่าประเภทการเติมเป็นสีทึบและสีเติมเป็นช็อกโกแลต
## จัดรูปแบบเส้นขอบของสี่เหลี่ยมผืนผ้า
ต่อไปเราจะจัดรูปแบบเส้นขอบของสี่เหลี่ยม
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
รหัสนี้กำหนดสีของเส้นขอบเป็นสีดำและความกว้างของเส้นขอบเป็น 5
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายนี้ มาบันทึกการนำเสนอลงในไดเร็กทอรีโครงการของคุณกัน
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
บรรทัดโค้ดนี้จะบันทึกงานนำเสนอเป็นไฟล์ PPTX ในไดเร็กทอรีที่คุณระบุ
## ขั้นตอนที่ 7: ทำความสะอาดทรัพยากร
 แนวทางปฏิบัติที่ดีคือการกำจัดทิ้ง`Presentation` คัดค้านการเพิ่มทรัพยากร
```java
if (pres != null) pres.dispose();
```
เพื่อให้แน่ใจว่าทรัพยากรทั้งหมดได้รับการเผยแพร่อย่างเหมาะสม
## บทสรุป
การสร้างและจัดรูปแบบรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถสร้างสไลด์ที่ดึงดูดสายตาได้โดยอัตโนมัติได้อย่างง่ายดาย ไม่ว่าคุณกำลังพัฒนาแอปพลิเคชันสำหรับการรายงานทางธุรกิจ เนื้อหาทางการศึกษา หรือการนำเสนอแบบไดนามิก Aspose.Slides สำหรับ Java มีเครื่องมือที่คุณต้องการเพื่อประสบความสำเร็จ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java เป็นไลบรารีที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ใด ๆ ได้หรือไม่
ได้ คุณสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ที่เข้ากันได้กับ Java เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### ฉันจะทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
###  จำเป็นต้องกำจัดทิ้งหรือไม่.`Presentation` object?
 ใช่แล้ว การกำจัด.`Presentation` วัตถุช่วยเพิ่มพื้นที่ว่างทรัพยากรและหลีกเลี่ยงการรั่วไหลของหน่วยความจำ
### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
