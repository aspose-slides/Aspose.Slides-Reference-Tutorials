---
"description": "เรียนรู้วิธีการเติมรูปร่างด้วยรูปภาพในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพิ่มความน่าสนใจให้กับภาพได้อย่างง่ายดาย"
"linktitle": "เติมรูปร่างด้วยรูปภาพใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เติมรูปร่างด้วยรูปภาพใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เติมรูปร่างด้วยรูปภาพใน PowerPoint

## การแนะนำ
การนำเสนอ PowerPoint มักต้องการองค์ประกอบภาพ เช่น รูปร่างที่เต็มไปด้วยรูปภาพ เพื่อเพิ่มความน่าสนใจและถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java มอบชุดเครื่องมืออันทรงพลังเพื่อให้ทำงานนี้ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการเติมรูปร่างด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้โหลดแพ็กเกจที่จำเป็น:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีโครงการ
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
ให้แน่ใจว่าจะเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีโครงการของคุณ
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
```java
Presentation pres = new Presentation();
```
สร้างตัวอย่าง `Presentation` ชั้นเรียนเพื่อสร้างการนำเสนอ PowerPoint ใหม่
## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
เพิ่มสไลด์ลงในงานนำเสนอและสร้างรูปทรงสี่เหลี่ยมผืนผ้าบนนั้น
## ขั้นตอนที่ 4: ตั้งค่าประเภทการเติมเป็นรูปภาพ
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
ตั้งค่าประเภทการเติมของรูปร่างให้เป็นภาพ
## ขั้นตอนที่ 5: ตั้งค่าโหมดเติมภาพ
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
ตั้งค่าโหมดเติมภาพของรูปร่าง
## ขั้นตอนที่ 6: ตั้งค่ารูปภาพ
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
โหลดภาพและตั้งค่าเป็นการเติมให้กับรูปร่าง
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์

## บทสรุป
การใช้ Aspose.Slides สำหรับ Java ช่วยให้การเติมรูปภาพลงในรูปร่างต่างๆ ในงานนำเสนอ PowerPoint กลายเป็นกระบวนการที่ง่ายดาย เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณก็ปรับปรุงงานนำเสนอของคุณด้วยองค์ประกอบที่ดึงดูดสายตาได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถเติมรูปร่างต่างๆ ด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับการเติมรูปภาพลงในรูปทรงต่างๆ ช่วยให้การออกแบบมีความยืดหยุ่น
### Aspose.Slides สำหรับ Java สามารถใช้งานร่วมกับ PowerPoint ทุกเวอร์ชันได้หรือไม่
Aspose.Slides สำหรับ Java สร้างการนำเสนอที่เข้ากันได้กับ PowerPoint 97 ขึ้นไป ช่วยให้มั่นใจถึงความเข้ากันได้อย่างกว้างขวาง
### ฉันจะปรับขนาดรูปภาพภายในรูปร่างได้อย่างไร?
คุณสามารถปรับขนาดภาพภายในรูปร่างได้ โดยปรับขนาดของรูปร่างหรือปรับขนาดภาพให้เหมาะสมก่อนตั้งค่าเป็นการเติม
### มีข้อจำกัดใด ๆ เกี่ยวกับรูปแบบภาพที่รองรับสำหรับการกรอกรูปร่างหรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบภาพหลากหลาย เช่น JPEG, PNG, GIF, BMP และ TIFF เป็นต้น
### ฉันสามารถใช้เอฟเฟ็กต์กับรูปร่างที่เติมสีแล้วได้ไหม
ใช่ Aspose.Slides สำหรับ Java มี API ที่ครอบคลุมในการใช้เอฟเฟ็กต์ต่างๆ เช่น เงา การสะท้อน และการหมุน 3 มิติ กับรูปทรงที่เต็มไปด้วย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}