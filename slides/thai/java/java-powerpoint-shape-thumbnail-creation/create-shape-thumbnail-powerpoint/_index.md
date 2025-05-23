---
"description": "เรียนรู้วิธีสร้างภาพขนาดย่อในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java มีคำแนะนำทีละขั้นตอนให้"
"linktitle": "สร้างรูปขนาดย่อของรูปทรงใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างรูปขนาดย่อของรูปทรงใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างรูปขนาดย่อของรูปทรงใน PowerPoint

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกการสร้างภาพขนาดย่อของรูปทรงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนาสามารถทำงานกับไฟล์ PowerPoint ได้ด้วยโปรแกรม ทำให้สามารถทำงานอัตโนมัติได้หลายอย่าง รวมถึงการสร้างภาพขนาดย่อของรูปทรง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ของคุณได้แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ขั้นแรก คุณต้องนำเข้าแพ็กเกจที่จำเป็นในโค้ด Java เพื่อใช้ฟังก์ชันการทำงานของ Aspose.Slides ใส่คำสั่งนำเข้าต่อไปนี้ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีเอกสาร
```java
String dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` โดยมีเส้นทางไปยังไดเร็กทอรีที่มีไฟล์ PowerPoint ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
สร้างอินสแตนซ์ใหม่ของ `Presentation` คลาสนี้ส่งผ่านเส้นทางไปยังไฟล์ PowerPoint ของคุณเป็นพารามิเตอร์
## ขั้นตอนที่ 3: สร้างรูปขนาดย่อของรูปร่าง
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
ดึงภาพขนาดย่อของรูปร่างที่ต้องการจากสไลด์แรกของการนำเสนอ
## ขั้นตอนที่ 4: บันทึกภาพขนาดย่อ
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
บันทึกภาพขนาดย่อที่สร้างขึ้นไปยังดิสก์ในรูปแบบ PNG โดยใช้ชื่อไฟล์ที่ระบุ

## บทสรุป
โดยสรุป บทช่วยสอนนี้สาธิตวิธีการสร้างภาพขนาดย่อของรูปทรงในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java โดยปฏิบัติตามคำแนะนำทีละขั้นตอนและใช้ตัวอย่างโค้ดที่ให้มา คุณก็สามารถสร้างภาพขนาดย่อของรูปทรงในโปรแกรมได้อย่างมีประสิทธิภาพ

## คำถามที่พบบ่อย
### ฉันสามารถสร้างภาพขนาดย่อสำหรับรูปร่างบนสไลด์ใดๆ ในงานนำเสนอได้หรือไม่
ใช่ คุณสามารถปรับเปลี่ยนโค้ดเพื่อกำหนดเป้าหมายรูปร่างบนสไลด์ใดๆ ได้โดยปรับดัชนีสไลด์ให้เหมาะสม
### Aspose.Slides รองรับรูปแบบภาพอื่นสำหรับการบันทึกภาพขนาดย่อหรือไม่
ใช่ นอกจาก PNG แล้ว Aspose.Slides ยังรองรับการบันทึกภาพขนาดย่อในรูปแบบภาพต่างๆ เช่น JPEG, GIF และ BMP อีกด้วย
### Aspose.Slides เหมาะสำหรับการใช้งานในเชิงพาณิชย์หรือไม่?
ใช่ Aspose.Slides นำเสนอใบอนุญาตเชิงพาณิชย์สำหรับธุรกิจและองค์กร คุณสามารถซื้อใบอนุญาตได้จาก [ที่นี่](https://purchase-aspose.com/buy).
### ฉันสามารถทดลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่?
แน่นอน! คุณสามารถดาวน์โหลด Aspose.Slides เวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases.aspose.com/) เพื่อประเมินคุณสมบัติและความสามารถของมัน
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
หากคุณมีคำถามหรือต้องการความช่วยเหลือเกี่ยวกับ Aspose.Slides คุณสามารถไปที่ [ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อรองรับ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}