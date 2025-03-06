---
title: ใช้เงาด้านนอกใน PowerPoint กับ Java
linktitle: ใช้เงาด้านนอกใน PowerPoint กับ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการใช้เอฟเฟกต์เงาภายนอกใน PowerPoint โดยใช้ Java กับ Aspose.Slides ปรับปรุงการนำเสนอของคุณด้วยความลึกและดึงดูดสายตา
weight: 13
url: /th/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่ดึงดูดสายตามักจะเกี่ยวข้องกับการเพิ่มเอฟเฟ็กต์ต่างๆ ให้กับรูปร่างและข้อความ เอฟเฟกต์อย่างหนึ่งคือเงาด้านนอก ซึ่งสามารถทำให้องค์ประกอบโดดเด่นและเพิ่มความลึกให้กับสไลด์ของคุณได้ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้เอฟเฟกต์เงาภายนอกกับรูปร่างใน PowerPoint โดยใช้ Java กับ Aspose.Slides
## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จากเว็บไซต์ Oracle

2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).

3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก Java IDE ที่คุณต้องการ เช่น Eclipse, IntelliJ IDEA หรือ NetBeans สำหรับการเขียนโค้ดและการรันแอปพลิเคชัน Java

4. ความรู้ Java ขั้นพื้นฐาน: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม Java และแนวคิดเชิงวัตถุจะเป็นประโยชน์สำหรับการทำความเข้าใจตัวอย่างโค้ด

## แพ็คเกจนำเข้า

ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides และฟังก์ชันที่เกี่ยวข้องในโปรเจ็กต์ Java ของคุณ:

```java
import com.aspose.slides.*;
```

ตอนนี้เราจะแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อใช้เอฟเฟกต์เงาด้านนอกกับรูปร่างใน PowerPoint โดยใช้ Java กับ Aspose.Slides:

## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมโครงการของคุณ

สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่ม Aspose.Slides สำหรับไลบรารี Java ไปยังพาธการสร้างโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ

 สร้างอินสแตนซ์ของ`Presentation` คลาสซึ่งแสดงถึงไฟล์งานนำเสนอ PowerPoint

```java
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง

รับข้อมูลอ้างอิงไปยังสไลด์ที่คุณต้องการเพิ่มรูปร่าง แล้วเพิ่มรูปร่างอัตโนมัติ (เช่น สี่เหลี่ยมผืนผ้า) ลงในสไลด์

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## ขั้นตอนที่ 4: ปรับแต่งรูปร่าง

ตั้งค่าประเภทการเติมของรูปร่างเป็น 'NoFill' และเพิ่มข้อความให้กับรูปร่าง

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## ขั้นตอนที่ 5: ปรับแต่งข้อความ

เข้าถึงคุณสมบัติข้อความของรูปร่างและปรับแต่งขนาดตัวอักษร

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## ขั้นตอนที่ 6: เปิดใช้งานเอฟเฟกต์เงาด้านนอก

เปิดใช้งานเอฟเฟกต์เงาด้านนอกสำหรับส่วนข้อความ

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## ขั้นตอนที่ 7: ตั้งค่าพารามิเตอร์เงา

กำหนดพารามิเตอร์สำหรับเอฟเฟกต์เงาภายนอก เช่น รัศมีการเบลอ ทิศทาง ระยะทาง และสีของเงา

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## ขั้นตอนที่ 8: บันทึกงานนำเสนอ

บันทึกงานนำเสนอที่แก้ไขแล้วโดยใช้เอฟเฟ็กต์เงาด้านนอกที่นำไปใช้กับรูปร่าง

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## บทสรุป

ยินดีด้วย! คุณนำเอฟเฟกต์เงาภายนอกไปใช้กับรูปร่างใน PowerPoint ได้สำเร็จโดยใช้ Java กับ Aspose.Slides ทดลองใช้พารามิเตอร์ต่างๆ เพื่อให้ได้เอฟเฟ็กต์ภาพที่ต้องการในการนำเสนอของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถใช้เอฟเฟกต์เงาด้านนอกกับรูปร่างอื่นนอกเหนือจากสี่เหลี่ยมได้หรือไม่
ได้ คุณสามารถใช้เอฟเฟกต์เงาด้านนอกกับรูปร่างต่างๆ ที่ Aspose.Slides รองรับ เช่น วงกลม สามเหลี่ยม และรูปร่างแบบกำหนดเอง

### สามารถปรับสีและความเข้มของเงาได้หรือไม่?
อย่างแน่นอน! คุณสามารถควบคุมพารามิเตอร์เงาได้อย่างเต็มที่ รวมถึงสี รัศมีการเบลอ ทิศทาง และระยะห่าง

### ฉันสามารถใช้เอฟเฟ็กต์หลายรายการกับรูปร่างเดียวกันได้หรือไม่
ได้ คุณสามารถรวมเอฟเฟ็กต์ต่างๆ เข้าด้วยกัน เช่น เงาด้านนอก เงาด้านใน เรืองแสง และการสะท้อน เพื่อเพิ่มรูปลักษณ์ที่สวยงามของรูปร่างและข้อความในงานนำเสนอของคุณ

### Aspose.Slides รองรับการใช้เอฟเฟกต์กับองค์ประกอบข้อความหรือไม่
ใช่ คุณสามารถใช้เอฟเฟ็กต์ได้ไม่เพียงแต่กับรูปร่างเท่านั้น แต่ยังรวมถึงส่วนข้อความแต่ละรายการภายในรูปร่างด้วย ทำให้คุณมีความยืดหยุ่นในการออกแบบสไลด์ของคุณอย่างกว้างขวาง

### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/java/) สำหรับการอ้างอิง API โดยละเอียดและสำรวจ[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการอภิปรายของชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
