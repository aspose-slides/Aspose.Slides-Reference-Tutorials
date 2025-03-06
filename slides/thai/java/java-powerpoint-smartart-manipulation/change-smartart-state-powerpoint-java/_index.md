---
title: เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java
linktitle: เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเปลี่ยนสถานะ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java และ Aspose.Slides พัฒนาทักษะการนำเสนออัตโนมัติของคุณ
weight: 21
url: /th/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีจัดการวัตถุ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java กับไลบรารี Aspose.Slides SmartArt เป็นฟีเจอร์ที่มีประสิทธิภาพใน PowerPoint ที่ช่วยให้คุณสามารถสร้างไดอะแกรมและกราฟิกที่ดึงดูดสายตาได้
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ออราเคิล](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จากไฟล์[เว็บไซต์](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
หากต้องการเริ่มทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าแพ็คเกจที่จำเป็น:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
ตอนนี้เรามาแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
 ที่นี่เราสร้างใหม่`Presentation` วัตถุซึ่งแสดงถึงการนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่มวัตถุ SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 ขั้นตอนนี้จะเพิ่มวัตถุ SmartArt ลงในสไลด์แรกของงานนำเสนอ เราระบุตำแหน่งและขนาดของวัตถุ SmartArt รวมถึงประเภทเค้าโครง (ในกรณีนี้`BasicProcess`-
## ขั้นตอนที่ 3: ตั้งค่าสถานะ SmartArt
```java
smart.setReversed(true);
```
ที่นี่ เราตั้งค่าสถานะของวัตถุ SmartArt ในตัวอย่างนี้ เรากำลังกลับทิศทางของ SmartArt
## ขั้นตอนที่ 4: ตรวจสอบสถานะ SmartArt
```java
boolean flag = smart.isReversed();
```
 นอกจากนี้เรายังสามารถตรวจสอบสถานะปัจจุบันของวัตถุ SmartArt ได้อีกด้วย บรรทัดนี้จะดึงข้อมูลว่า SmartArt จะกลับรายการหรือไม่ และจัดเก็บไว้ใน`flag` ตัวแปร.
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
สุดท้าย เราจะบันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุบนดิสก์

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเปลี่ยนสถานะของวัตถุ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java และไลบรารี Aspose.Slides ด้วยความรู้นี้ คุณสามารถสร้างงานนำเสนอแบบไดนามิกและน่าดึงดูดโดยทางโปรแกรม
## คำถามที่พบบ่อย
### ฉันสามารถแก้ไขคุณสมบัติอื่นๆ ของ SmartArt โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถปรับเปลี่ยนแง่มุมต่างๆ ของวัตถุ SmartArt ได้ เช่น สี สไตล์ และเค้าโครง โดยใช้ Aspose.Slides
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Slides รองรับการนำเสนอ PowerPoint ในเวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความเข้ากันได้และการผสานรวมที่ราบรื่น
### ฉันสามารถสร้างเค้าโครง SmartArt แบบกำหนดเองด้วย Aspose.Slides ได้หรือไม่
อย่างแน่นอน! Aspose.Slides มี API เพื่อสร้างเค้าโครง SmartArt แบบกำหนดเองที่ปรับให้เหมาะกับความต้องการเฉพาะของคุณ
### Aspose.Slides รองรับไฟล์รูปแบบอื่นนอกเหนือจาก PowerPoint หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบไฟล์ที่หลากหลาย รวมถึง PPTX, PPT, PDF และอื่นๆ
### มีฟอรัมชุมชนที่ฉันสามารถขอความช่วยเหลือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Slides ได้หรือไม่
 ใช่ คุณสามารถเยี่ยมชมฟอรั่ม Aspose.Slides ได้ที่[ที่นี่](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือและหารือ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
