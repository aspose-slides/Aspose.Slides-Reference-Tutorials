---
title: สร้างรูปขนาดย่อของรูปร่างใน PowerPoint
linktitle: สร้างรูปขนาดย่อของรูปร่างใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างรูปขนาดย่อของรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java มีคำแนะนำทีละขั้นตอน
weight: 14
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการสร้างรูปขนาดย่อของรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม ช่วยให้งานต่างๆ ทำงานอัตโนมัติ รวมถึงการสร้างรูปขนาดย่อของรูปร่าง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่าในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณเพื่อใช้ฟังก์ชันการทำงานของ Aspose.Slides รวมคำสั่งการนำเข้าต่อไปนี้ไว้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: กำหนดไดเร็กทอรีเอกสาร
```java
String dataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PowerPoint ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 สร้างอินสแตนซ์ใหม่ของ`Presentation` คลาสโดยส่งเส้นทางไปยังไฟล์ PowerPoint ของคุณเป็นพารามิเตอร์
## ขั้นตอนที่ 3: สร้างรูปขนาดย่อของรูปร่าง
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
ดึงภาพขนาดย่อของรูปร่างที่ต้องการจากสไลด์แรกของงานนำเสนอ
## ขั้นตอนที่ 4: บันทึกภาพขนาดย่อ
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
บันทึกภาพขนาดย่อที่สร้างขึ้นลงในดิสก์ในรูปแบบ PNG ด้วยชื่อไฟล์ที่ระบุ

## บทสรุป
โดยสรุป บทช่วยสอนนี้สาธิตวิธีการสร้างรูปขนาดย่อของรูปร่างในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ข้อมูลโค้ดที่ให้มา คุณสามารถสร้างภาพขนาดย่อของรูปร่างโดยทางโปรแกรมได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ฉันสามารถสร้างรูปขนาดย่อสำหรับรูปร่างบนสไลด์ใดๆ ในงานนำเสนอได้หรือไม่
ได้ คุณสามารถแก้ไขโค้ดเพื่อกำหนดเป้าหมายรูปร่างบนสไลด์ใดก็ได้โดยการปรับดัชนีสไลด์ให้สอดคล้องกัน
### Aspose.Slides รองรับรูปแบบรูปภาพอื่นสำหรับการบันทึกภาพขนาดย่อหรือไม่
ใช่ นอกจาก PNG แล้ว Aspose.Slides ยังรองรับการบันทึกภาพย่อในรูปแบบรูปภาพต่างๆ เช่น JPEG, GIF และ BMP
### Aspose.Slides เหมาะสำหรับใช้ในเชิงพาณิชย์หรือไม่
 ใช่ Aspose.Slides เสนอใบอนุญาตเชิงพาณิชย์สำหรับธุรกิจและองค์กร คุณสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### ฉันสามารถลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่
 อย่างแน่นอน! คุณสามารถดาวน์โหลด Aspose.Slides เวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติและความสามารถของมัน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 หากคุณมีคำถามหรือต้องการความช่วยเหลือเกี่ยวกับ Aspose.Slides คุณสามารถไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุน
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
