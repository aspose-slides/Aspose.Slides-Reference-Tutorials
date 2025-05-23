---
"description": "เรียนรู้วิธีการเพิ่มกรอบรูปภาพที่มีความสูงตามมาตราส่วนสัมพันธ์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เพื่อปรับปรุงเนื้อหาภาพของคุณ"
"linktitle": "เพิ่มกรอบรูปความสูงตามมาตราส่วนสัมพันธ์ใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มกรอบรูปความสูงตามมาตราส่วนสัมพันธ์ใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มกรอบรูปความสูงตามมาตราส่วนสัมพันธ์ใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการเพิ่มกรอบรูปที่มีความสูงตามมาตราส่วนสัมพันธ์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java และเพิ่มลงในโปรเจ็กต์ Java ของคุณแล้ว

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็กเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ขั้นแรก ให้แน่ใจว่าคุณได้ตั้งค่าไดเร็กทอรีสำหรับโครงการของคุณแล้ว และสภาพแวดล้อม Java ของคุณได้รับการกำหนดค่าอย่างถูกต้อง
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
## ขั้นตอนที่ 4: เพิ่มกรอบรูปลงในสไลด์
เพิ่มกรอบรูปให้กับสไลด์ในงานนำเสนอ:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## ขั้นตอนที่ 5: ตั้งค่าความกว้างและความสูงตามมาตราส่วน
ตั้งค่ามาตราส่วนความกว้างและความสูงที่สัมพันธ์กันของกรอบรูป:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## ขั้นตอนที่ 6: บันทึกการนำเสนอ
บันทึกการนำเสนอพร้อมกรอบรูปเพิ่ม:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณสามารถเพิ่มกรอบรูปที่มีขนาดความสูงสัมพันธ์กันในงานนำเสนอ PowerPoint ได้อย่างง่ายดายโดยใช้ Aspose.Slides สำหรับ Java ทดลองใช้ค่าขนาดต่างๆ เพื่อให้ได้รูปลักษณ์ที่ต้องการสำหรับรูปภาพของคุณ

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มกรอบรูปหลาย ๆ กรอบลงในสไลด์เดียวด้วยวิธีนี้ได้หรือไม่?
ใช่ คุณสามารถเพิ่มกรอบรูปหลาย ๆ กรอบลงในสไลด์ได้โดยทำซ้ำขั้นตอนเดียวกันสำหรับภาพแต่ละภาพ
### Aspose.Slides สำหรับ Java สามารถใช้งานร่วมกับ PowerPoint ทุกเวอร์ชันได้หรือไม่
Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint หลายเวอร์ชัน ช่วยให้สร้างงานนำเสนอได้อย่างยืดหยุ่น
### ฉันสามารถปรับแต่งตำแหน่งและขนาดของกรอบรูปได้ไหม?
แน่นอน คุณสามารถปรับตำแหน่งและพารามิเตอร์ขนาดได้ใน `addPictureFrame` วิธีการที่จะเหมาะสมกับความต้องการของคุณ
### Aspose.Slides สำหรับ Java รองรับรูปแบบภาพอื่นนอกเหนือจาก JPEG หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบภาพต่างๆ รวมถึง PNG, GIF, BMP และอื่นๆ อีกมากมาย
### มีฟอรัมชุมชนหรือช่องสนับสนุนสำหรับผู้ใช้ Aspose.Slides หรือไม่
ใช่ คุณสามารถเยี่ยมชมฟอรัม Aspose.Slides หากมีคำถาม การอภิปราย หรือความช่วยเหลือใดๆ เกี่ยวกับห้องสมุด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}