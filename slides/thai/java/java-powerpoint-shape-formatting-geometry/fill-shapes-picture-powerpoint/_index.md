---
title: เติมรูปร่างด้วยรูปภาพใน PowerPoint
linktitle: เติมรูปร่างด้วยรูปภาพใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเติมรูปร่างด้วยรูปภาพในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพิ่มความดึงดูดสายตาได้อย่างง่ายดาย
weight: 12
url: /th/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
งานนำเสนอ PowerPoint มักต้องใช้องค์ประกอบภาพ เช่น รูปร่างที่เต็มไปด้วยรูปภาพ เพื่อเพิ่มความน่าสนใจและถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java มอบชุดเครื่องมืออันทรงพลังที่ช่วยให้งานนี้สำเร็จได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีเติมรูปร่างด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ดาวน์โหลด Aspose.Slides สำหรับไลบรารี Java แล้ว คุณสามารถรับได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็น:
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
 ให้แน่ใจว่าจะเปลี่ยน`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีโครงการของคุณ
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
```java
Presentation pres = new Presentation();
```
 ยกตัวอย่าง`Presentation` คลาสเพื่อสร้างงานนำเสนอ PowerPoint ใหม่
## ขั้นตอนที่ 3: เพิ่มสไลด์และรูปร่าง
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
เพิ่มสไลด์ลงในงานนำเสนอและสร้างรูปทรงสี่เหลี่ยมผืนผ้าบนสไลด์
## ขั้นตอนที่ 4: ตั้งค่าประเภทการเติมเป็นรูปภาพ
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
ตั้งค่าประเภทการเติมของรูปร่างให้กับรูปภาพ
## ขั้นตอนที่ 5: ตั้งค่าโหมดเติมรูปภาพ
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
ตั้งค่าโหมดการเติมรูปภาพของรูปร่าง
## ขั้นตอนที่ 6: ตั้งค่ารูปภาพ
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
โหลดรูปภาพและตั้งค่าเป็นการเติมรูปร่าง
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์

## บทสรุป
ด้วย Aspose.Slides สำหรับ Java การเติมรูปร่างด้วยรูปภาพในงานนำเสนอ PowerPoint จะกลายเป็นกระบวนการที่ไม่ซับซ้อน ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถเพิ่มประสิทธิภาพการนำเสนอของคุณด้วยองค์ประกอบที่ดึงดูดสายตาได้อย่างง่ายดาย

## คำถามที่พบบ่อย
### ฉันสามารถเติมรูปร่างต่างๆ ด้วยรูปภาพโดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับการเติมรูปร่างต่างๆ ด้วยรูปภาพ ซึ่งให้ความยืดหยุ่นในการออกแบบ
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides สำหรับ Java สร้างงานนำเสนอที่เข้ากันได้กับ PowerPoint 97 ขึ้นไป จึงรับประกันความเข้ากันได้ในวงกว้าง
### ฉันจะปรับขนาดรูปภาพภายในรูปร่างได้อย่างไร
คุณสามารถปรับขนาดรูปภาพภายในรูปร่างได้โดยการปรับขนาดของรูปร่างหรือปรับขนาดรูปภาพตามนั้นก่อนที่จะตั้งค่าเป็นการเติม
### มีข้อจำกัดเกี่ยวกับรูปแบบรูปภาพที่รองรับการเติมรูปร่างหรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบภาพที่หลากหลาย รวมถึง JPEG, PNG, GIF, BMP และ TIFF และอื่นๆ อีกมากมาย
### ฉันสามารถใช้เอฟเฟ็กต์กับรูปร่างที่เติมแล้วได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java มี API ที่ครอบคลุมเพื่อใช้เอฟเฟกต์ต่างๆ เช่น เงา การสะท้อน และการหมุน 3 มิติกับรูปร่างที่เติม
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
