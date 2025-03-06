---
title: ใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างใน PowerPoint
linktitle: ใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนที่ครอบคลุมทีละขั้นตอนนี้
type: docs
weight: 12
url: /th/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---
## การแนะนำ
คุณพร้อมที่จะยกระดับการนำเสนอ PowerPoint ของคุณไปอีกระดับแล้วหรือยัง? การเพิ่มเอฟเฟ็กต์การหมุน 3 มิติสามารถทำให้สไลด์ของคุณมีชีวิตชีวาและน่าดึงดูดยิ่งขึ้น ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนทีละขั้นตอนนี้จะแสดงวิธีใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java มาดำดิ่งกันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันล่าสุดจาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเข้ารหัส
4.  ใบอนุญาตที่ถูกต้อง: หากคุณไม่มีใบอนุญาต คุณสามารถขอรับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อลองใช้คุณสมบัติต่างๆ
## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณกันก่อน การนำเข้าเหล่านี้จะช่วยคุณจัดการการนำเสนอและรูปร่างด้วย Aspose.Slides
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนที่จะเจาะลึกโค้ด ให้ตั้งค่าสภาพแวดล้อมโปรเจ็กต์ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่ม Aspose.Slides สำหรับ Java ลงในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
เพิ่ม Aspose.Slides ในโครงการของคุณ:
1.  ดาวน์โหลดไฟล์ Aspose.Slides JAR จากไฟล์[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).
2. เพิ่มไฟล์ JAR เหล่านี้ไปยังพาธการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างงานนำเสนอ PowerPoint ใหม่
ในขั้นตอนนี้ เราจะสร้างงานนำเสนอ PowerPoint ใหม่
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation pres = new Presentation();
```
ข้อมูลโค้ดนี้เริ่มต้นวัตถุการนำเสนอใหม่ที่เราจะเพิ่มรูปร่างของเรา
## ขั้นตอนที่ 3: เพิ่มรูปร่างสี่เหลี่ยมผืนผ้า
ต่อไป มาเพิ่มรูปร่างสี่เหลี่ยมผืนผ้าให้กับสไลด์แรก
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
รหัสนี้จะเพิ่มรูปร่างสี่เหลี่ยมผืนผ้าในตำแหน่งและขนาดที่ระบุในสไลด์แรก
## ขั้นตอนที่ 4: ใช้การหมุน 3 มิติกับสี่เหลี่ยมผืนผ้า
ตอนนี้ ลองใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างสี่เหลี่ยมผืนผ้า
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
ที่นี่ เราตั้งค่าความลึก มุมการหมุนกล้อง ประเภทกล้อง และประเภทแสง เพื่อให้รูปสี่เหลี่ยมผืนผ้าของเราดูเป็น 3 มิติ
## ขั้นตอนที่ 5: เพิ่มรูปร่างเส้น
มาเพิ่มรูปร่างอื่น คราวนี้เป็นเส้น ให้กับสไลด์
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
รหัสนี้วางรูปร่างเส้นบนสไลด์
## ขั้นตอนที่ 6: ใช้การหมุน 3 มิติกับเส้น
สุดท้ายนี้ เราจะใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างของเส้น
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
เช่นเดียวกับสี่เหลี่ยมผืนผ้า เราตั้งค่าคุณสมบัติ 3 มิติสำหรับรูปร่างเส้น
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
หลังจากเพิ่มและกำหนดค่ารูปร่างของคุณแล้ว ให้บันทึกงานนำเสนอ
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
รหัสนี้จะบันทึกการนำเสนอของคุณด้วยชื่อไฟล์ที่ระบุในรูปแบบที่ต้องการ
## บทสรุป
 ยินดีด้วย! คุณใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างงานนำเสนอที่ดึงดูดสายตาและมีชีวิตชีวาได้ สำหรับการปรับแต่งเพิ่มเติมและคุณสมบัติขั้นสูง โปรดดูที่[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/).
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพในการสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) หรือก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบคุณสมบัติต่างๆ
### รูปร่างประเภทใดที่ฉันสามารถเพิ่มเอฟเฟกต์ 3D ให้กับ Aspose.Slides ได้
คุณสามารถเพิ่มเอฟเฟ็กต์ 3D ให้กับรูปร่างต่างๆ เช่น สี่เหลี่ยม เส้น วงรี และรูปร่างแบบกำหนดเองได้
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 ท่านสามารถเยี่ยมชมได้ที่[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือและหารือประเด็นต่างๆ
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ แต่คุณต้องซื้อใบอนุญาต คุณสามารถซื้อได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).