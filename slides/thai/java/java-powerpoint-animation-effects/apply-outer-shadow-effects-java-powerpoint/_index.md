---
"description": "เรียนรู้วิธีการใช้เอฟเฟกต์เงาภายนอกในงานนำเสนอ Java PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดของเรา"
"linktitle": "ใช้เอฟเฟกต์เงาภายนอกใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ใช้เอฟเฟกต์เงาภายนอกใน Java PowerPoint"
"url": "/th/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ใช้เอฟเฟกต์เงาภายนอกใน Java PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดใจมักต้องเพิ่มเอฟเฟกต์ต่างๆ เพื่อเพิ่มความสวยงามให้กับสไลด์ของคุณ เอฟเฟกต์ดังกล่าวอย่างหนึ่งคือเงาภายนอก ซึ่งสามารถทำให้องค์ประกอบต่างๆ ของคุณโดดเด่นขึ้นและเพิ่มความลึกให้กับเนื้อหาของคุณได้ ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนการใช้เอฟเฟกต์เงาภายนอกกับรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกคู่มือทีละขั้นตอน เรามาตรวจสอบกันก่อนว่าคุณมีทุกสิ่งที่คุณต้องการ:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ของออราเคิล](https://www-oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับ Java Library: ดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides สำหรับ Java](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเขียนและดำเนินการโค้ด Java ของคุณ
4. ใบอนุญาต Aspose ที่ถูกต้อง: คุณสามารถซื้อใบอนุญาตได้จาก [อาโปเซ่](https://purchase.aspose.com/buy) หรือรับ [ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) เพื่อการประเมินผล
## แพ็คเกจนำเข้า
ขั้นแรก คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นสำหรับ Aspose.Slides การดำเนินการนี้จะช่วยเตรียมการสำหรับการใช้ฟังก์ชันอันทรงพลังที่ไลบรารีจัดเตรียมไว้ให้
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
มาแบ่งกระบวนการการใช้เอฟเฟกต์เงาภายนอกออกเป็นขั้นตอนที่จัดการได้:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการ
ก่อนที่คุณจะเริ่มเขียนโค้ด คุณต้องตั้งค่าไดเร็กทอรีของโครงการที่คุณจะเก็บและเข้าถึงไฟล์ PowerPoint ของคุณ
ตรวจสอบให้แน่ใจว่าไดเรกทอรีโครงการของคุณมีอยู่ หากไม่มี ให้สร้างโดยใช้โค้ดต่อไปนี้:
```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ตอนนี้ เราต้องเริ่มการนำเสนอซึ่งเราจะเพิ่มรูปทรงและเอฟเฟกต์ต่างๆ

สร้างอินสแตนซ์ใหม่ของ `Presentation` ชั้นเรียนเพื่อเริ่มทำงานกับไฟล์ PowerPoint ใหม่
```java
// สร้างอินสแตนซ์คลาส PPTX
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง
ขั้นตอนต่อไปคือเพิ่มสไลด์ลงในงานนำเสนอของคุณ จากนั้นเพิ่มรูปร่างที่คุณจะใช้เอฟเฟกต์เงา
### รับข้อมูลอ้างอิงสำหรับสไลด์
ดึงข้อมูลอ้างอิงไปยังสไลด์แรกในงานนำเสนอ
```java
// รับข้อมูลอ้างอิงของสไลด์
ISlide sld = pres.getSlides().get_Item(0);
```
### เพิ่มรูปร่างอัตโนมัติ
เพิ่มรูปสี่เหลี่ยมผืนผ้า AutoShape ลงในสไลด์ตามพิกัดที่ระบุ
```java
// เพิ่มรูปร่างอัตโนมัติของชนิดสี่เหลี่ยมผืนผ้า
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## ขั้นตอนที่ 4: ปรับแต่งรูปร่าง
เพิ่มข้อความลงในรูปร่างของคุณและปรับการตั้งค่าการเติมเพื่อให้เอฟเฟกต์เงามองเห็นได้ชัดเจนขึ้น
### เพิ่ม TextFrame ลงในรูปร่าง
แทรกข้อความลงในรูปสี่เหลี่ยมผืนผ้า
```java
// เพิ่ม TextFrame ลงในสี่เหลี่ยมผืนผ้า
aShp.addTextFrame("Aspose TextBox");
```
### ปิดใช้งานการเติมรูปร่าง
ปิดใช้งานการเติมรูปร่างเพื่อเน้นเงาของข้อความ
```java
// ปิดใช้งานการเติมรูปร่างในกรณีที่เราต้องการให้ข้อความมีเงา
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## ขั้นตอนที่ 5: ใช้เอฟเฟกต์เงาภายนอก
ตอนนี้ถึงเวลาที่จะใช้เอฟเฟกต์เงาด้านนอกให้กับรูปร่างแล้ว
### เปิดใช้งานเอฟเฟกต์เงาภายนอก
เปิดใช้งานเอฟเฟ็กต์เงาด้านนอกให้กับรูปร่าง
```java
// เพิ่มเงาภายนอกและตั้งค่าพารามิเตอร์ที่จำเป็นทั้งหมด
aShp.getEffectFormat().enableOuterShadowEffect();
```
### กำหนดค่าพารามิเตอร์เงา
ตั้งค่าคุณสมบัติต่างๆ ของเงา เช่น รัศมีการเบลอ ทิศทาง ระยะทาง การจัดตำแหน่ง และสี
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอลงดิสก์
```java
//เขียนการนำเสนอลงดิสก์
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: กำจัดทรัพยากร
ตรวจสอบให้แน่ใจว่าคุณปล่อยทรัพยากรโดยการกำจัดวัตถุการนำเสนอ
```java
// ทำความสะอาดทรัพยากร
if (pres != null) pres.dispose();
```
## บทสรุป
และแล้วคุณก็ทำได้สำเร็จ! คุณได้ใช้เอฟเฟกต์เงาภายนอกกับรูปร่างในงานนำเสนอ PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java เอฟเฟกต์นี้สามารถเพิ่มความน่าสนใจให้กับสไลด์ของคุณได้อย่างมาก ทำให้เนื้อหาของคุณโดดเด่น
หากคุณประสบปัญหาใดๆ หรือต้องการความช่วยเหลือเพิ่มเติม โปรดอย่าลังเลที่จะตรวจสอบ [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/java/) หรือเยี่ยมชม [ฟอรั่มสนับสนุน](https://forum.aspose.com/c/slides/11). สนุกกับการเขียนโค้ด!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ในแอปพลิเคชัน Java ได้
### ฉันจะได้รับรุ่นทดลองใช้งาน Aspose.Slides สำหรับ Java ฟรีได้อย่างไร
คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [เว็บไซต์อาโพส](https://releases-aspose.com/).
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ IDE ใดๆ ได้หรือไม่
ใช่ คุณสามารถใช้ Aspose.Slides สำหรับ Java ร่วมกับ Java IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans ได้
### ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [เว็บไซต์อาโพส](https://purchase-aspose.com/temporary-license/).
### ฉันสามารถหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
คุณสามารถค้นหาตัวอย่างเพิ่มเติมและเอกสารรายละเอียดได้ที่ [หน้าเอกสาร Aspose.Slides](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}