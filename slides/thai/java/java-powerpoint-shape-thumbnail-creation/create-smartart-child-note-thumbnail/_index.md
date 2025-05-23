---
"description": "เรียนรู้วิธีการสร้างภาพขนาดย่อของบันทึกย่อย่อย SmartArt ใน Java ด้วย Aspose.Slides เพื่อเพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณได้อย่างง่ายดาย"
"linktitle": "สร้างภาพย่อของบันทึกย่อเด็ก SmartArt"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างภาพย่อของบันทึกย่อเด็ก SmartArt"
"url": "/th/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพย่อของบันทึกย่อเด็ก SmartArt

## การแนะนำ
ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีสร้างภาพย่อของโน้ตย่อย SmartArt ใน Java โดยใช้ Aspose.Slides Aspose.Slides คือ Java API ที่ทรงพลังที่ช่วยให้ผู้พัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ได้ด้วยโปรแกรม ทำให้สามารถสร้าง แก้ไข และจัดการสไลด์ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าแพ็คเกจที่จำเป็นลงในคลาส Java ของคุณ:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าและกำหนดค่าโครงการ Java ด้วยไลบรารี Aspose.Slides แล้ว
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
สร้างตัวอย่าง `Presentation` คลาสเพื่อแสดงไฟล์ PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่ม SmartArt
เพิ่ม SmartArt ลงในสไลด์การนำเสนอของคุณ:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## ขั้นตอนที่ 4: รับการอ้างอิงโหนด
รับการอ้างอิงของโหนดโดยใช้ดัชนี:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## ขั้นตอนที่ 5: รับภาพขนาดย่อ
ดึงภาพขนาดย่อของโหนด SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## ขั้นตอนที่ 6: บันทึกภาพขนาดย่อ
บันทึกภาพย่อลงในไฟล์:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับโหนด SmartArt แต่ละโหนดตามต้องการในงานนำเสนอของคุณ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างภาพย่อของโน้ตย่อย SmartArt ใน Java โดยใช้ Aspose.Slides ด้วยความรู้ดังกล่าว คุณสามารถปรับปรุงการนำเสนอ PowerPoint ของคุณผ่านโปรแกรมได้ โดยเพิ่มองค์ประกอบที่ดึงดูดสายตาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides เพื่อจัดการไฟล์ PowerPoint ที่มีอยู่ได้หรือไม่
ใช่ Aspose.Slides ช่วยให้คุณปรับเปลี่ยนไฟล์ PowerPoint ที่มีอยู่ได้ รวมถึงการเพิ่ม การลบ หรือการแก้ไขสไลด์และเนื้อหาต่างๆ
### Aspose.Slides รองรับการส่งออกสไลด์ไปยังรูปแบบไฟล์อื่นหรือไม่
แน่นอน! Aspose.Slides รองรับการส่งออกสไลด์เป็นรูปแบบต่างๆ รวมถึง PDF รูปภาพ และ HTML เป็นต้น
### Aspose.Slides เหมาะกับการทำงานอัตโนมัติของ PowerPoint ระดับองค์กรหรือไม่
ใช่ Aspose.Slides ได้รับการออกแบบมาเพื่อจัดการกับงานอัตโนมัติของ PowerPoint ระดับองค์กรอย่างมีประสิทธิภาพและเชื่อถือได้
### ฉันสามารถสร้างไดอะแกรม SmartArt ที่ซับซ้อนโดยใช้โปรแกรม Aspose.Slides ได้หรือไม่
แน่นอน! Aspose.Slides ให้การสนับสนุนที่ครอบคลุมสำหรับการสร้างและจัดการไดอะแกรม SmartArt ที่มีความซับซ้อนหลากหลาย
### Aspose.Slides ให้การสนับสนุนทางเทคนิคแก่นักพัฒนาหรือไม่
ใช่ Aspose.Slides ให้การสนับสนุนทางเทคนิคเฉพาะสำหรับนักพัฒนาผ่านทาง [ฟอรั่ม](https://forum.aspose.com/c/slides/11) และช่องทางอื่นๆ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}