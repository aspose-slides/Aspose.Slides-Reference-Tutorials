---
"description": "เรียนรู้วิธีการเปลี่ยนสถานะ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java และ Aspose.Slides พัฒนาทักษะการนำเสนออัตโนมัติของคุณ"
"linktitle": "เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java"
"url": "/th/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เปลี่ยนสถานะ SmartArt ใน PowerPoint ด้วย Java

## การแนะนำ
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการจัดการวัตถุ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java ด้วยไลบรารี Aspose.Slides SmartArt เป็นฟีเจอร์อันทรงพลังใน PowerPoint ที่ช่วยให้คุณสร้างไดอะแกรมและกราฟิกที่ดึงดูดสายตาได้
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java ไว้ในระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์ออราเคิล](https://www-oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จาก [เว็บไซต์](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
หากต้องการเริ่มทำงานกับ Aspose.Slides ในโปรเจ็กต์ Java ของคุณ โปรดนำเข้าแพ็กเกจที่จำเป็น:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
ตอนนี้เรามาแบ่งโค้ดตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ กัน:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
ที่นี่เราสร้างใหม่ `Presentation` วัตถุซึ่งแสดงถึงการนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่มวัตถุ SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
ขั้นตอนนี้จะเพิ่มวัตถุ SmartArt ลงในสไลด์แรกของการนำเสนอ เราจะระบุตำแหน่งและขนาดของวัตถุ SmartArt รวมถึงประเภทเค้าโครง (ในกรณีนี้คือ `BasicProcess`-
## ขั้นตอนที่ 3: ตั้งค่าสถานะ SmartArt
```java
smart.setReversed(true);
```
ที่นี่ เราตั้งค่าสถานะของวัตถุ SmartArt ในตัวอย่างนี้ เราจะย้อนทิศทางของ SmartArt
## ขั้นตอนที่ 4: ตรวจสอบสถานะ SmartArt
```java
boolean flag = smart.isReversed();
```
เราสามารถตรวจสอบสถานะปัจจุบันของวัตถุ SmartArt ได้เช่นกัน บรรทัดนี้จะดึงข้อมูลว่า SmartArt ถูกย้อนกลับหรือไม่ และจัดเก็บไว้ใน `flag` ตัวแปร.
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
สุดท้ายเราบันทึกการนำเสนอที่ปรับเปลี่ยนแล้วไปยังตำแหน่งที่ระบุบนดิสก์

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการเปลี่ยนสถานะของวัตถุ SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java และไลบรารี Aspose.Slides ด้วยความรู้ดังกล่าว คุณสามารถสร้างงานนำเสนอที่ไดนามิกและน่าสนใจด้วยโปรแกรมได้
## คำถามที่พบบ่อย
### ฉันสามารถปรับเปลี่ยนคุณสมบัติอื่นๆ ของ SmartArt โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ คุณสามารถปรับเปลี่ยนลักษณะต่างๆ ของวัตถุ SmartArt เช่น สี สไตล์ และเค้าโครง โดยใช้ Aspose.Slides
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Slides รองรับการนำเสนอ PowerPoint ในเวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และการบูรณาการที่ราบรื่น
### ฉันสามารถสร้างเค้าโครง SmartArt แบบกำหนดเองด้วย Aspose.Slides ได้หรือไม่
แน่นอน! Aspose.Slides นำเสนอ API เพื่อสร้างเค้าโครง SmartArt ที่กำหนดเองตามความต้องการเฉพาะของคุณ
### Aspose.Slides รองรับรูปแบบไฟล์อื่นนอกเหนือจาก PowerPoint หรือไม่
ใช่ Aspose.Slides รองรับรูปแบบไฟล์ต่างๆ มากมาย รวมถึง PPTX, PPT, PDF และอื่นๆ อีกมากมาย
### มีฟอรัมชุมชนที่ฉันสามารถรับความช่วยเหลือเกี่ยวกับคำถามที่เกี่ยวข้องกับ Aspose.Slides หรือไม่
ใช่ คุณสามารถเยี่ยมชมฟอรั่ม Aspose.Slides ได้ที่ [ที่นี่](https://forum.aspose.com/c/slides/11) เพื่อขอความช่วยเหลือและการหารือ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}