---
title: เปลี่ยนเค้าโครง SmartArt ใน PowerPoint ด้วย Java
linktitle: เปลี่ยนเค้าโครง SmartArt ใน PowerPoint ด้วย Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการเค้าโครง SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java กับ Aspose.Slides สำหรับ Java
weight: 19
url: /th/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในบทช่วยสอนนี้ เราจะสำรวจวิธีจัดการเค้าโครง SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java SmartArt เป็นฟีเจอร์ที่มีประสิทธิภาพใน PowerPoint ที่ช่วยให้ผู้ใช้สามารถสร้างกราฟิกที่ดึงดูดสายตาเพื่อวัตถุประสงค์ต่างๆ เช่น การแสดงกระบวนการ ลำดับชั้น ความสัมพันธ์ และอื่นๆ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  ไลบรารี Aspose.Slides: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/slides/java/).
3. ความเข้าใจพื้นฐานของ Java: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม Java จะเป็นประโยชน์
4. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เลือก IDE ตามที่คุณต้องการ เช่น Eclipse หรือ IntelliJ IDEA

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อมโปรเจ็กต์ Java ของคุณ
ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ Java ของคุณได้รับการตั้งค่าอย่างถูกต้องใน IDE ที่คุณเลือก สร้างโปรเจ็กต์ Java ใหม่และรวมไลบรารี Aspose.Slides ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่
สร้างอินสแตนซ์วัตถุการนำเสนอใหม่เพื่อสร้างงานนำเสนอ PowerPoint ใหม่
```java
Presentation presentation = new Presentation();
```
## ขั้นตอนที่ 3: เพิ่มกราฟิก SmartArt
เพิ่มกราฟิก SmartArt ลงในงานนำเสนอของคุณ ระบุตำแหน่งและขนาดของกราฟิก SmartArt บนสไลด์
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## ขั้นตอนที่ 4: เปลี่ยนเค้าโครง SmartArt
เปลี่ยนเค้าโครงของกราฟิก SmartArt ให้เป็นประเภทเค้าโครงที่คุณต้องการ
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
บันทึกการนำเสนอที่แก้ไขไปยังไดเร็กทอรีที่ระบุบนระบบของคุณ
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
การจัดการเค้าโครง SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java เป็นกระบวนการที่ไม่ซับซ้อนด้วย Aspose.Slides สำหรับ Java เมื่อทำตามบทช่วยสอนนี้ คุณสามารถปรับเปลี่ยนกราฟิก SmartArt ให้เหมาะกับความต้องการในการนำเสนอของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของกราฟิก SmartArt โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถกำหนดลักษณะต่างๆ ของกราฟิก SmartArt ได้ เช่น สี สไตล์ และเอฟเฟ็กต์
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides รองรับการนำเสนอ PowerPoint ที่สร้างขึ้นใน PowerPoint เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความเข้ากันได้บนแพลตฟอร์มต่างๆ
### Aspose.Slides รองรับภาษาการเขียนโปรแกรมอื่นๆ หรือไม่
ใช่ Aspose.Slides พร้อมใช้งานสำหรับภาษาการเขียนโปรแกรมหลายภาษา รวมถึง .NET, Python และ JavaScript
### ฉันสามารถสร้างกราฟิก SmartArt ตั้งแต่เริ่มต้นโดยใช้ Aspose.Slides ได้หรือไม่
แน่นอน คุณสามารถสร้างกราฟิก SmartArt โดยทางโปรแกรมหรือปรับเปลี่ยนกราฟิกที่มีอยู่ให้ตรงตามความต้องการของคุณได้
### มีฟอรัมชุมชนที่ฉันสามารถขอความช่วยเหลือเกี่ยวกับ Aspose.Slides ได้หรือไม่
 ใช่ คุณสามารถเยี่ยมชมฟอรัม Aspose.Slides ได้[ที่นี่](https://forum.aspose.com/c/slides/11) เพื่อถามคำถามและมีส่วนร่วมกับชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
