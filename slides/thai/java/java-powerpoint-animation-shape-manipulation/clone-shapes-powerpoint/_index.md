---
title: รูปร่างโคลนใน PowerPoint
linktitle: รูปร่างโคลนใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีโคลนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงขั้นตอนการทำงานของคุณด้วยบทช่วยสอนที่ปฏิบัติตามง่ายนี้
weight: 16
url: /th/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีการโคลนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การโคลนรูปร่างทำให้คุณสามารถทำซ้ำรูปร่างที่มีอยู่ภายในงานนำเสนอได้ ซึ่งจะเป็นประโยชน์อย่างยิ่งสำหรับการสร้างเลย์เอาต์ที่สอดคล้องกันหรือทำซ้ำองค์ประกอบในสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit บนระบบของคุณ คุณสามารถดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลดและรวม Aspose.Slides สำหรับไลบรารี Java ในโปรเจ็กต์ Java ของคุณ คุณสามารถค้นหาลิงค์ดาวน์โหลด[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้มีฟังก์ชันที่จำเป็นในการทำงานกับงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
 ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีรูปร่างที่คุณต้องการโคลน ใช้`Presentation` คลาสเพื่อโหลดการนำเสนอต้นฉบับ
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## ขั้นตอนที่ 2: โคลนรูปร่าง
จากนั้น คุณจะลอกเลียนแบบรูปร่างจากงานนำเสนอต้นฉบับและเพิ่มลงในสไลด์ใหม่ในงานนำเสนอเดียวกัน ซึ่งเกี่ยวข้องกับการเข้าถึงรูปร่างของแหล่งที่มา การสร้างสไลด์ใหม่ จากนั้นจึงเพิ่มรูปร่างที่ลอกแบบมาลงในสไลด์ใหม่
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## ขั้นตอนที่ 3: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วด้วยรูปร่างที่ลอกแบบมาลงในไฟล์ใหม่
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การโคลนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการที่ไม่ซับซ้อนซึ่งสามารถช่วยปรับปรุงเวิร์กโฟลว์การสร้างงานนำเสนอของคุณได้ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถทำซ้ำรูปร่างที่มีอยู่และปรับแต่งได้ตามต้องการได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถโคลนรูปร่างบนสไลด์ต่างๆ ได้หรือไม่
ได้ คุณสามารถโคลนรูปร่างจากสไลด์ใดๆ ในงานนำเสนอ และเพิ่มลงในสไลด์อื่นได้โดยใช้ Aspose.Slides for Java
### การโคลนรูปร่างมีข้อจำกัดหรือไม่?
แม้ว่า Aspose.Slides สำหรับ Java จะมีความสามารถในการโคลนนิ่งที่มีประสิทธิภาพ แต่รูปร่างหรือภาพเคลื่อนไหวที่ซับซ้อนอาจไม่สามารถจำลองได้อย่างสมบูรณ์แบบ
### ฉันสามารถแก้ไขรูปร่างที่โคลนหลังจากเพิ่มลงในสไลด์ได้หรือไม่
แน่นอน เมื่อรูปร่างถูกโคลนและเพิ่มลงในสไลด์แล้ว คุณสามารถแก้ไขคุณสมบัติ สไตล์ และเนื้อหาได้ตามต้องการ
### Aspose.Slides สำหรับ Java รองรับการโคลนองค์ประกอบอื่น ๆ นอกเหนือจากรูปร่างหรือไม่
ได้ คุณสามารถโคลนสไลด์ ข้อความ รูปภาพ และองค์ประกอบอื่นๆ ภายในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันทดลองใช้ฟรีได้จาก[เว็บไซต์](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
