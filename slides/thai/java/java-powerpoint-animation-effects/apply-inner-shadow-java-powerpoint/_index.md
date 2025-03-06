---
title: ใช้เงาภายในในการนำเสนอ PowerPoint Java
linktitle: ใช้เงาภายในในการนำเสนอ PowerPoint Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้เอฟเฟกต์เงาภายในกับรูปร่างในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides ปรับปรุงสไลด์ของคุณด้วยคำแนะนำทีละขั้นตอนนี้
type: docs
weight: 12
url: /th/java/java-powerpoint-animation-effects/apply-inner-shadow-java-powerpoint/
---
## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการสื่อสารแนวคิดของคุณอย่างมีประสิทธิภาพ เครื่องมืออย่างหนึ่งที่สามารถปรับปรุงงานนำเสนอของคุณได้อย่างมากคือการใช้เงาภายใน บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการนำเงาภายในไปใช้กับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะมีความเข้าใจอย่างครอบคลุมเกี่ยวกับวิธีการจัดการองค์ประกอบสไลด์เพื่อสร้างเอฟเฟกต์ที่น่าทึ่ง
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์จาวา](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะช่วยให้คุณจัดการโครงการของคุณได้อย่างมีประสิทธิภาพมากขึ้น
4.  ใบอนุญาต Aspose.Slides: สำหรับใบอนุญาตชั่วคราว โปรดไปที่[มอบหมายใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) - สำหรับตัวเลือกการซื้อ ให้ตรวจสอบ[กำหนดหน้าการซื้อ](https://purchase.aspose.com/buy).
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็น สิ่งเหล่านี้จะช่วยให้คุณใช้คลาสและวิธีการที่ได้รับจาก Aspose.Slides
```java
import com.aspose.slides.*;
import java.io.File;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก ให้ตั้งค่าไดเรกทอรีโครงการของคุณ นี่จะเป็นที่เก็บไฟล์ PowerPoint และคลาส Java ของคุณ
```java
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
ในขั้นตอนนี้ เราตรวจสอบให้แน่ใจว่ามีไดเร็กทอรีสำหรับไฟล์โปรเจ็กต์ของคุณอยู่ หากไม่เป็นเช่นนั้น เราก็สร้างมันขึ้นมา
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
 ถัดไป คุณต้องสร้างอินสแตนซ์ของ`Presentation` ระดับ. วัตถุนี้จะเป็นอินเทอร์เฟซหลักของคุณสำหรับจัดการงานนำเสนอ PowerPoint
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
ตอนนี้ เข้าถึงสไลด์แรกของงานนำเสนอของคุณ สไลด์จะถูกจัดเก็บไว้ในคอลเลกชั่น และคุณสามารถเรียกดูสไลด์แรกได้โดยใช้ดัชนีของมัน
```java
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างให้กับสไลด์
เราจะเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าให้กับสไลด์ รูปร่างนี้จะมีข้อความและเงาด้านในติดอยู่ในภายหลัง
```java
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## ขั้นตอนที่ 5: เพิ่มข้อความลงในรูปร่าง
### สร้างและเข้าถึง TextFrame
 หากต้องการเพิ่มข้อความลงในรูปร่าง คุณต้องสร้างและเข้าถึง`TextFrame`.
```java
ashp.addTextFrame(" ");
ITextFrame txtFrame = ashp.getTextFrame();
```
### ตั้งค่าข้อความ
เพิ่มข้อความลงในรูปร่างสี่เหลี่ยมผืนผ้าโดยเข้าไปที่`Paragraph` และ`Portion` วัตถุ
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## ขั้นตอนที่ 6: ใช้เงาภายใน
ขั้นตอนนี้เกี่ยวข้องกับการสร้างเอฟเฟกต์เงาภายในและนำไปใช้กับรูปร่าง
```java
IEffectFormat effectFormat = ashp.getEffectFormat();
effectFormat.enableInnerShadowEffect();
IInnerShadowEffect innerShadow = effectFormat.getInnerShadowEffect();
innerShadow.setBlurRadius(5.0);
innerShadow.setDirection(45.0);
innerShadow.setDistance(4.0);
innerShadow.getShadowColor().setColor(java.awt.Color.BLACK);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอไปยังไดเร็กทอรีที่ระบุ ขั้นตอนนี้ช่วยให้แน่ใจว่าการเปลี่ยนแปลงของคุณถูกเขียนลงในไฟล์
```java
pres.save(dataDir + "ApplyInnerShadow_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 8: ทำความสะอาดทรัพยากร
 เพื่อหลีกเลี่ยงไม่ให้หน่วยความจำรั่วไหล ให้กำจัดทิ้งเสมอ`Presentation` วัตถุหลังจากที่คุณทำเสร็จแล้ว
```java
if (pres != null) pres.dispose();
```
## บทสรุป
ยินดีด้วย! คุณใช้เงาภายในกับรูปร่างในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้ครอบคลุมขั้นตอนสำคัญตั้งแต่การตั้งค่าโปรเจ็กต์ของคุณไปจนถึงการบันทึกการนำเสนอขั้นสุดท้าย ด้วยทักษะเหล่านี้ คุณสามารถปรับปรุงการนำเสนอของคุณด้วยเอฟเฟกต์ต่างๆ เพื่อให้น่าสนใจและดึงดูดสายตามากขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่ทรงพลังสำหรับการสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ช่วยให้นักพัฒนาทำงานกับการนำเสนอโดยไม่ต้องใช้ Microsoft PowerPoint
### ฉันสามารถใช้ Aspose.Slides โดยไม่มีใบอนุญาตได้หรือไม่
 Aspose.Slides ให้ทดลองใช้ฟรีซึ่งคุณสามารถดาวน์โหลดได้จาก[กำหนดหน้าทดลองใช้ฟรี](https://releases.aspose.com/)- อย่างไรก็ตาม เพื่อการใช้งานเต็มรูปแบบ จำเป็นต้องมีใบอนุญาต
### ฉันจะเพิ่มรูปร่างต่างๆ ลงในสไลด์ได้อย่างไร
 คุณสามารถเพิ่มรูปทรงต่างๆ ได้โดยใช้`addAutoShape` วิธีการและระบุประเภทรูปทรง เช่น`ShapeType.Rectangle`, `ShapeType.Ellipse`ฯลฯ
### ฉันสามารถปรับแต่งเอฟเฟ็กต์เงาเพิ่มเติมได้หรือไม่
ได้ คุณสามารถปรับแต่งพารามิเตอร์ต่างๆ ของเอฟเฟกต์เงาได้ เช่น รัศมีการเบลอ ทิศทาง ระยะทาง และสี เพื่อให้เหมาะกับความต้องการของคุณ
### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมได้จากที่ไหน?
 คุณสามารถอ้างถึง[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับข้อมูลโดยละเอียดและตัวอย่าง