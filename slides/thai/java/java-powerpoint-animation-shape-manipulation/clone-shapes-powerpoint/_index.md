---
"description": "เรียนรู้วิธีโคลนรูปทรงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงเวิร์กโฟลว์ของคุณด้วยบทช่วยสอนที่ทำตามได้ง่ายนี้"
"linktitle": "โคลนรูปร่างใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "โคลนรูปร่างใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# โคลนรูปร่างใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการโคลนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การโคลนรูปร่างช่วยให้คุณสามารถทำซ้ำรูปร่างที่มีอยู่แล้วในงานนำเสนอได้ ซึ่งมีประโยชน์อย่างยิ่งสำหรับการสร้างเค้าโครงที่สม่ำเสมอหรือการทำซ้ำองค์ประกอบต่างๆ ในสไลด์
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้งเวอร์ชันล่าสุดได้จาก [เว็บไซต์](https://www-oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับไลบรารี Java: ดาวน์โหลดและรวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ Java ของคุณ คุณสามารถค้นหาลิงก์ดาวน์โหลด [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้มีฟังก์ชันการทำงานที่จำเป็นสำหรับการทำงานกับการนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
```java
import com.aspose.slides.*;

```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
ขั้นแรก คุณต้องโหลดงานนำเสนอ PowerPoint ที่มีรูปร่างที่คุณต้องการโคลน ใช้ `Presentation` คลาสที่จะโหลดการนำเสนอแหล่งที่มา
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## ขั้นตอนที่ 2: โคลนรูปร่าง
ขั้นตอนต่อไปคือโคลนรูปร่างจากงานนำเสนอต้นฉบับและเพิ่มรูปร่างเหล่านี้ลงในสไลด์ใหม่ในงานนำเสนอเดียวกัน ซึ่งต้องเข้าถึงรูปร่างต้นฉบับ สร้างสไลด์ใหม่ แล้วจึงเพิ่มรูปร่างที่โคลนลงในสไลด์ใหม่
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
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วด้วยรูปร่างที่โคลนไปยังไฟล์ใหม่
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การโคลนรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เป็นกระบวนการตรงไปตรงมาที่สามารถช่วยปรับกระบวนการสร้างงานนำเสนอของคุณให้มีประสิทธิภาพยิ่งขึ้น ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถทำซ้ำรูปร่างที่มีอยู่และปรับแต่งตามต้องการได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถโคลนรูปร่างต่างๆ ลงในสไลด์ต่างๆ ได้หรือไม่
ใช่ คุณสามารถโคลนรูปร่างจากสไลด์ใดๆ ในงานนำเสนอและเพิ่มลงในสไลด์อื่นได้โดยใช้ Aspose.Slides สำหรับ Java
### การโคลนรูปร่างมีข้อจำกัดใด ๆ หรือไม่?
แม้ว่า Aspose.Slides สำหรับ Java จะมีความสามารถในการโคลนที่แข็งแกร่ง แต่รูปร่างหรือแอนิเมชันที่ซับซ้อนอาจไม่สามารถจำลองได้อย่างสมบูรณ์แบบ
### ฉันสามารถแก้ไขรูปร่างที่โคลนหลังจากเพิ่มลงในสไลด์แล้วได้หรือไม่
แน่นอน เมื่อโคลนและเพิ่มรูปร่างลงในสไลด์แล้ว คุณสามารถปรับเปลี่ยนคุณสมบัติ สไตล์ และเนื้อหาของรูปร่างตามต้องการได้
### Aspose.Slides สำหรับ Java รองรับการโคลนองค์ประกอบอื่นนอกเหนือจากรูปร่างหรือไม่
ใช่ คุณสามารถโคลนสไลด์ ข้อความ รูปภาพ และองค์ประกอบอื่นๆ ภายในงานนำเสนอ PowerPoint ได้โดยใช้ Aspose.Slides สำหรับ Java
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันทดลองใช้งานฟรีได้จาก [เว็บไซต์](https://releases-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}