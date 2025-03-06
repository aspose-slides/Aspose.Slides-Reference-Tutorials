---
title: เพิ่มภาพเคลื่อนไหวให้กับรูปร่างใน PowerPoint
linktitle: เพิ่มภาพเคลื่อนไหวให้กับรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มภาพเคลื่อนไหวให้กับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมบทช่วยสอนโดยละเอียดนี้ เหมาะสำหรับการสร้างการนำเสนอที่น่าสนใจ
weight: 10
url: /th/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องเพิ่มภาพเคลื่อนไหวให้กับรูปร่างและข้อความ แอนิเมชันสามารถทำให้สไลด์ของคุณมีชีวิตชีวาและน่าดึงดูดยิ่งขึ้น ทำให้มั่นใจได้ว่าผู้ชมจะสนใจอยู่เสมอ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มภาพเคลื่อนไหวให้กับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ในตอนท้ายของบทความนี้ คุณจะสามารถสร้างแอนิเมชั่นระดับมืออาชีพได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:
1.  Aspose.Slides สำหรับ Java Library: คุณต้องติดตั้ง Aspose.Slides สำหรับไลบรารี Java คุณสามารถ[ดาวน์โหลดได้ที่นี่](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ Java IDE ใดๆ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
4. ความรู้พื้นฐานของ Java: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides และคลาส Java ที่จำเป็นอื่นๆ
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก สร้างไดเร็กทอรีสำหรับไฟล์โปรเจ็กต์ของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
 ถัดไป ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์ PowerPoint ของคุณ
```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึง PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
ตอนนี้ให้เข้าถึงสไลด์แรกในงานนำเสนอที่คุณจะเพิ่มภาพเคลื่อนไหว
```java
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างให้กับสไลด์
เพิ่มรูปร่างสี่เหลี่ยมผืนผ้าลงในสไลด์และแทรกข้อความลงไป
```java
// เพิ่มรูปร่างสี่เหลี่ยมผืนผ้าให้กับสไลด์
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## ขั้นตอนที่ 5: ใช้เอฟเฟ็กต์ภาพเคลื่อนไหว
ใช้เอฟเฟกต์ภาพเคลื่อนไหว "PathFootball" กับรูปร่าง
```java
// เพิ่มเอฟเฟกต์ภาพเคลื่อนไหว PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## ขั้นตอนที่ 6: สร้างทริกเกอร์แบบโต้ตอบ
สร้างรูปร่างปุ่มที่จะทริกเกอร์ภาพเคลื่อนไหวเมื่อคลิก
```java
// สร้างรูปร่าง "ปุ่ม" เพื่อเรียกภาพเคลื่อนไหว
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## ขั้นตอนที่ 7: กำหนดลำดับการโต้ตอบ
กำหนดลำดับเอฟเฟกต์สำหรับปุ่ม
```java
// สร้างลำดับเอฟเฟกต์สำหรับปุ่ม
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## ขั้นตอนที่ 8: เพิ่มเส้นทางผู้ใช้ที่กำหนดเอง
เพิ่มภาพเคลื่อนไหวเส้นทางผู้ใช้แบบกำหนดเองให้กับรูปร่าง
```java
// เพิ่มเอฟเฟกต์ภาพเคลื่อนไหวเส้นทางผู้ใช้ที่กำหนดเอง
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// สร้างเอฟเฟกต์การเคลื่อนไหว
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// กำหนดจุดเส้นทาง
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## ขั้นตอนที่ 9: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอไปยังตำแหน่งที่คุณต้องการ
```java
// บันทึกงานนำเสนอเป็นไฟล์ PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// กำจัดวัตถุการนำเสนอ
if (pres != null) pres.dispose();
```
## บทสรุป
และคุณก็ได้แล้ว! คุณได้เพิ่มภาพเคลื่อนไหวให้กับรูปร่างในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ทำให้ง่ายต่อการปรับปรุงการนำเสนอของคุณด้วยเอฟเฟกต์ไดนามิก เพื่อให้มั่นใจว่าผู้ชมของคุณยังคงมีส่วนร่วม โปรดจำไว้ว่า การฝึกฝนทำให้สมบูรณ์แบบ ดังนั้นให้ทดลองกับเอฟเฟกต์และตัวกระตุ้นต่างๆ เพื่อดูว่าอะไรเหมาะกับความต้องการของคุณมากที่สุด
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพในการสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่
 คุณสามารถลองใช้ Aspose.Slides ได้ฟรีด้วย[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)- สำหรับการใช้งานต่อเนื่อง จำเป็นต้องมีใบอนุญาตแบบชำระเงิน
### Java เวอร์ชันใดที่เข้ากันได้กับ Aspose.Slides
Aspose.Slides รองรับ Java SE 6 ขึ้นไป
### ฉันจะเพิ่มภาพเคลื่อนไหวต่างๆ ให้กับรูปร่างต่างๆ ได้อย่างไร
คุณสามารถเพิ่มภาพเคลื่อนไหวที่แตกต่างกันให้กับรูปร่างต่างๆ ได้โดยทำซ้ำขั้นตอนสำหรับแต่ละรูปร่าง และระบุเอฟเฟกต์ที่แตกต่างกันตามต้องการ
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/slides/java/) และ[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11)สำหรับตัวอย่างและความช่วยเหลือเพิ่มเติม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
