---
title: เปลี่ยนข้อความบนโหนด SmartArt โดยใช้ Java
linktitle: เปลี่ยนข้อความบนโหนด SmartArt โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ค้นพบวิธีอัปเดตข้อความโหนด SmartArt ใน PowerPoint โดยใช้ Java กับ Aspose.Slides ซึ่งปรับปรุงการปรับแต่งงานนำเสนอให้ดียิ่งขึ้น
type: docs
weight: 22
url: /th/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---
## การแนะนำ
SmartArt ใน PowerPoint เป็นฟีเจอร์ที่มีประสิทธิภาพสำหรับการสร้างไดอะแกรมที่ดึงดูดสายตา Aspose.Slides สำหรับ Java ให้การสนับสนุนที่ครอบคลุมในการจัดการองค์ประกอบ SmartArt โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเปลี่ยนข้อความบนโหนด SmartArt โดยใช้ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและอ้างอิงในโปรเจ็กต์ Java ของคุณ
- ความเข้าใจพื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides ภายในโค้ด Java ของคุณ
```java
import com.aspose.slides.*;
```
มาแบ่งตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: เริ่มต้นวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
 สร้างอินสแตนซ์ใหม่ของ`Presentation` ชั้นเรียนเพื่อทำงานกับงานนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่ม SmartArt ลงในสไลด์
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 เพิ่ม SmartArt ลงในสไลด์แรก ในตัวอย่างนี้ เรากำลังใช้`BasicCycle` เค้าโครง
## ขั้นตอนที่ 3: เข้าถึงโหนด SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
รับการอ้างอิงไปยังโหนดรูทที่สองของ SmartArt
## ขั้นตอนที่ 4: ตั้งค่าข้อความบนโหนด
```java
node.getTextFrame().setText("Second root node");
```
ตั้งค่าข้อความสำหรับโหนด SmartArt ที่เลือก
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุ

## บทสรุป
ในบทช่วยสอนนี้ เราได้สาธิตวิธีการเปลี่ยนข้อความบนโหนด SmartArt โดยใช้ Java และ Aspose.Slides ด้วยความรู้นี้ คุณสามารถจัดการองค์ประกอบ SmartArt ในงานนำเสนอ PowerPoint ของคุณได้แบบไดนามิก เพิ่มความดึงดูดใจและความชัดเจนขององค์ประกอบเหล่านั้น
## คำถามที่พบบ่อย
### ฉันสามารถเปลี่ยนเค้าโครงของ SmartArt หลังจากเพิ่มลงในสไลด์ได้หรือไม่
 ใช่ คุณสามารถเปลี่ยนเค้าโครงได้โดยเข้าไปที่`SmartArt.setAllNodes(LayoutType)` วิธี.
### Aspose.Slides เข้ากันได้กับ Java 11 หรือไม่
ใช่ Aspose.Slides สำหรับ Java เข้ากันได้กับ Java 11 และเวอร์ชันที่ใหม่กว่า
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของโหนด SmartArt โดยทางโปรแกรมได้หรือไม่
แน่นอนว่าคุณสามารถแก้ไขคุณสมบัติต่างๆ เช่น สี ขนาด และรูปร่างได้โดยใช้ Aspose.Slides API
### Aspose.Slides รองรับเค้าโครง SmartArt ประเภทอื่นหรือไม่
ใช่ Aspose.Slides รองรับเค้าโครง SmartArt ที่หลากหลาย ช่วยให้คุณสามารถเลือกเค้าโครงที่เหมาะกับความต้องการในการนำเสนอของคุณได้ดีที่สุด
### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) สำหรับการอ้างอิง API โดยละเอียดและบทช่วยสอน นอกจากนี้คุณยังสามารถขอความช่วยเหลือจาก[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) หรือพิจารณาซื้อก[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) สำหรับการสนับสนุนอย่างมืออาชีพ