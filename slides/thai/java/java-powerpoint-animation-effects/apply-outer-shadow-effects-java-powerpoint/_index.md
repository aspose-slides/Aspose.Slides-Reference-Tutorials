---
title: ใช้เอฟเฟกต์เงาด้านนอกใน Java PowerPoint
linktitle: ใช้เอฟเฟกต์เงาด้านนอกใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีใช้เอฟเฟกต์เงาภายนอกในงานนำเสนอ Java PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides พร้อมคำแนะนำโดยละเอียดทีละขั้นตอนของเรา
weight: 11
url: /th/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ใช้เอฟเฟกต์เงาด้านนอกใน Java PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจมักต้องเพิ่มเอฟเฟ็กต์ต่างๆ เพื่อเพิ่มความสวยงามให้กับสไลด์ของคุณ เอฟเฟกต์อย่างหนึ่งคือเงาด้านนอก ซึ่งสามารถทำให้องค์ประกอบของคุณโดดเด่นและเพิ่มความลึกให้กับเนื้อหาของคุณได้ ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการใช้เอฟเฟกต์เงาภายนอกกับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกคำแนะนำทีละขั้นตอน เรามาตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ของออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java Library: ดาวน์โหลดเวอร์ชันล่าสุดจาก[Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเขียนและรันโค้ด Java ของคุณ
4.  ใบอนุญาต กำหนด ที่ถูกต้อง: คุณสามารถซื้อใบอนุญาตได้จาก[Aspose](https://purchase.aspose.com/buy) หรือได้รับ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการประเมินผล
## แพ็คเกจนำเข้า
ขั้นแรก คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides นี่เป็นการปูทางสำหรับการใช้ประโยชน์จากฟังก์ชันอันทรงพลังที่ห้องสมุดมีให้
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
เรามาแจกแจงขั้นตอนการใช้เอฟเฟกต์เงาภายนอกเป็นขั้นตอนที่สามารถจัดการได้:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการ
ก่อนที่คุณจะเริ่มเขียนโค้ด คุณต้องตั้งค่าไดเร็กทอรีโปรเจ็กต์ที่จะจัดเก็บและเข้าถึงไฟล์ PowerPoint ของคุณ
ตรวจสอบให้แน่ใจว่าไดเร็กทอรีโปรเจ็กต์ของคุณมีอยู่ หากไม่เป็นเช่นนั้น ให้สร้างขึ้นโดยใช้รหัสต่อไปนี้:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ตอนนี้ เราต้องเริ่มต้นการนำเสนอโดยที่เราจะเพิ่มรูปร่างและเอฟเฟ็กต์ของเรา

 สร้างอินสแตนซ์ใหม่ของ`Presentation` ชั้นเรียนเพื่อเริ่มทำงานกับไฟล์ PowerPoint ใหม่
```java
// สร้างอินสแตนซ์คลาส PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง
จากนั้น เพิ่มสไลด์ลงในงานนำเสนอของคุณ จากนั้นเพิ่มรูปร่างที่คุณจะใช้เอฟเฟกต์เงา
### รับการอ้างอิงถึงสไลด์
ดึงข้อมูลอ้างอิงไปยังสไลด์แรกในงานนำเสนอ
```java
// รับข้อมูลอ้างอิงของสไลด์
ISlide sld = pres.getSlides().get_Item(0);
```
### เพิ่มรูปร่างอัตโนมัติ
เพิ่มรูปร่างอัตโนมัติรูปสี่เหลี่ยมผืนผ้าลงในสไลด์ตามพิกัดที่ระบุ
```java
// เพิ่มประเภทสี่เหลี่ยมผืนผ้ารูปร่างอัตโนมัติ
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## ขั้นตอนที่ 4: ปรับแต่งรูปร่าง
เพิ่มข้อความลงในรูปร่างของคุณและปรับการตั้งค่าการเติมเพื่อทำให้เอฟเฟกต์เงามองเห็นได้ชัดเจนยิ่งขึ้น
### เพิ่ม TextFrame ให้กับรูปร่าง
แทรกข้อความลงในรูปทรงสี่เหลี่ยมผืนผ้า
```java
// เพิ่ม TextFrame ให้กับสี่เหลี่ยมผืนผ้า
aShp.addTextFrame("Aspose TextBox");
```
### ปิดการใช้งานการเติมรูปร่าง
ปิดใช้งานการเติมรูปร่างเพื่อเน้นเงาของข้อความ
```java
// ปิดการใช้งานการเติมรูปร่างในกรณีที่เราต้องการได้รับเงาของข้อความ
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## ขั้นตอนที่ 5: ใช้เอฟเฟกต์เงาด้านนอก
ตอนนี้ได้เวลาใช้เอฟเฟกต์เงาด้านนอกกับรูปร่างแล้ว
### เปิดใช้งานเอฟเฟกต์เงาภายนอก
เปิดใช้งานเอฟเฟกต์เงาภายนอกสำหรับรูปร่าง
```java
// เพิ่มเงาด้านนอกและตั้งค่าพารามิเตอร์ที่จำเป็นทั้งหมด
aShp.getEffectFormat().enableOuterShadowEffect();
```
### กำหนดค่าพารามิเตอร์เงา
ตั้งค่าคุณสมบัติต่างๆ ของเงา เช่น รัศมีการเบลอ ทิศทาง ระยะทาง การจัดแนว และสี
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอลงดิสก์
```java
//เขียนงานนำเสนอลงดิสก์
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: กำจัดทรัพยากร
ตรวจสอบให้แน่ใจว่าคุณปล่อยทรัพยากรโดยการกำจัดออบเจ็กต์การนำเสนอ
```java
// ทำความสะอาดทรัพยากร
if (pres != null) pres.dispose();
```
## บทสรุป
และคุณก็ได้แล้ว! คุณใช้เอฟเฟกต์เงาภายนอกกับรูปร่างในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java เอฟเฟ็กต์นี้สามารถเพิ่มความน่าสนใจให้กับสไลด์ของคุณได้อย่างมาก ทำให้เนื้อหาของคุณโดดเด่น
 หากคุณประสบปัญหาใดๆ หรือต้องการความช่วยเหลือเพิ่มเติม อย่าลังเลที่จะตรวจสอบ[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) หรือเยี่ยมชมได้ที่[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11)- ขอให้มีความสุขในการเขียนโค้ด!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ในแอปพลิเคชัน Java
### ฉันจะทดลองใช้ Aspose.Slides สำหรับ Java ฟรีได้อย่างไร
 คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/).
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ใด ๆ ได้หรือไม่
ได้ คุณสามารถใช้ Aspose.Slides สำหรับ Java กับ Java IDE ใดก็ได้ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
### ฉันจะรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[เว็บไซต์กำหนด](https://purchase.aspose.com/temporary-license/).
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถดูตัวอย่างเพิ่มเติมและเอกสารประกอบโดยละเอียดได้ที่[หน้าเอกสารประกอบของ Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
