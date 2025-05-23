---
"description": "เรียนรู้วิธีการใช้เอฟเฟ็กต์การหมุน 3 มิติกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนทีละขั้นตอนที่ครอบคลุมนี้"
"linktitle": "ใช้เอฟเฟกต์การหมุน 3 มิติกับรูปทรงใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ใช้เอฟเฟกต์การหมุน 3 มิติกับรูปทรงใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ใช้เอฟเฟกต์การหมุน 3 มิติกับรูปทรงใน PowerPoint

## การแนะนำ
คุณพร้อมที่จะยกระดับการนำเสนอ PowerPoint ของคุณหรือยัง การเพิ่มเอฟเฟกต์การหมุน 3 มิติสามารถทำให้สไลด์ของคุณมีชีวิตชีวาและน่าสนใจยิ่งขึ้น ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนแบบทีละขั้นตอนนี้จะแสดงให้คุณเห็นถึงวิธีการใช้เอฟเฟกต์การหมุน 3 มิติกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java มาเริ่มกันเลย!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ออราเคิล](https://www-oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides สำหรับ Java: ดาวน์โหลด Aspose.Slides เวอร์ชันล่าสุดสำหรับ Java จาก [ลิงค์ดาวน์โหลด](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเขียนโค้ด
4. ใบอนุญาตที่ถูกต้อง: หากคุณไม่มีใบอนุญาต คุณสามารถขอรับได้ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อทดลองใช้คุณสมบัติต่างๆ
## แพ็คเกจนำเข้า
ก่อนอื่น ให้ทำการอิมพอร์ตแพ็กเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ อิมพอร์ตเหล่านี้จะช่วยให้คุณจัดการการนำเสนอและรูปร่างต่างๆ ด้วย Aspose.Slides ได้
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ก่อนจะเริ่มเขียนโค้ด ให้ตั้งค่าสภาพแวดล้อมของโปรเจ็กต์ของคุณก่อน ตรวจสอบว่าคุณได้เพิ่ม Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์แล้ว
เพิ่ม Aspose.Slides ลงในโปรเจ็กต์ของคุณ:
1. ดาวน์โหลดไฟล์ JAR Aspose.Slides จาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/java/).
2. เพิ่มไฟล์ JAR เหล่านี้ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างการนำเสนอ PowerPoint ใหม่
ในขั้นตอนนี้เราจะสร้างการนำเสนอ PowerPoint ใหม่
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation pres = new Presentation();
```
โค้ดตัวอย่างนี้จะเริ่มต้นวัตถุการนำเสนอใหม่ซึ่งเราจะเพิ่มรูปร่างของเรา
## ขั้นตอนที่ 3: เพิ่มรูปทรงสี่เหลี่ยมผืนผ้า
ต่อไปเราจะเพิ่มรูปสี่เหลี่ยมผืนผ้าลงในสไลด์แรก
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
โค้ดนี้จะเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าที่ตำแหน่งและขนาดที่ระบุในสไลด์แรก
## ขั้นตอนที่ 4: ใช้การหมุน 3 มิติกับสี่เหลี่ยมผืนผ้า
ต่อไปเราลองมาใช้เอฟเฟ็กต์การหมุน 3 มิติกับรูปสี่เหลี่ยมผืนผ้ากัน
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
ที่นี่ เราตั้งค่าความลึก มุมการหมุนของกล้อง ประเภทของกล้อง และประเภทของแสง เพื่อให้รูปสี่เหลี่ยมของเรามีลักษณะเป็นสามมิติ
## ขั้นตอนที่ 5: เพิ่มรูปร่างเส้น
มาเพิ่มรูปร่างอีกอัน คราวนี้เป็นเส้น ลงในสไลด์กัน
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
โค้ดนี้จะวางรูปร่างเส้นบนสไลด์
## ขั้นตอนที่ 6: ใช้การหมุน 3 มิติกับเส้น
สุดท้ายเราจะใช้เอฟเฟ็กต์การหมุน 3 มิติให้กับรูปร่างเส้น
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
คล้ายกับรูปสี่เหลี่ยมผืนผ้า เราตั้งค่าคุณสมบัติ 3D ให้กับรูปร่างเส้น
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
หลังจากเพิ่มและกำหนดค่ารูปร่างของคุณแล้ว ให้บันทึกการนำเสนอ
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
รหัสนี้จะบันทึกการนำเสนอของคุณด้วยชื่อไฟล์ที่ระบุในรูปแบบที่ต้องการ
## บทสรุป
ขอแสดงความยินดี! คุณได้นำเอฟเฟ็กต์การหมุน 3 มิติไปใช้กับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว หากทำตามขั้นตอนเหล่านี้ คุณก็สามารถสร้างงานนำเสนอที่ดึงดูดสายตาและมีชีวิตชีวาได้ สำหรับการปรับแต่งเพิ่มเติมและฟีเจอร์ขั้นสูงเพิ่มเติม โปรดดูที่ [เอกสารประกอบ Aspose.Slides](https://reference-aspose.com/slides/java/).
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังในการสร้าง แก้ไข และจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่?
ใช่ คุณสามารถรับได้ [ทดลองใช้งานฟรี](https://releases.aspose.com/) หรือ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อทดสอบคุณสมบัติ
### ฉันสามารถเพิ่มเอฟเฟ็กต์ 3 มิติลงในรูปทรงประเภทใดได้บ้างใน Aspose.Slides
คุณสามารถเพิ่มเอฟเฟ็กต์ 3 มิติให้กับรูปร่างต่างๆ เช่น สี่เหลี่ยมผืนผ้า เส้น วงรี และรูปร่างที่กำหนดเองได้
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถเยี่ยมชม [ฟอรั่มสนับสนุน](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือและหารือปัญหาต่างๆ
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์ได้หรือไม่
ใช่ แต่คุณต้องซื้อใบอนุญาต คุณสามารถซื้อได้จาก [หน้าการซื้อ](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}