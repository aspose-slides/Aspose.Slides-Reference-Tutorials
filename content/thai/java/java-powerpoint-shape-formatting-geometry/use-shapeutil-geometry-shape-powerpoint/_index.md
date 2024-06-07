---
title: ใช้ ShapeUtil สำหรับรูปร่างเรขาคณิตใน PowerPoint
linktitle: ใช้ ShapeUtil สำหรับรูปร่างเรขาคณิตใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างรูปร่างที่กำหนดเองใน PowerPoint ด้วย Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนนี้เพื่อปรับปรุงการนำเสนอของคุณ
type: docs
weight: 23
url: /th/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---
## การแนะนำ
 การสร้างงานนำเสนอ PowerPoint ที่ดึงดูดสายตามักต้องการมากกว่าการใช้รูปร่างและข้อความมาตรฐาน ลองนึกภาพความสามารถในการเพิ่มรูปร่างและเส้นทางข้อความที่กำหนดเองลงในสไลด์ของคุณได้โดยตรง ซึ่งจะช่วยเพิ่มผลกระทบทางภาพให้กับงานนำเสนอของคุณ การใช้ Aspose.Slides สำหรับ Java คุณสามารถทำสิ่งนี้ได้อย่างง่ายดาย บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการใช้งาน`ShapeUtil`คลาสสร้างรูปทรงเรขาคณิตในงานนำเสนอ PowerPoint ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณใช้ประโยชน์จากพลังของ Aspose.Slides สำหรับ Java เพื่อสร้างเนื้อหาที่สวยงามและปรับแต่งได้เอง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน มีบางสิ่งที่คุณต้องการ:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 8 ขึ้นไปบนเครื่องของคุณ
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดเวอร์ชันล่าสุดจาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนา: ใช้ Java IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
4.  ใบอนุญาตชั่วคราว: รับใบอนุญาตชั่วคราวฟรีจาก[หน้าใบอนุญาตชั่วคราวของ Aspose](https://purchase.aspose.com/temporary-license/) เพื่อปลดล็อกการทำงานเต็มรูปแบบของ Aspose.Slides สำหรับ Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides และ Java AWT (Abstract Window Toolkit):
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## ขั้นตอนที่ 1: การตั้งค่าโครงการของคุณ
ขั้นแรก ให้ตั้งค่าโปรเจ็กต์ Java ของคุณและเพิ่ม Aspose.Slides สำหรับ Java ไปยังการขึ้นต่อกันของโปรเจ็กต์ของคุณ คุณสามารถทำได้โดยการเพิ่มไฟล์ JAR โดยตรง หรือโดยใช้เครื่องมือสร้าง เช่น Maven หรือ Gradle
## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่
เริ่มต้นด้วยการสร้างวัตถุการนำเสนอ PowerPoint ใหม่ วัตถุนี้จะเป็นผืนผ้าใบที่คุณจะเพิ่มรูปร่างที่คุณกำหนดเอง
```java
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างสี่เหลี่ยมผืนผ้า
จากนั้น เพิ่มรูปร่างสี่เหลี่ยมผืนผ้าพื้นฐานลงในสไลด์แรกของงานนำเสนอ รูปร่างนี้จะได้รับการแก้ไขในภายหลังเพื่อรวมเส้นทางเรขาคณิตที่กำหนดเอง
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## ขั้นตอนที่ 4: ดึงข้อมูลและแก้ไขเส้นทางเรขาคณิต
 ดึงเส้นทางเรขาคณิตของรูปร่างสี่เหลี่ยมผืนผ้าและแก้ไขโหมดการเติมเป็น`None`- ขั้นตอนนี้มีความสำคัญเนื่องจากช่วยให้คุณสามารถรวมเส้นทางนี้กับเส้นทางเรขาคณิตที่กำหนดเองอื่นได้
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## ขั้นตอนที่ 5: สร้างเส้นทางเรขาคณิตที่กำหนดเองจากข้อความ
ตอนนี้ ให้สร้างเส้นทางเรขาคณิตที่กำหนดเองตามข้อความ สิ่งนี้เกี่ยวข้องกับการแปลงสตริงข้อความเป็นเส้นทางแบบกราฟิกแล้วแปลงเส้นทางนั้นเป็นเส้นทางเรขาคณิต
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## ขั้นตอนที่ 6: รวมเส้นทางเรขาคณิต
รวมเส้นทางเรขาคณิตดั้งเดิมเข้ากับเส้นทางเรขาคณิตแบบข้อความใหม่และตั้งค่าชุดค่าผสมนี้เป็นรูปร่าง
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ เพื่อส่งออกไฟล์ PowerPoint ที่มีรูปร่างที่คุณกำหนดเอง
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## บทสรุป
ยินดีด้วย! คุณเพิ่งสร้างรูปทรงเรขาคณิตที่กำหนดเองในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะอธิบายให้คุณทราบแต่ละขั้นตอน ตั้งแต่การตั้งค่าโปรเจ็กต์ไปจนถึงการสร้างและการรวมเส้นทางเรขาคณิต เมื่อเชี่ยวชาญเทคนิคเหล่านี้ คุณจะสามารถเพิ่มองค์ประกอบที่เป็นเอกลักษณ์และสะดุดตาให้กับงานนำเสนอของคุณ ทำให้โดดเด่นได้
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพสำหรับการทำงานกับไฟล์ PowerPoint ใน Java ช่วยให้คุณสร้าง แก้ไข และแปลงงานนำเสนอโดยทางโปรแกรม
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/) และเพิ่มไฟล์ JAR ในโครงการของคุณ
### ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่
 Aspose.Slides มีเวอร์ชันทดลองใช้ฟรี ซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/)- หากต้องการฟังก์ชันการทำงานเต็มรูปแบบ คุณจะต้องซื้อใบอนุญาต
### คลาส ShapeUtil มีประโยชน์อย่างไร?
 ที่`ShapeUtil` คลาสใน Aspose.Slides มีวิธีการที่เป็นประโยชน์สำหรับการทำงานกับรูปร่าง เช่น การแปลงเส้นทางกราฟิกเป็นเส้นทางเรขาคณิต
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจาก[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).