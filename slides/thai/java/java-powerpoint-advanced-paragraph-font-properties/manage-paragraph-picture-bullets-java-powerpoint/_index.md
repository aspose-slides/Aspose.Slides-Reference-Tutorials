---
title: จัดการสัญลักษณ์แสดงหัวข้อย่อยรูปภาพย่อหน้าใน Java PowerPoint
linktitle: จัดการสัญลักษณ์แสดงหัวข้อย่อยรูปภาพย่อหน้าใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มสัญลักษณ์แสดงหัวข้อย่อยรูปภาพแบบกำหนดเองลงในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำโดยละเอียดทีละขั้นตอนนี้เพื่อการบูรณาการที่ราบรื่น
weight: 11
url: /th/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดการสัญลักษณ์แสดงหัวข้อย่อยรูปภาพย่อหน้าใน Java PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่น่าดึงดูดและดึงดูดสายตาเป็นทักษะที่สำคัญในโลกธุรกิจสมัยใหม่ นักพัฒนา Java สามารถใช้ประโยชน์จาก Aspose.Slides เพื่อปรับปรุงการนำเสนอด้วยสัญลักษณ์หัวข้อย่อยที่กำหนดเองในสไลด์ PowerPoint บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทีละขั้นตอน เพื่อให้มั่นใจว่าคุณสามารถเพิ่มหัวข้อย่อยรูปภาพในงานนำเสนอของคุณได้อย่างมั่นใจ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ IDEA
- Aspose.Slides สำหรับไลบรารี Java
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ไฟล์รูปภาพสำหรับรูปภาพหัวข้อย่อย
 หากต้องการดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java โปรดไปที่[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/) - สำหรับเอกสารโปรดตรวจสอบที่[เอกสารประกอบ](https://reference.aspose.com/slides/java/).
## แพ็คเกจนำเข้า
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นสำหรับโครงการของคุณแล้ว เพิ่มการนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
เรามาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
สร้างไดเรกทอรีใหม่สำหรับโครงการของคุณ ไดเร็กทอรีนี้จะมีไฟล์ Java, ไลบรารี Aspose.Slides และไฟล์รูปภาพสำหรับสัญลักษณ์แสดงหัวข้อย่อย
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
 เริ่มต้นอินสแตนซ์ใหม่ของ`Presentation` ระดับ. วัตถุนี้แสดงถึงงานนำเสนอ PowerPoint ของคุณ
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
เข้าถึงสไลด์แรกของงานนำเสนอ สไลด์มีการจัดทำดัชนีเป็นศูนย์ ดังนั้นสไลด์แรกจึงอยู่ที่ดัชนี 0
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: โหลดอิมเมจ Bullet
โหลดรูปภาพที่คุณต้องการใช้สำหรับสัญลักษณ์แสดงหัวข้อย่อย ภาพนี้ควรอยู่ในไดเร็กทอรีโครงการของคุณ
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างอัตโนมัติให้กับสไลด์
เพิ่มรูปร่างอัตโนมัติลงในสไลด์ รูปร่างจะมีข้อความพร้อมสัญลักษณ์แสดงหัวข้อย่อยแบบกำหนดเอง
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## ขั้นตอนที่ 6: เข้าถึงกรอบข้อความ
เข้าถึงกรอบข้อความของรูปร่างอัตโนมัติเพื่อจัดการย่อหน้า
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## ขั้นตอนที่ 7: ลบย่อหน้าเริ่มต้น
ลบย่อหน้าเริ่มต้นที่เพิ่มลงในกรอบข้อความโดยอัตโนมัติ
```java
textFrame.getParagraphs().removeAt(0);
```
## ขั้นตอนที่ 8: สร้างย่อหน้าใหม่
สร้างย่อหน้าใหม่และตั้งค่าข้อความ ย่อหน้านี้จะมีสัญลักษณ์แสดงหัวข้อย่อยรูปภาพแบบกำหนดเอง
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## ขั้นตอนที่ 9: ตั้งค่าสไตล์สัญลักษณ์แสดงหัวข้อย่อยและรูปภาพ
ตั้งค่าสไตล์สัญลักษณ์แสดงหัวข้อย่อยเพื่อใช้รูปภาพที่กำหนดเองที่โหลดไว้ก่อนหน้านี้
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## ขั้นตอนที่ 10: ปรับความสูงของกระสุน
กำหนดความสูงของสัญลักษณ์แสดงหัวข้อย่อยเพื่อให้แน่ใจว่าดูดีในการนำเสนอ
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## ขั้นตอนที่ 11: เพิ่มย่อหน้าลงในกรอบข้อความ
เพิ่มย่อหน้าที่สร้างขึ้นใหม่ลงในกรอบข้อความของรูปร่างอัตโนมัติ
```java
textFrame.getParagraphs().add(paragraph);
```
## ขั้นตอนที่ 12: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอเป็นทั้งไฟล์ PPTX และ PPT
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## บทสรุป
 และคุณก็ได้แล้ว! เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มหัวข้อย่อยรูปภาพแบบกำหนดเองลงในงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้นำเสนอคุณสมบัติที่หลากหลายเพื่อช่วยให้คุณสร้างงานนำเสนอระดับมืออาชีพและดึงดูดสายตา อย่าลืมไปสำรวจ[เอกสารประกอบ](https://reference.aspose.com/slides/java/)สำหรับคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันสามารถใช้รูปภาพใด ๆ สำหรับหัวข้อย่อยรูปภาพได้หรือไม่
ได้ คุณสามารถใช้รูปภาพใดๆ สำหรับหัวข้อย่อยรูปภาพได้ ตราบใดที่สามารถเข้าถึงได้จากไดเร็กทอรีโปรเจ็กต์ของคุณ
### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่
 Aspose.Slides สำหรับ Java ต้องมีใบอนุญาตเพื่อการใช้งานเต็มรูปแบบ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) หรือซื้อใบอนุญาตแบบเต็ม[ที่นี่](https://purchase.aspose.com/buy).
### ฉันสามารถเพิ่มหลายย่อหน้าด้วยสไตล์สัญลักษณ์แสดงหัวข้อย่อยที่แตกต่างกันในรูปร่างอัตโนมัติเดียวได้หรือไม่
ได้ คุณสามารถเพิ่มหลายย่อหน้าด้วยสไตล์สัญลักษณ์แสดงหัวข้อย่อยที่แตกต่างกันให้กับรูปร่างอัตโนมัติเดียวได้โดยการสร้างและกำหนดค่าแต่ละย่อหน้าแยกกัน
### ฉันจะหาตัวอย่างและการสนับสนุนเพิ่มเติมได้ที่ไหน
 คุณสามารถดูตัวอย่างเพิ่มเติมได้ใน[เอกสารประกอบ](https://reference.aspose.com/slides/java/) และรับการสนับสนุนจากชุมชน Aspose บน[ฟอรั่ม](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
