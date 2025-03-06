---
title: เพิ่มโหนดลูกแบบกำหนดเองใน SmartArt โดยใช้ Java
linktitle: เพิ่มโหนดลูกแบบกำหนดเองใน SmartArt โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มโหนดลูกแบบกำหนดเองลงใน SmartArt ในงานนำเสนอ PowerPoint โดยใช้ Java กับ Aspose.Slides ปรับปรุงสไลด์ของคุณด้วยกราฟิกระดับมืออาชีพได้อย่างง่ายดาย
weight: 11
url: /th/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
SmartArt เป็นฟีเจอร์ที่มีประสิทธิภาพใน PowerPoint ที่ช่วยให้ผู้ใช้สามารถสร้างกราฟิกที่ดูเป็นมืออาชีพได้อย่างรวดเร็วและง่ายดาย ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีเพิ่มโหนดลูกแบบกำหนดเองให้กับ SmartArt โดยใช้ Java กับ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณ
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
โหลดงานนำเสนอ PowerPoint ที่คุณต้องการเพิ่มโหนดลูกแบบกำหนดเองลงใน SmartArt:
```java
String dataDir = "Your Document Directory";
// โหลดการนำเสนอที่ต้องการ
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## ขั้นตอนที่ 2: เพิ่ม SmartArt ลงในสไลด์
ตอนนี้ มาเพิ่ม SmartArt ลงในสไลด์กันดีกว่า:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## ขั้นตอนที่ 3: ย้ายรูปร่าง SmartArt
ย้ายรูปร่าง SmartArt ไปยังตำแหน่งใหม่:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## ขั้นตอนที่ 4: เปลี่ยนความกว้างของรูปร่าง
เปลี่ยนความกว้างของรูปร่าง SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## ขั้นตอนที่ 5: เปลี่ยนความสูงของรูปร่าง
เปลี่ยนความสูงของรูปร่าง SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## ขั้นตอนที่ 6: หมุนรูปร่าง
หมุนรูปร่าง SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## ขั้นตอนที่ 7: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้ว:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มโหนดลูกแบบกำหนดเองให้กับ SmartArt โดยใช้ Java กับ Aspose.Slides เมื่อทำตามขั้นตอนเหล่านี้ คุณจะปรับปรุงการนำเสนอของคุณด้วยกราฟิกที่ปรับแต่งเองได้ ทำให้น่าสนใจและเป็นมืออาชีพมากขึ้น
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มเค้าโครง SmartArt ประเภทต่างๆ โดยใช้ Aspose.Slides สำหรับ Java ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java รองรับเค้าโครง SmartArt ที่หลากหลาย ช่วยให้คุณสามารถเลือกเค้าโครงที่เหมาะกับความต้องการในการนำเสนอของคุณได้มากที่สุด
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides สำหรับ Java ได้รับการออกแบบมาให้ทำงานได้อย่างราบรื่นกับ PowerPoint เวอร์ชันต่างๆ ทำให้มั่นใจได้ถึงความเข้ากันได้และความสม่ำเสมอในทุกแพลตฟอร์ม
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่าง SmartArt โดยทางโปรแกรมได้หรือไม่
อย่างแน่นอน! ด้วย Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งรูปลักษณ์ ขนาด สี และเลย์เอาต์ของรูปร่าง SmartArt โดยทางโปรแกรมเพื่อให้เหมาะกับความต้องการในการออกแบบของคุณ
### Aspose.Slides สำหรับ Java มีเอกสารประกอบและการสนับสนุนหรือไม่
ใช่ คุณสามารถค้นหาเอกสารที่ครอบคลุมและเข้าถึงฟอรัมสนับสนุนชุมชนได้จากเว็บไซต์ Aspose
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java เวอร์ชันทดลองใช้ฟรีได้จากเว็บไซต์เพื่อสำรวจคุณลักษณะและความสามารถของเวอร์ชันก่อนตัดสินใจซื้อ[ที่นี่](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
