---
title: เพิ่มกรอบรูปความสูงขนาดสัมพัทธ์ใน PowerPoint
linktitle: เพิ่มกรอบรูปความสูงขนาดสัมพัทธ์ใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มกรอบรูปที่มีความสูงสัมพัทธ์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพื่อปรับปรุงเนื้อหาภาพของคุณ
type: docs
weight: 15
url: /th/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2. Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มลงในโปรเจ็กต์ Java ของคุณ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีสำหรับโปรเจ็กต์ของคุณ และสภาพแวดล้อม Java ของคุณได้รับการกำหนดค่าอย่างเหมาะสม
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
สร้างวัตถุการนำเสนอใหม่โดยใช้ Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: โหลดรูปภาพที่จะเพิ่ม
โหลดรูปภาพที่คุณต้องการเพิ่มลงในงานนำเสนอ:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## ขั้นตอนที่ 4: เพิ่มกรอบรูปเพื่อสไลด์
เพิ่มกรอบรูปลงในสไลด์ในงานนำเสนอ:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## ขั้นตอนที่ 5: ตั้งค่าความกว้างและความสูงของสเกลสัมพันธ์
ตั้งค่าความกว้างและความสูงของสเกลสัมพัทธ์สำหรับกรอบรูป:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกงานนำเสนอด้วยกรอบรูปที่เพิ่ม:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มกรอบรูปที่มีความสูงสัมพัทธ์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ได้อย่างง่ายดาย ทดลองใช้ค่าขนาดต่างๆ เพื่อให้ได้รูปลักษณ์ที่ต้องการสำหรับภาพของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มกรอบรูปหลายเฟรมลงในสไลด์เดียวโดยใช้วิธีนี้ได้หรือไม่
ได้ คุณสามารถเพิ่มกรอบรูปหลายเฟรมลงในสไลด์ได้โดยทำซ้ำขั้นตอนสำหรับแต่ละภาพ
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความยืดหยุ่นในการสร้างงานนำเสนอ
### ฉันสามารถปรับแต่งตำแหน่งและขนาดของกรอบรูปได้หรือไม่?
 แน่นอนคุณสามารถปรับพารามิเตอร์ตำแหน่งและขนาดได้ใน`addPictureFrame` วิธีการที่เหมาะกับความต้องการของคุณ
### Aspose.Slides สำหรับ Java รองรับรูปแบบภาพอื่นนอกเหนือจาก JPEG หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบรูปภาพที่หลากหลาย รวมถึง PNG, GIF, BMP และอื่นๆ
### มีฟอรัมชุมชนหรือช่องทางการสนับสนุนสำหรับผู้ใช้ Aspose.Slides หรือไม่
ใช่ คุณสามารถไปที่ฟอรัม Aspose.Slides สำหรับคำถาม การสนทนา หรือความช่วยเหลือเกี่ยวกับห้องสมุด