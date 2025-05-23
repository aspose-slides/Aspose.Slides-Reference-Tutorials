---
"description": "เรียนรู้วิธีการเปลี่ยนลำดับรูปร่างใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนแบบทีละขั้นตอนนี้ พัฒนาทักษะการนำเสนอของคุณได้อย่างง่ายดาย"
"linktitle": "การเปลี่ยนลำดับรูปร่างใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การเปลี่ยนลำดับรูปร่างใน PowerPoint"
"url": "/th/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเปลี่ยนลำดับรูปร่างใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่มีโครงสร้างสวยงามและดึงดูดสายตาอาจเป็นงานที่ยากลำบาก อย่างไรก็ตาม คุณสามารถทำให้ทุกอย่างง่ายขึ้นได้อย่างมากด้วยเครื่องมือและเทคนิคที่เหมาะสม Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้คุณจัดการและปรับแต่งงานนำเสนอ PowerPoint ได้ด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนต่างๆ ในการเปลี่ยนลำดับรูปร่างในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK ไว้ในเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ออราเคิล](https://www-oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides สำหรับ Java Library: ดาวน์โหลดเวอร์ชันล่าสุดได้จาก [หน้าดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases-aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE): ใช้ IDE เช่น IntelliJ IDEA หรือ Eclipse สำหรับการเขียนโค้ด
4. ไฟล์การนำเสนอ: เตรียมไฟล์ PowerPoint ที่คุณต้องการจัดการ
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็คเกจที่จำเป็นจากไลบรารี Aspose.Slides การนำเข้าเหล่านี้จะช่วยให้คุณทำงานกับงานนำเสนอ สไลด์ และรูปทรงได้
```java
import com.aspose.slides.*;

```
ในคู่มือนี้ เราจะแบ่งขั้นตอนการเปลี่ยนแปลงลำดับรูปร่างออกเป็นหลายขั้นตอน เพื่อให้เข้าใจได้ดีขึ้นและใช้งานได้ง่าย
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
ขั้นแรก คุณต้องโหลดไฟล์นำเสนอ PowerPoint ที่คุณต้องการใช้งาน ขั้นตอนนี้เกี่ยวข้องกับการเริ่มต้นใช้งาน `Presentation` คลาสที่มีเส้นทางไปยังไฟล์ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## ขั้นตอนที่ 2: เข้าถึงสไลด์ที่ต้องการ
เมื่อโหลดงานนำเสนอเสร็จแล้ว ให้เข้าถึงสไลด์ที่คุณต้องการเรียงลำดับรูปร่างใหม่ สไลด์จะมีดัชนีเริ่มจาก 0 ดังนั้นหากต้องการเข้าถึงสไลด์แรก ให้ใช้ดัชนี 0
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: เพิ่มรูปร่างลงในสไลด์
ขั้นตอนต่อไปคือการเพิ่มรูปทรงลงในสไลด์ สำหรับการสาธิต เราจะเพิ่มรูปทรงสี่เหลี่ยมผืนผ้าและสามเหลี่ยมลงในสไลด์
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## ขั้นตอนที่ 4: เรียงลำดับรูปร่างใหม่
ตอนนี้ให้เรียงลำดับรูปร่างบนสไลด์ใหม่ `reorder` วิธีการนี้ช่วยให้คุณระบุตำแหน่งใหม่สำหรับรูปร่างภายในคอลเลกชันรูปร่างของสไลด์ได้
```java
slide.getShapes().reorder(2, shp3);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอที่แก้ไขแล้ว
หลังจากจัดเรียงรูปร่างใหม่แล้ว ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังไฟล์ใหม่ วิธีนี้จะช่วยให้ไฟล์ต้นฉบับของคุณไม่เปลี่ยนแปลง
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## ขั้นตอนที่ 6: ทำความสะอาดทรัพยากร
สุดท้าย กำจัดวัตถุที่นำเสนอเพื่อปลดปล่อยทรัพยากร
```java
if (presentation1 != null) presentation1.dispose();
```
## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณสามารถเปลี่ยนลำดับของรูปร่างในสไลด์ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ช่วยลดความซับซ้อนของงานต่างๆ ที่เกี่ยวข้องกับการนำเสนอ PowerPoint ทำให้คุณสามารถสร้างและจัดการสไลด์ด้วยโปรแกรมได้ ไม่ว่าคุณจะกำลังสร้างการนำเสนอโดยอัตโนมัติหรือเพียงแค่ต้องการเปลี่ยนแปลงจำนวนมาก Aspose.Slides สำหรับ Java ก็เป็นเครื่องมืออันล้ำค่า
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น Java API สำหรับการสร้างและจัดการการนำเสนอ PowerPoint โดยไม่ต้องใช้ Microsoft PowerPoint
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ร่วมกับ Java IDE อื่นๆ ได้หรือไม่
ใช่ คุณสามารถใช้ร่วมกับ Java IDE ใดๆ เช่น IntelliJ IDEA, Eclipse หรือ NetBeans ได้
### Aspose.Slides สำหรับ Java สามารถใช้งานร่วมกับรูปแบบ PowerPoint ทั้งหมดได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับ PPT, PPTX และรูปแบบ PowerPoint อื่นๆ
### ฉันจะได้รับรุ่นทดลองใช้งาน Aspose.Slides สำหรับ Java ฟรีได้อย่างไร
คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้จาก [หน้าดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาเอกสารรายละเอียดได้ที่ [หน้าเอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}