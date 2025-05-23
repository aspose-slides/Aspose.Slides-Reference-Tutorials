---
"description": "เรียนรู้วิธีใช้เอฟเฟกต์เงาภายนอกใน PowerPoint โดยใช้ Java ด้วย Aspose.Slides ปรับปรุงการนำเสนอของคุณด้วยความลึกและความสวยงาม"
"linktitle": "ใช้เงาภายนอกใน PowerPoint ด้วย Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ใช้เงาภายนอกใน PowerPoint ด้วย Java"
"url": "/th/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ใช้เงาภายนอกใน PowerPoint ด้วย Java

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจมักเกี่ยวข้องกับการเพิ่มเอฟเฟกต์ต่างๆ ให้กับรูปร่างและข้อความ เอฟเฟกต์ดังกล่าวอย่างหนึ่งคือเงาภายนอก ซึ่งสามารถทำให้องค์ประกอบต่างๆ โดดเด่นและเพิ่มความลึกให้กับสไลด์ของคุณได้ ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีใช้เอฟเฟกต์เงาภายนอกกับรูปร่างใน PowerPoint โดยใช้ Java กับ Aspose.Slides
## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK เวอร์ชันล่าสุดได้จากเว็บไซต์ของ Oracle

2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก [หน้าดาวน์โหลด](https://releases-aspose.com/slides/java/).

3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): เลือก Java IDE ที่คุณต้องการ เช่น Eclipse, IntelliJ IDEA หรือ NetBeans สำหรับการเขียนโค้ดและรันแอปพลิเคชัน Java

4. ความรู้พื้นฐานเกี่ยวกับ Java: ความคุ้นเคยกับพื้นฐานของภาษาการเขียนโปรแกรม Java และแนวคิดเชิงวัตถุจะเป็นประโยชน์สำหรับการทำความเข้าใจตัวอย่างโค้ด

## แพ็คเกจนำเข้า

ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides และฟังก์ชันที่เกี่ยวข้องในโครงการ Java ของคุณ:

```java
import com.aspose.slides.*;
```

ตอนนี้เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอนเพื่อใช้เอฟเฟกต์เงาภายนอกกับรูปร่างใน PowerPoint โดยใช้ Java กับ Aspose.Slides:

## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมโครงการของคุณ

สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่ม Aspose.Slides สำหรับไลบรารี Java ลงในเส้นทางการสร้างโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: เริ่มต้นวัตถุการนำเสนอ

สร้างอินสแตนซ์ของ `Presentation` คลาสซึ่งแสดงถึงไฟล์การนำเสนอ PowerPoint

```java
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง

รับการอ้างอิงไปยังสไลด์ที่คุณต้องการเพิ่มรูปร่าง จากนั้นเพิ่มรูปร่างอัตโนมัติ (เช่น สี่เหลี่ยมผืนผ้า) ลงในสไลด์

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## ขั้นตอนที่ 4: ปรับแต่งรูปร่าง

ตั้งค่าประเภทการเติมของรูปร่างเป็น 'NoFill' และเพิ่มข้อความลงในรูปร่าง

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## ขั้นตอนที่ 5: ปรับแต่งข้อความ

เข้าถึงคุณสมบัติข้อความของรูปร่างและปรับแต่งขนาดแบบอักษร

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## ขั้นตอนที่ 6: เปิดใช้งานเอฟเฟกต์เงาภายนอก

เปิดใช้งานเอฟเฟกต์เงาด้านนอกให้กับส่วนข้อความ

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## ขั้นตอนที่ 7: ตั้งค่าพารามิเตอร์เงา

กำหนดพารามิเตอร์สำหรับเอฟเฟกต์เงาภายนอก เช่น รัศมีการเบลอ ทิศทาง ระยะทาง และสีเงา

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## ขั้นตอนที่ 8: บันทึกการนำเสนอ

บันทึกงานนำเสนอที่แก้ไขแล้วโดยใช้เอฟเฟกต์เงาด้านนอกกับรูปร่าง

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## บทสรุป

ขอแสดงความยินดี! คุณได้ใช้เอฟเฟกต์เงาภายนอกกับรูปร่างใน PowerPoint โดยใช้ Java กับ Aspose.Slides สำเร็จแล้ว ทดลองใช้พารามิเตอร์ต่างๆ เพื่อให้ได้เอฟเฟกต์ภาพตามต้องการในงานนำเสนอของคุณ

## คำถามที่พบบ่อย

### ฉันสามารถใช้เอฟเฟ็กต์เงาด้านนอกกับรูปร่างอื่นนอกจากสี่เหลี่ยมผืนผ้าได้ไหม
ใช่ คุณสามารถใช้เอฟเฟกต์เงาด้านนอกกับรูปทรงต่างๆ ที่ได้รับการรองรับโดย Aspose.Slides เช่น วงกลม รูปสามเหลี่ยม และรูปทรงที่กำหนดเอง

### สามารถปรับแต่งสีและความเข้มของเงาได้หรือไม่?
แน่นอน! คุณสามารถควบคุมพารามิเตอร์เงาได้เต็มที่ ไม่ว่าจะเป็นสี รัศมีการเบลอ ทิศทาง และระยะห่าง

### ฉันสามารถใช้เอฟเฟ็กต์ต่างๆ กับรูปร่างเดียวกันได้ไหม
ใช่ คุณสามารถรวมเอฟเฟ็กต์ต่างๆ เข้าด้วยกัน เช่น เงาภายนอก เงาภายใน แสงเรืองรอง และการสะท้อนแสง เพื่อเพิ่มความสวยงามให้กับรูปทรงและข้อความในงานนำเสนอของคุณได้

### Aspose.Slides รองรับการใช้เอฟเฟกต์กับองค์ประกอบข้อความหรือไม่
ใช่ คุณสามารถใช้เอฟเฟ็กต์ไม่เพียงแค่กับรูปร่างเท่านั้น แต่ยังรวมถึงส่วนข้อความแต่ละส่วนในรูปร่างได้ด้วย ทำให้คุณมีความยืดหยุ่นในการออกแบบสไลด์อย่างกว้างขวาง

### ฉันสามารถหาทรัพยากรและการสนับสนุนเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด
คุณสามารถอ้างอิงได้ที่ [เอกสารประกอบ](https://reference.aspose.com/slides/java/) สำหรับข้อมูลอ้างอิง API โดยละเอียดและสำรวจ [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและการหารือของชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}