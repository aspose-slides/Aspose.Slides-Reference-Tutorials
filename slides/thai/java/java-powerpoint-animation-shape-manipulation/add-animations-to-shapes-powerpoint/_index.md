---
"description": "เรียนรู้วิธีการเพิ่มแอนิเมชั่นลงในรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนโดยละเอียดนี้ เหมาะอย่างยิ่งสำหรับการสร้างงานนำเสนอที่น่าสนใจ"
"linktitle": "เพิ่มแอนิเมชั่นให้กับรูปร่างใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มแอนิเมชั่นให้กับรูปร่างใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มแอนิเมชั่นให้กับรูปร่างใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดใจมักต้องเพิ่มแอนิเมชั่นให้กับรูปร่างและข้อความ แอนิเมชั่นสามารถทำให้สไลด์ของคุณมีชีวิตชีวาและน่าดึงดูดมากขึ้น ทำให้ผู้ชมของคุณสนใจต่อไป ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการเพิ่มแอนิเมชั่นให้กับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เมื่ออ่านบทความนี้จบ คุณจะสามารถสร้างแอนิเมชั่นระดับมืออาชีพได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกในบทช่วยสอน เรามาตรวจสอบกันก่อนว่าคุณมีทุกสิ่งที่คุณต้องการ:
1. Aspose.Slides สำหรับไลบรารี Java: คุณต้องติดตั้งไลบรารี Aspose.Slides สำหรับ Java คุณสามารถ [ดาวน์โหลดได้ที่นี่](https://releases-aspose.com/slides/java/).
2. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในเครื่องของคุณแล้ว
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ Java IDE ใดๆ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
4. ความรู้พื้นฐานเกี่ยวกับ Java: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็กเกจที่จำเป็นสำหรับ Aspose.Slides และคลาส Java ที่จำเป็นอื่นๆ
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
ขั้นแรก ให้สร้างไดเร็กทอรีสำหรับไฟล์โครงการของคุณ
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
ถัดไปสร้างอินสแตนซ์ `Presentation` คลาสที่จะแสดงไฟล์ PowerPoint ของคุณ
```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดง PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
ตอนนี้เข้าถึงสไลด์แรกในการนำเสนอที่คุณจะเพิ่มแอนิเมชัน
```java
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างลงในสไลด์
เพิ่มรูปทรงสี่เหลี่ยมผืนผ้าลงในสไลด์และแทรกข้อความลงไป
```java
// เพิ่มรูปสี่เหลี่ยมผืนผ้าให้กับสไลด์
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## ขั้นตอนที่ 5: ใช้เอฟเฟ็กต์แอนิเมชัน
ใช้เอฟเฟ็กต์แอนิเมชัน "PathFootball" กับรูปร่าง
```java
// เพิ่มเอฟเฟกต์แอนิเมชัน PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## ขั้นตอนที่ 6: สร้างทริกเกอร์แบบโต้ตอบ
สร้างรูปร่างปุ่มที่จะทริกเกอร์แอนิเมชันเมื่อคลิก
```java
// สร้างรูปร่าง "ปุ่ม" เพื่อเรียกใช้แอนิเมชั่น
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## ขั้นตอนที่ 7: กำหนดลำดับการโต้ตอบ
กำหนดลำดับเอฟเฟกต์สำหรับปุ่ม
```java
// สร้างลำดับเอฟเฟกต์สำหรับปุ่ม
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## ขั้นตอนที่ 8: เพิ่มเส้นทางผู้ใช้แบบกำหนดเอง
เพิ่มแอนิเมชั่นเส้นทางผู้ใช้แบบกำหนดเองลงในรูปร่าง
```java
// เพิ่มเอฟเฟกต์แอนิเมชั่นเส้นทางผู้ใช้แบบกำหนดเอง
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// สร้างเอฟเฟ็กต์การเคลื่อนไหว
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
สุดท้ายให้บันทึกการนำเสนอไปยังตำแหน่งที่คุณต้องการ
```java
// บันทึกการนำเสนอเป็นไฟล์ PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// กำจัดวัตถุนำเสนอ
if (pres != null) pres.dispose();
```
## บทสรุป
และแล้วคุณก็ทำได้สำเร็จ! คุณสามารถเพิ่มแอนิเมชันให้กับรูปร่างในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ทำให้การปรับปรุงงานนำเสนอของคุณง่ายขึ้นด้วยเอฟเฟกต์ไดนามิก ช่วยให้ผู้ฟังของคุณมีส่วนร่วมอยู่เสมอ จำไว้ว่าการฝึกฝนทำให้เก่ง ดังนั้นควรทดลองใช้เอฟเฟกต์และทริกเกอร์ต่างๆ อย่างต่อเนื่องเพื่อดูว่าเอฟเฟกต์ใดเหมาะกับความต้องการของคุณที่สุด
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังในการสร้าง แก้ไข และจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันสามารถใช้ Aspose.Slides ได้ฟรีหรือไม่?
คุณสามารถทดลองใช้ Aspose.Slides ได้ฟรีด้วย [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/)หากต้องการใช้ต่อจำเป็นต้องมีใบอนุญาตแบบชำระเงิน
### Java เวอร์ชันใดที่เข้ากันได้กับ Aspose.Slides?
Aspose.Slides รองรับ Java SE 6 ขึ้นไป
### ฉันจะเพิ่มแอนิเมชั่นต่างๆ ให้กับรูปร่างหลายรูปร่างได้อย่างไร
คุณสามารถเพิ่มแอนิเมชั่นต่างๆ ให้กับรูปร่างหลายๆ รูปร่างได้โดยการทำซ้ำขั้นตอนสำหรับรูปร่างแต่ละรูปร่างและระบุเอฟเฟกต์ต่างๆ ตามต้องการ
### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน
ตรวจสอบออก [เอกสารประกอบ](https://reference.aspose.com/slides/java/) และ [ฟอรั่มสนับสนุน](https://forum.aspose.com/c/slides/11) สำหรับตัวอย่างเพิ่มเติมและความช่วยเหลือ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}