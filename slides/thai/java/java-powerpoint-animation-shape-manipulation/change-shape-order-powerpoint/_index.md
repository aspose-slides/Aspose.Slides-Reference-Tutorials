---
title: เปลี่ยนลำดับรูปร่างใน PowerPoint
linktitle: เปลี่ยนลำดับรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเปลี่ยนลำดับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนทีละขั้นตอนนี้ พัฒนาทักษะการนำเสนอของคุณได้อย่างง่ายดาย
type: docs
weight: 15
url: /th/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---
## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาและมีโครงสร้างที่ดีอาจเป็นงานที่น่ากังวล อย่างไรก็ตาม ด้วยเครื่องมือและเทคนิคที่เหมาะสม คุณสามารถทำให้ง่ายขึ้นอย่างมาก Aspose.Slides for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณจัดการและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนในการเปลี่ยนลำดับรูปร่างในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java Library: ดาวน์โหลดเวอร์ชันล่าสุดจาก[Aspose.Slides สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเข้ารหัส
4. ไฟล์การนำเสนอ: เตรียมไฟล์ PowerPoint ที่คุณต้องการจัดการให้พร้อม
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นจากไลบรารี Aspose.Slides การนำเข้าเหล่านี้จะช่วยให้คุณสามารถทำงานกับงานนำเสนอ สไลด์ และรูปร่างได้
```java
import com.aspose.slides.*;

```
ในคู่มือนี้ เราจะแจกแจงกระบวนการเปลี่ยนลำดับรูปร่างออกเป็นหลายขั้นตอนเพื่อความเข้าใจที่ดีขึ้นและง่ายต่อการนำไปใช้
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
 ขั้นแรก คุณต้องโหลดไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการใช้งาน ขั้นตอนนี้เกี่ยวข้องกับการเริ่มต้นไฟล์`Presentation` คลาสพร้อมเส้นทางไปยังไฟล์ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์ที่ต้องการ
เมื่อโหลดงานนำเสนอแล้ว ให้เข้าถึงสไลด์ที่คุณต้องการเรียงลำดับรูปร่างใหม่ สไลด์จะได้รับการจัดทำดัชนีโดยเริ่มจาก 0 ดังนั้นหากต้องการเข้าถึงสไลด์แรก ให้ใช้ดัชนี 0
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
จากนั้น เพิ่มรูปร่างลงในสไลด์ สำหรับการสาธิต เราจะเพิ่มรูปสี่เหลี่ยมผืนผ้าและรูปสามเหลี่ยมลงในสไลด์
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## ขั้นตอนที่ 4: เรียงลำดับรูปร่างใหม่
 ตอนนี้ จัดลำดับรูปร่างบนสไลด์ใหม่ ที่`reorder` วิธีการช่วยให้คุณสามารถระบุตำแหน่งใหม่สำหรับรูปร่างภายในคอลเลกชันรูปร่างของสไลด์
```java
slide.getShapes().reorder(2, shp3);
```
## ขั้นตอนที่ 5: บันทึกงานนำเสนอที่แก้ไข
หลังจากเรียงลำดับรูปร่างใหม่แล้ว ให้บันทึกงานนำเสนอที่แก้ไขแล้วเป็นไฟล์ใหม่ เพื่อให้แน่ใจว่าไฟล์ต้นฉบับของคุณยังคงไม่เปลี่ยนแปลง
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ทำความสะอาดทรัพยากร
สุดท้าย ให้กำจัดออบเจ็กต์การนำเสนอเพื่อเพิ่มทรัพยากร
```java
if (presentation1 != null) presentation1.dispose();
```
## บทสรุป
เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเปลี่ยนลำดับของรูปร่างในสไลด์ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ทำให้งานหลายอย่างที่เกี่ยวข้องกับงานนำเสนอ PowerPoint ง่ายขึ้น ทำให้คุณสามารถสร้างและจัดการสไลด์โดยทางโปรแกรมได้ ไม่ว่าคุณจะสร้างงานนำเสนอโดยอัตโนมัติหรือเพียงแค่ต้องการเปลี่ยนแปลงจำนวนมาก Aspose.Slides สำหรับ Java เป็นเครื่องมือที่ทรงคุณค่า
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides for Java เป็น Java API สำหรับการสร้างและจัดการงานนำเสนอ PowerPoint โดยไม่ต้องใช้ Microsoft PowerPoint
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ Java IDE อื่นๆ ได้หรือไม่
ได้ คุณสามารถใช้มันกับ Java IDE ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### Aspose.Slides สำหรับ Java เข้ากันได้กับรูปแบบ PowerPoint ทั้งหมดหรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับ PPT, PPTX และรูปแบบ PowerPoint อื่นๆ
### ฉันจะทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้อย่างไร
 คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[Aspose.Slides สำหรับหน้าดาวน์โหลด Java](https://releases.aspose.com/).
### ฉันจะหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถดูเอกสารรายละเอียดได้ที่[Aspose.Slides สำหรับหน้าเอกสารประกอบ Java](https://reference.aspose.com/slides/java/).