---
title: สร้างรูปขนาดย่อของบันทึกย่อเด็ก SmartArt
linktitle: สร้างรูปขนาดย่อของบันทึกย่อเด็ก SmartArt
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างภาพขนาดย่อบันทึกย่อของเด็ก SmartArt ใน Java ด้วย Aspose.Slides ซึ่งจะช่วยเพิ่มประสิทธิภาพการนำเสนอ PowerPoint ของคุณได้อย่างง่ายดาย
type: docs
weight: 15
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างภาพขนาดย่อบันทึกย่อย SmartArt ใน Java โดยใช้ Aspose.Slides Aspose.Slides เป็น Java API อันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ทำให้สามารถสร้าง ปรับเปลี่ยน และจัดการสไลด์ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่าในโปรเจ็กต์ของคุณ คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าได้นำเข้าแพ็คเกจที่จำเป็นในคลาส Java ของคุณ:
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
ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java และกำหนดค่าด้วยไลบรารี Aspose.Slides
## ขั้นตอนที่ 2: สร้างงานนำเสนอ
 ยกตัวอย่าง`Presentation` คลาสเพื่อแสดงไฟล์ PPTX:
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
บันทึกภาพขนาดย่อลงในไฟล์:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
ทำซ้ำขั้นตอนเหล่านี้สำหรับโหนด SmartArt แต่ละโหนดตามความจำเป็นในงานนำเสนอของคุณ

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างภาพขนาดย่อบันทึกย่อย SmartArt ใน Java โดยใช้ Aspose.Slides ด้วยความรู้นี้ คุณสามารถปรับปรุงงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรม โดยเพิ่มองค์ประกอบที่ดึงดูดสายตาได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides เพื่อจัดการไฟล์ PowerPoint ที่มีอยู่ได้หรือไม่
ใช่ Aspose.Slides ช่วยให้คุณสามารถแก้ไขไฟล์ PowerPoint ที่มีอยู่ รวมถึงการเพิ่ม ลบ หรือแก้ไขสไลด์และเนื้อหา
### Aspose.Slides รองรับการส่งออกสไลด์ไปยังรูปแบบไฟล์ต่างๆ หรือไม่
อย่างแน่นอน! Aspose.Slides รองรับการส่งออกสไลด์เป็นรูปแบบต่างๆ รวมถึง PDF รูปภาพ และ HTML และอื่นๆ อีกมากมาย
### Aspose.Slides เหมาะสำหรับระบบอัตโนมัติ PowerPoint ระดับองค์กรหรือไม่
ใช่ Aspose.Slides ได้รับการออกแบบมาเพื่อจัดการงาน PowerPoint อัตโนมัติระดับองค์กรอย่างมีประสิทธิภาพและเชื่อถือได้
### ฉันสามารถสร้างไดอะแกรม SmartArt ที่ซับซ้อนโดยทางโปรแกรมด้วย Aspose.Slides ได้หรือไม่
แน่นอน! Aspose.Slides ให้การสนับสนุนที่ครอบคลุมสำหรับการสร้างและจัดการไดอะแกรม SmartArt ที่มีความซับซ้อนแตกต่างกัน
### Aspose.Slides ให้การสนับสนุนทางเทคนิคสำหรับนักพัฒนาหรือไม่
 ใช่ Aspose.Slides ให้การสนับสนุนทางเทคนิคโดยเฉพาะสำหรับนักพัฒนาผ่านทางพวกเขา[ฟอรั่ม](https://forum.aspose.com/c/slides/11) และช่องทางอื่นๆ