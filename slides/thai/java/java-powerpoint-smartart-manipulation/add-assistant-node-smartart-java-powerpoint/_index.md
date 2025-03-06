---
title: เพิ่มโหนดผู้ช่วยให้กับ SmartArt ใน Java PowerPoint
linktitle: เพิ่มโหนดผู้ช่วยให้กับ SmartArt ใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มโหนดผู้ช่วยให้กับ SmartArt ในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides พัฒนาทักษะการแก้ไข PowerPoint ของคุณ
type: docs
weight: 17
url: /th/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่มโหนดผู้ช่วยให้กับ SmartArt ในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดและติดตั้ง JDK ล่าสุดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จาก[ลิงค์นี้](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
เริ่มต้นด้วยการสร้างอินสแตนซ์การนำเสนอโดยใช้เส้นทางไปยังไฟล์ PowerPoint ของคุณ:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## ขั้นตอนที่ 2: สำรวจผ่านรูปร่าง
สำรวจทุกรูปร่างภายในสไลด์แรกของงานนำเสนอ:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## ขั้นตอนที่ 3: ตรวจสอบรูปร่าง SmartArt
ตรวจสอบว่ารูปร่างเป็นประเภท SmartArt หรือไม่:
```java
if (shape instanceof ISmartArt)
```
## ขั้นตอนที่ 4: สำรวจผ่านโหนด SmartArt
สำรวจผ่านโหนดทั้งหมดของรูปร่าง SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## ขั้นตอนที่ 5: ตรวจสอบโหนดผู้ช่วย
ตรวจสอบว่าโหนดเป็นโหนดผู้ช่วยหรือไม่:
```java
if (node.isAssistant())
```
## ขั้นตอนที่ 6: ตั้งค่าโหนดผู้ช่วยเป็นปกติ
หากโหนดเป็นโหนดผู้ช่วย ให้ตั้งค่าเป็นโหนดปกติ:
```java
node.setAssistant(false);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
บันทึกงานนำเสนอที่แก้ไข:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ยินดีด้วย! คุณได้เพิ่มโหนดผู้ช่วยลงใน SmartArt ในงานนำเสนอ Java PowerPoint ของคุณสำเร็จแล้วโดยใช้ Aspose.Slides

## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มโหนดผู้ช่วยหลายรายการให้กับ SmartArt ในงานนำเสนอได้หรือไม่
ได้ คุณสามารถเพิ่มโหนดผู้ช่วยได้หลายโหนดโดยทำซ้ำขั้นตอนสำหรับแต่ละโหนด
### บทช่วยสอนนี้ใช้ได้กับทั้งเทมเพลต PowerPoint และ PowerPoint หรือไม่
ได้ คุณสามารถใช้บทช่วยสอนนี้กับทั้งงานนำเสนอ PowerPoint และเทมเพลต
### Aspose.Slides เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides รองรับ PowerPoint เวอร์ชันตั้งแต่ 97-2003 เป็นเวอร์ชันล่าสุด
### ฉันสามารถปรับแต่งรูปลักษณ์ของโหนดผู้ช่วยได้หรือไม่
ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏได้โดยใช้คุณสมบัติและวิธีการต่างๆ ที่ได้รับจาก Aspose.Slides
### มีการจำกัดจำนวนโหนดใน SmartArt หรือไม่?
SmartArt ใน PowerPoint รองรับโหนดจำนวนมาก แต่ขอแนะนำให้รักษาให้เหมาะสมเพื่อให้สามารถอ่านได้ดีขึ้น