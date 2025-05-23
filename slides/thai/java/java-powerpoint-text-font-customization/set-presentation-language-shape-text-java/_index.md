---
"description": "เรียนรู้วิธีการสร้างการนำเสนอ PowerPoint อัตโนมัติโดยใช้ Aspose.Slides สำหรับ Java สร้าง แก้ไข และปรับปรุงสไลด์ด้วยโปรแกรมได้อย่างง่ายดาย"
"linktitle": "ตั้งค่าภาษาการนำเสนอและข้อความรูปร่างใน Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าภาษาการนำเสนอและข้อความรูปร่างใน Java"
"url": "/th/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าภาษาการนำเสนอและข้อความรูปร่างใน Java

## การแนะนำ
การสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรมใน Java จะช่วยเพิ่มประสิทธิภาพการทำงานอัตโนมัติของเวิร์กโฟลว์และเพิ่มประสิทธิภาพการทำงานได้ Aspose.Slides สำหรับ Java มอบชุดเครื่องมืออันแข็งแกร่งเพื่อทำงานเหล่านี้ได้อย่างมีประสิทธิภาพ บทช่วยสอนนี้จะแนะนำคุณเกี่ยวกับขั้นตอนสำคัญในการตั้งค่าภาษาของงานนำเสนอและกำหนดรูปแบบข้อความโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.Slides สำหรับไลบรารี Java ซึ่งคุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/slides/java/)
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse ที่ติดตั้งบนระบบของคุณ
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็กเกจ Aspose.Slides ที่จำเป็นลงในไฟล์ Java ของคุณ:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
เริ่มต้นโดยการเริ่มต้น `Presentation` วัตถุ:
```java
Presentation pres = new Presentation();
```
นี่จะสร้างการนำเสนอ PowerPoint ใหม่
## ขั้นตอนที่ 2: เพิ่มและกำหนดค่า AutoShape
ขั้นตอนต่อไป เพิ่ม AutoShape ลงในสไลด์แรกและกำหนดค่าคุณสมบัติของมัน:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
ที่นี่ เราเพิ่มรูปสี่เหลี่ยมผืนผ้า AutoShape ที่พิกัด (50, 50) โดยมีขนาด 200x50 พิกเซล
## ขั้นตอนที่ 3: ตั้งค่าข้อความและภาษา
ตั้งค่าเนื้อหาข้อความและระบุภาษาสำหรับการตรวจสอบการสะกดคำ:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
แทนที่ `"Text to apply spellcheck language"` พร้อมข้อความตามต้องการ รหัสภาษา `"en-EN"` ระบุเป็นภาษาอังกฤษ (สหรัฐอเมริกา)
## ขั้นตอนที่ 4: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขแล้วไปยังไดเร็กทอรีเอาท์พุตที่ระบุ:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
ให้แน่ใจว่าจะเปลี่ยน `"Your Output Directory"` ด้วยเส้นทางไดเร็กทอรีจริงของคุณที่คุณต้องการบันทึกไฟล์
## ขั้นตอนที่ 5: กำจัดทรัพยากร
กำจัดอย่างถูกวิธี `Presentation` คัดค้านการปล่อยทรัพยากร:
```java
pres.dispose();
```
ขั้นตอนนี้เป็นสิ่งสำคัญเพื่อหลีกเลี่ยงการรั่วไหลของหน่วยความจำ

## บทสรุป
โดยสรุป Aspose.Slides สำหรับ Java ช่วยลดความยุ่งยากของกระบวนการสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถตั้งค่าภาษาของการนำเสนอและกำหนดค่าคุณสมบัติข้อความตามความต้องการของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างงานนำเสนอ PowerPoint ตั้งแต่เริ่มต้นได้หรือไม่
ใช่ Aspose.Slides มี API ที่ครอบคลุมเพื่อสร้างการนำเสนอโดยใช้โปรแกรมทั้งหมด
### ฉันจะใช้แบบอักษรที่แตกต่างกันกับข้อความในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้อย่างไร
คุณสามารถตั้งค่าคุณสมบัติแบบอักษรได้ผ่าน `IPortionFormat` วัตถุที่เกี่ยวข้องกับส่วนข้อความ
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถรับการทดลองใช้ฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
เอกสารรายละเอียดมีให้ [ที่นี่](https://reference-aspose.com/slides/java/).
### มีตัวเลือกการสนับสนุนอะไรบ้างสำหรับ Aspose.Slides สำหรับ Java?
คุณสามารถเยี่ยมชมฟอรั่ม Aspose.Slides ได้ [ที่นี่](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนชุมชน

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}