---
title: สร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิต
linktitle: สร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิต
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างวัตถุผสมในรูปทรงเรขาคณิตโดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนที่ครอบคลุมนี้ เหมาะสำหรับนักพัฒนา Java
weight: 20
url: /th/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# สร้างวัตถุคอมโพสิตในรูปทรงเรขาคณิต

## การแนะนำ
สวัสดี! คุณเคยต้องการที่จะสร้างรูปทรงที่น่าทึ่งและซับซ้อนในงานนำเสนอ PowerPoint ของคุณโดยใช้ Java หรือไม่? คุณอยู่ในสถานที่ที่เหมาะสม ในบทช่วยสอนนี้ เราจะเจาะลึกไลบรารี Aspose.Slides สำหรับ Java อันทรงพลังเพื่อสร้างออบเจ็กต์ผสมในรูปทรงเรขาคณิต ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น คำแนะนำทีละขั้นตอนนี้จะช่วยให้คุณบรรลุผลลัพธ์ที่น่าประทับใจได้ในเวลาอันรวดเร็ว พร้อมที่จะเริ่มต้นหรือยัง? มาดำน้ำกันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะพูดถึงโค้ด มีบางสิ่งที่คุณต้องการ:
- Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK 1.8 ขึ้นไปบนเครื่องของคุณ
- สภาพแวดล้อมการพัฒนาแบบผสมผสาน (IDE): IDE เช่น IntelliJ IDEA หรือ Eclipse จะทำให้ชีวิตของคุณง่ายขึ้น
-  Aspose.Slides สำหรับ Java: คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/) หรือใช้ Maven เพื่อรวมไว้ในโครงการของคุณ
- ความรู้พื้นฐานของ Java: บทช่วยสอนนี้ถือว่าคุณมีความเข้าใจพื้นฐานของ Java
## แพ็คเกจนำเข้า
ก่อนอื่น เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อเริ่มต้นใช้งาน Aspose.Slides สำหรับ Java กันก่อน
```java
import com.aspose.slides.*;

```

การสร้างวัตถุคอมโพสิตอาจฟังดูซับซ้อน แต่การแบ่งมันออกเป็นขั้นตอนที่สามารถจัดการได้ คุณจะพบว่ามันง่ายกว่าที่คุณคิด เราจะสร้างงานนำเสนอ PowerPoint เพิ่มรูปร่าง จากนั้นกำหนดและใช้เส้นทางเรขาคณิตหลายเส้นทางเพื่อสร้างรูปร่างคอมโพสิต
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
 ก่อนที่คุณจะเขียนโค้ดใดๆ ให้ตั้งค่าโปรเจ็กต์ Java ของคุณ สร้างโปรเจ็กต์ใหม่ใน IDE ของคุณและรวม Aspose.Slides สำหรับ Java คุณสามารถเพิ่มไลบรารีโดยใช้ Maven หรือดาวน์โหลดไฟล์ JAR จากไฟล์[หน้าดาวน์โหลด Aspose.Slides](https://releases.aspose.com/slides/java/).
### การเพิ่ม Aspose.Slides ในโครงการของคุณโดยใช้ Maven
 หากคุณใช้ Maven ให้เพิ่มการพึ่งพาต่อไปนี้ให้กับ your`pom.xml` ไฟล์:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
ตอนนี้เรามาสร้างงานนำเสนอ PowerPoint ใหม่กันดีกว่า เราจะเริ่มต้นด้วยการเริ่มต้น`Presentation` ระดับ.
```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: สร้างรูปร่างใหม่
ต่อไป เราจะเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าใหม่ลงในสไลด์แรกของงานนำเสนอของเรา
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## ขั้นตอนที่ 4: กำหนดเส้นทางเรขาคณิตแรก
 เราจะกำหนดส่วนแรกของรูปร่างประกอบโดยการสร้าง`GeometryPath` และเพิ่มคะแนนเข้าไป
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## ขั้นตอนที่ 5: กำหนดเส้นทางเรขาคณิตที่สอง
ในทำนองเดียวกัน ให้กำหนดส่วนที่สองของรูปร่างประกอบของเรา
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## ขั้นตอนที่ 6: รวมเส้นทางเรขาคณิต
รวมเส้นทางเรขาคณิตทั้งสองเข้าด้วยกันแล้วกำหนดให้เป็นรูปร่าง
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอของคุณเป็นไฟล์
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## ขั้นตอนที่ 8: ทำความสะอาดทรัพยากร
ตรวจสอบให้แน่ใจว่าคุณเผยแพร่ทรัพยากรใดๆ ที่ใช้ในการนำเสนอ
```java
if (pres != null) pres.dispose();
```
## บทสรุป
และคุณก็ได้แล้ว! คุณสร้างรูปร่างผสมโดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ด้วยการแบ่งกระบวนการออกเป็นขั้นตอนง่ายๆ คุณสามารถสร้างรูปทรงที่ซับซ้อนและปรับปรุงการนำเสนอของคุณได้อย่างง่ายดาย ทดลองเส้นทางเรขาคณิตต่างๆ ต่อไปเพื่อสร้างการออกแบบที่มีเอกลักษณ์
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ใน Java
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถติดตั้งโดยใช้ Maven หรือดาวน์โหลดไฟล์ JAR จากไฟล์[เว็บไซต์](https://releases.aspose.com/slides/java/).
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่
 ใช่ แต่คุณจะต้องซื้อใบอนุญาต สามารถดูรายละเอียดเพิ่มเติมได้ที่[หน้าซื้อ](https://purchase.aspose.com/buy).
### มีการทดลองใช้ฟรีหรือไม่?
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารและความช่วยเหลือเพิ่มเติมได้จากที่ไหน?
 ตรวจสอบ[เอกสารประกอบ](https://reference.aspose.com/slides/java/) และ[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
