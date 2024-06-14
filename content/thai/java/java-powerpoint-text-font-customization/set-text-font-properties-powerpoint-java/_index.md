---
title: ตั้งค่าคุณสมบัติแบบอักษรข้อความใน PowerPoint ด้วย Java
linktitle: ตั้งค่าคุณสมบัติแบบอักษรข้อความใน PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าคุณสมบัติแบบอักษรของข้อความใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนง่ายๆ สำหรับนักพัฒนา Java#เรียนรู้วิธีจัดการคุณสมบัติแบบอักษรข้อความ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนทีละขั้นตอนสำหรับนักพัฒนา Java
type: docs
weight: 18
url: /th/java/java-powerpoint-text-font-customization/set-text-font-properties-powerpoint-java/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อตั้งค่าคุณสมบัติแบบอักษรข้อความต่างๆ ในงานนำเสนอ PowerPoint โดยทางโปรแกรม เราจะครอบคลุมการตั้งค่าประเภทแบบอักษร สไตล์ (ตัวหนา ตัวเอียง) ขีดเส้นใต้ ขนาด และสีของข้อความในสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- JDK ติดตั้งอยู่บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่นการตั้งค่า IntelliJ IDEA หรือ Eclipse
## แพ็คเกจนำเข้า
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าคลาส Aspose.Slides ที่จำเป็นแล้ว:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน IDE ของคุณและเพิ่มไลบรารี Aspose.Slides ลงในพาธการสร้างโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` วัตถุที่จะทำงานกับไฟล์ PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์และเพิ่มรูปร่างอัตโนมัติ
รับสไลด์แรกและเพิ่มรูปร่างอัตโนมัติ (สี่เหลี่ยมผืนผ้า) ลงไป:
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
## ขั้นตอนที่ 4: ตั้งค่าข้อความเป็นรูปร่างอัตโนมัติ
ตั้งค่าเนื้อหาข้อความเป็นรูปร่างอัตโนมัติ:
```java
ITextFrame textFrame = shape.getTextFrame();
textFrame.setText("Aspose TextBox");
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติแบบอักษร
เข้าถึงส่วนของข้อความและตั้งค่าคุณสมบัติแบบอักษรต่างๆ:
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
// ตั้งค่าตระกูลแบบอักษร
portion.getPortionFormat().setLatinFont(new FontData("Times New Roman"));
// ตั้งค่าตัวหนา
portion.getPortionFormat().setFontBold(NullableBool.True);
// ตั้งค่าตัวเอียง
portion.getPortionFormat().setFontItalic(NullableBool.True);
// ตั้งค่าขีดเส้นใต้
portion.getPortionFormat().setFontUnderline(TextUnderlineType.Single);
// ตั้งค่าขนาดตัวอักษร
portion.getPortionFormat().setFontHeight(25);
// ตั้งค่าสีตัวอักษร
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์:
```java
presentation.save(dataDir + "SetTextFontProperties_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 7: ทรัพยากรการล้างข้อมูล
กำจัดวัตถุการนำเสนอเพื่อเผยแพร่ทรัพยากร:
```java
if (presentation != null) {
    presentation.dispose();
}
```

## บทสรุป
ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีใช้ Aspose.Slides สำหรับ Java เพื่อปรับแต่งคุณสมบัติแบบอักษรของข้อความในสไลด์ PowerPoint แบบไดนามิก ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถจัดรูปแบบข้อความให้ตรงตามข้อกำหนดการออกแบบเฉพาะทางทางโปรแกรมได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถนำการเปลี่ยนแปลงแบบอักษรเหล่านี้ไปใช้กับข้อความที่มีอยู่ในสไลด์ PowerPoint ได้หรือไม่
 ใช่ คุณสามารถแก้ไขข้อความที่มีอยู่ได้โดยเข้าไปที่ข้อความนั้น`Portion` และใช้คุณสมบัติแบบอักษรที่ต้องการ
### ฉันจะเปลี่ยนสีแบบอักษรเป็นการไล่ระดับสีหรือการเติมลวดลายได้อย่างไร
 แทน`SolidFillColor` , ใช้`GradientFillColor` หรือ`PatternedFillColor` ตามนั้น
### Aspose.Slides เข้ากันได้กับเทมเพลต PowerPoint (.potx) หรือไม่
ได้ คุณสามารถใช้ Aspose.Slides เพื่อทำงานกับเทมเพลต PowerPoint
### Aspose.Slides รองรับการส่งออกเป็นรูปแบบ PDF หรือไม่
ใช่ Aspose.Slides อนุญาตให้ส่งออกงานนำเสนอเป็นรูปแบบต่างๆ รวมถึง PDF
### ฉันจะขอความช่วยเหลือและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน
 เยี่ยม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและคำแนะนำจากชุมชน