---
"description": "เรียนรู้วิธีเพิ่มภาพหัวข้อย่อยแบบกำหนดเองลงในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนโดยละเอียดนี้เพื่อการผสานรวมที่ราบรื่น"
"linktitle": "การจัดการย่อหน้า รูปภาพ หัวข้อย่อยใน Java PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การจัดการย่อหน้า รูปภาพ หัวข้อย่อยใน Java PowerPoint"
"url": "/th/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การจัดการย่อหน้า รูปภาพ หัวข้อย่อยใน Java PowerPoint

## การแนะนำ
การสร้างงานนำเสนอที่ดึงดูดใจและดึงดูดสายตาเป็นทักษะที่สำคัญในโลกธุรกิจยุคใหม่ นักพัฒนา Java สามารถใช้ประโยชน์จาก Aspose.Slides เพื่อปรับปรุงงานนำเสนอของตนด้วยภาพสัญลักษณ์ที่ปรับแต่งเองในสไลด์ PowerPoint บทช่วยสอนนี้จะแนะนำคุณตลอดขั้นตอนต่างๆ เพื่อให้แน่ใจว่าคุณสามารถเพิ่มภาพสัญลักษณ์ลงในงานนำเสนอของคุณได้อย่างมั่นใจ
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ โปรดแน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) แล้ว
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Eclipse หรือ IntelliJ IDEA
- Aspose.Slides สำหรับไลบรารี Java
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- ไฟล์ภาพสำหรับภาพกระสุน
หากต้องการดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ให้ไปที่ [หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/). สำหรับเอกสารประกอบ โปรดตรวจสอบ [เอกสารประกอบ](https://reference-aspose.com/slides/java/).
## แพ็คเกจนำเข้า
ขั้นแรก ให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นสำหรับโครงการของคุณแล้ว เพิ่มการนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
มาแบ่งกระบวนการออกเป็นขั้นตอนที่สามารถจัดการได้
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการของคุณ
สร้างไดเร็กทอรีใหม่สำหรับโปรเจ็กต์ของคุณ ไดเร็กทอรีนี้จะมีไฟล์ Java ไลบรารี Aspose.Slides และไฟล์รูปภาพสำหรับหัวข้อย่อย
```java
String dataDir = "Your Document Directory";
```
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
เริ่มต้นอินสแตนซ์ใหม่ของ `Presentation` คลาส วัตถุนี้แสดงถึงการนำเสนอ PowerPoint ของคุณ
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
เข้าถึงสไลด์แรกของการนำเสนอ สไลด์มีดัชนีเป็นศูนย์ ดังนั้นสไลด์แรกจึงอยู่ที่ดัชนี 0
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 4: โหลดภาพกระสุน
โหลดรูปภาพที่คุณต้องการใช้สำหรับหัวข้อย่อย รูปภาพนี้ควรวางไว้ในไดเร็กทอรีโครงการของคุณ
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## ขั้นตอนที่ 5: เพิ่มรูปร่างอัตโนมัติลงในสไลด์
เพิ่ม AutoShape ลงในสไลด์ รูปร่างจะประกอบด้วยข้อความพร้อมจุดหัวข้อแบบกำหนดเอง
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## ขั้นตอนที่ 6: เข้าถึงกรอบข้อความ
เข้าถึงกรอบข้อความของ AutoShape เพื่อจัดการย่อหน้า
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## ขั้นตอนที่ 7: ลบย่อหน้าเริ่มต้น
ลบย่อหน้าเริ่มต้นที่ถูกเพิ่มไปยังกรอบข้อความโดยอัตโนมัติ
```java
textFrame.getParagraphs().removeAt(0);
```
## ขั้นตอนที่ 8: สร้างย่อหน้าใหม่
สร้างย่อหน้าใหม่และตั้งค่าข้อความ ย่อหน้านี้จะมีหัวข้อรูปภาพแบบกำหนดเอง
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## ขั้นตอนที่ 9: ตั้งค่ารูปแบบกระสุนและรูปภาพ
ตั้งค่ารูปแบบหัวข้อย่อยเพื่อใช้รูปภาพแบบกำหนดเองที่โหลดไว้ก่อนหน้านี้
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## ขั้นตอนที่ 10: ปรับความสูงของกระสุน
กำหนดความสูงของหัวข้อย่อยเพื่อให้แน่ใจว่าจะดูดีในการนำเสนอ
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## ขั้นตอนที่ 11: เพิ่มย่อหน้าลงในกรอบข้อความ
เพิ่มย่อหน้าที่เพิ่งสร้างใหม่ลงในกรอบข้อความของ AutoShape
```java
textFrame.getParagraphs().add(paragraph);
```
## ขั้นตอนที่ 12: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกการนำเสนอเป็นทั้งไฟล์ PPTX และไฟล์ PPT
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## บทสรุป
และแล้วคุณก็ทำได้! ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถเพิ่มภาพสัญลักษณ์ที่กำหนดเองลงในงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้มีคุณสมบัติมากมายที่จะช่วยให้คุณสร้างงานนำเสนอที่เป็นมืออาชีพและดึงดูดสายตา อย่าลืมสำรวจ [เอกสารประกอบ](https://reference.aspose.com/slides/java/) สำหรับคุณสมบัติขั้นสูงและตัวเลือกการปรับแต่งเพิ่มเติม
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนา Java สามารถสร้าง แก้ไข และจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม
### ฉันสามารถใช้รูปภาพใด ๆ สำหรับภาพหัวข้อย่อยได้หรือไม่
ใช่ คุณสามารถใช้รูปภาพใดๆ สำหรับภาพหัวข้อย่อยได้ ตราบใดที่สามารถเข้าถึงได้จากไดเร็กทอรีโครงการของคุณ
### ฉันต้องมีใบอนุญาตเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่
Aspose.Slides สำหรับ Java ต้องมีใบอนุญาตจึงจะใช้งานได้เต็มรูปแบบ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก [ที่นี่](https://purchase.aspose.com/temporary-license/) หรือซื้อใบอนุญาตเต็มรูปแบบ [ที่นี่](https://purchase-aspose.com/buy).
### ฉันสามารถเพิ่มย่อหน้าหลายย่อหน้าโดยใช้รูปแบบหัวข้อย่อยที่ต่างกันใน AutoShape เดียวได้หรือไม่
ใช่ คุณสามารถเพิ่มย่อหน้าหลายย่อหน้าด้วยรูปแบบหัวข้อย่อยที่ต่างกันลงใน AutoShape เดียวได้โดยการสร้างและกำหนดค่าแต่ละย่อหน้าทีละรายการ
### ฉันสามารถหาตัวอย่างและการสนับสนุนเพิ่มเติมได้ที่ไหน
คุณสามารถค้นหาตัวอย่างเพิ่มเติมได้ใน [เอกสารประกอบ](https://reference.aspose.com/slides/java/) และรับการสนับสนุนจากชุมชน Aspose บน [ฟอรั่ม](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}