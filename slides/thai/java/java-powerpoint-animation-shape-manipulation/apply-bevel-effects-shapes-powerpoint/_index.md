---
title: ใช้เอฟเฟกต์เอียงกับรูปร่างใน PowerPoint
linktitle: ใช้เอฟเฟกต์เอียงกับรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้เอฟเฟกต์เอียงกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java พร้อมคำแนะนำทีละขั้นตอนของเรา ปรับปรุงการนำเสนอของคุณ
weight: 13
url: /th/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ใช้เอฟเฟกต์เอียงกับรูปร่างใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญในการดึงดูดความสนใจของผู้ชม การเพิ่มเอฟเฟ็กต์เอียงให้กับรูปร่างสามารถเสริมความสวยงามโดยรวมของสไลด์ได้ ทำให้งานนำเสนอของคุณโดดเด่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้เอฟเฟกต์มุมเอียงกับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ไม่ว่าคุณจะเป็นนักพัฒนาที่ต้องการสร้างงานนำเสนอแบบอัตโนมัติหรือเพียงผู้ที่รักการปรับแต่งการออกแบบ คู่มือนี้ก็ครอบคลุมทุกอย่างแล้ว
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides สำหรับ Java Library: ดาวน์โหลดไลบรารีจาก[Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/).
- IDE (สภาพแวดล้อมการพัฒนาแบบรวม): ใช้ IDE ใดก็ได้ที่คุณเลือก เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
-  Aspose License: หากต้องการใช้ Aspose.Slides โดยไม่มีข้อจำกัด ให้ขอรับใบอนุญาตจาก[กำหนดให้จัดซื้อ](https://purchase.aspose.com/buy) หรือได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล
## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
 ก่อนที่คุณจะเริ่มเขียนโค้ดได้ ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณได้รับการตั้งค่าอย่างถูกต้อง รวมไลบรารี Aspose.Slides ไว้ในเส้นทางการสร้างโปรเจ็กต์ของคุณ หากคุณใช้ Maven ให้เพิ่มการพึ่งพาต่อไปนี้ให้กับ your`pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
 หากต้องการเริ่มทำงานกับ Aspose.Slides คุณต้องสร้างอินสแตนซ์ของ`Presentation` ระดับ. คลาสนี้นำเสนอไฟล์ PowerPoint
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
หลังจากสร้างงานนำเสนอแล้ว ให้เข้าถึงสไลด์แรกที่คุณจะเพิ่มและปรับแต่งรูปร่าง
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างให้กับสไลด์
ตอนนี้ เพิ่มรูปร่างให้กับสไลด์ ในตัวอย่างนี้ เราจะเพิ่มวงรี
```java
// เพิ่มรูปร่างบนสไลด์
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## ขั้นตอนที่ 5: ใช้เอฟเฟกต์เอียงกับรูปร่าง
จากนั้น ใช้เอฟเฟกต์เอียงกับรูปร่างเพื่อให้มีลักษณะเป็นสามมิติ
```java
// ตั้งค่าคุณสมบัติ ThreeDFormat ของรูปร่าง
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย บันทึกงานนำเสนอเป็นไฟล์ PPTX ไปยังไดเร็กทอรีที่คุณระบุ
```java
// เขียนงานนำเสนอเป็นไฟล์ PPTX
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: กำจัดวัตถุการนำเสนอ
 หากต้องการเพิ่มทรัพยากร ให้ตรวจสอบให้แน่ใจเสมอว่า`Presentation` วัตถุถูกกำจัดอย่างเหมาะสม
```java
if (pres != null) pres.dispose();
```
## บทสรุป
 การใช้เอฟเฟกต์มุมเอียงกับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ไม่ซับซ้อนซึ่งสามารถปรับปรุงรูปลักษณ์ของสไลด์ของคุณได้อย่างมาก ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถสร้างงานนำเสนอที่เป็นมืออาชีพและน่าสนใจได้อย่างง่ายดาย อย่าลืมสำรวจ[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับข้อมูลรายละเอียดเพิ่มเติมและคุณสมบัติขั้นสูง
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ได้ฟรีหรือไม่
 Aspose.Slides ให้ทดลองใช้ฟรีซึ่งคุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/)- หากต้องการคุณสมบัติครบถ้วน คุณต้องซื้อใบอนุญาต
### ฉันสามารถเพิ่มรูปร่างประเภทใดลงในสไลด์ได้
คุณสามารถเพิ่มรูปร่างต่างๆ เช่น สี่เหลี่ยม วงรี เส้น และรูปร่างที่กำหนดเองได้โดยใช้ Aspose.Slides สำหรับ Java
### เป็นไปได้ไหมที่จะใช้เอฟเฟกต์ 3D อื่น ๆ นอกเหนือจากมุมเอียง?
ใช่ Aspose.Slides สำหรับ Java อนุญาตให้คุณใช้เอฟเฟกต์ 3D ที่หลากหลาย รวมถึงความลึก แสง และเอฟเฟกต์กล้อง
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose และทีมสนับสนุนได้[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
