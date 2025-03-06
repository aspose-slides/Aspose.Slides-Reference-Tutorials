---
title: คุณสมบัติแบบอักษรใน PowerPoint พร้อม Java
linktitle: คุณสมบัติแบบอักษรใน PowerPoint พร้อม Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการคุณสมบัติแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Java กับ Aspose.Slides สำหรับ Java ปรับแต่งแบบอักษรได้อย่างง่ายดายด้วยคำแนะนำทีละขั้นตอนนี้
weight: 11
url: /th/java/java-powerpoint-font-management/font-properties-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการคุณสมบัติแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Java โดยเฉพาะกับ Aspose.Slides สำหรับ Java เราจะแนะนำคุณตลอดแต่ละขั้นตอน ตั้งแต่การนำเข้าแพ็คเกจที่จำเป็นไปจนถึงการบันทึกงานนำเสนอที่คุณแก้ไข มาดำน้ำกันเถอะ!
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java JAR: ดาวน์โหลด Aspose.Slides สำหรับไลบรารี Java จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): คุณสามารถใช้ Java IDE ใดก็ได้ตามที่คุณต้องการ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans

## แพ็คเกจนำเข้า
ขั้นแรก เรามานำเข้าแพ็คเกจที่จำเป็นเพื่อทำงานกับ Aspose.Slides สำหรับ Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## ขั้นตอนที่ 1: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
 เริ่มต้นด้วยการสร้าง`Presentation` วัตถุที่แสดงถึงไฟล์ PowerPoint ของคุณ:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์และตัวยึดตำแหน่ง
ตอนนี้ เรามาเข้าถึงสไลด์และตัวยึดตำแหน่งในงานนำเสนอของคุณกันดีกว่า:
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## ขั้นตอนที่ 3: เข้าถึงย่อหน้าและส่วนต่างๆ
ต่อไป เราจะเข้าถึงย่อหน้าและส่วนต่างๆ ภายในกรอบข้อความ:
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## ขั้นตอนที่ 4: กำหนดแบบอักษรใหม่
กำหนดแบบอักษรที่คุณต้องการใช้สำหรับส่วนต่างๆ:
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## ขั้นตอนที่ 5: ตั้งค่าคุณสมบัติแบบอักษร
ตั้งค่าคุณสมบัติแบบอักษรต่างๆ เช่น ตัวหนา ตัวเอียง และสี:
```java
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## ขั้นตอนที่ 6: บันทึกงานนำเสนอที่แก้ไข
สุดท้าย ให้บันทึกงานนำเสนอที่คุณแก้ไขแล้วลงในดิสก์:
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การจัดการคุณสมบัติแบบอักษรในงานนำเสนอ PowerPoint โดยใช้ Java ทำได้ง่ายด้วย Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถปรับแต่งแบบอักษรเพื่อเพิ่มความสวยงามให้กับสไลด์ของคุณได้
## คำถามที่พบบ่อย
### ฉันสามารถใช้แบบอักษรที่กำหนดเองกับ Aspose.Slides สำหรับ Java ได้หรือไม่
 ได้ คุณสามารถใช้แบบอักษรแบบกำหนดเองได้โดยระบุชื่อแบบอักษรขณะกำหนด`FontData`.
### ฉันจะเปลี่ยนขนาดตัวอักษรของข้อความในสไลด์ PowerPoint ได้อย่างไร
 คุณสามารถปรับขนาดตัวอักษรได้โดยการตั้งค่า`FontHeight` ทรัพย์สินของ`PortionFormat`.
### Aspose.Slides สำหรับ Java รองรับการเพิ่มเอฟเฟกต์ข้อความหรือไม่
ใช่ Aspose.Slides สำหรับ Java มีตัวเลือกเอฟเฟกต์ข้อความมากมายเพื่อปรับปรุงการนำเสนอของคุณ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### ฉันจะค้นหาการสนับสนุนและทรัพยากรเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถเยี่ยมชมฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและเอกสาร[ที่นี่](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
