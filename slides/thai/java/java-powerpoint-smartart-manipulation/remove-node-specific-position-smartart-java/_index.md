---
title: ลบโหนดในตำแหน่งเฉพาะใน SmartArt
linktitle: ลบโหนดในตำแหน่งเฉพาะใน SmartArt
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีลบโหนดที่ตำแหน่งเฉพาะภายใน SmartArt โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการปรับแต่งการนำเสนอได้อย่างง่ายดาย
weight: 15
url: /th/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในขอบเขตของการพัฒนา Java Aspose.Slides กลายเป็นเครื่องมืออันทรงพลังสำหรับจัดการการนำเสนอโดยทางโปรแกรม ไม่ว่าจะเป็นการสร้าง การแก้ไข หรือการจัดการสไลด์ Aspose.Slides สำหรับ Java มอบชุดคุณสมบัติที่แข็งแกร่งเพื่อปรับปรุงงานเหล่านี้อย่างมีประสิทธิภาพ การดำเนินการทั่วไปประการหนึ่งคือการลบโหนดที่ตำแหน่งเฉพาะภายในวัตถุ SmartArt บทช่วยสอนนี้จะเจาะลึกกระบวนการทีละขั้นตอนในการทำให้สิ่งนี้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides สำหรับ Java: รับไลบรารี Aspose.Slides สำหรับ Java คุณสามารถดาวน์โหลดได้จาก[ลิงค์นี้](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): ติดตั้ง IDE เช่น IntelliJ IDEA หรือ Eclipse เพื่อเขียนและรันโค้ด Java ได้อย่างราบรื่น

## แพ็คเกจนำเข้า
ในโปรเจ็กต์ Java ของคุณ ให้รวมแพ็คเกจที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Slides:
```java
import com.aspose.slides.*;
```
## ขั้นตอนที่ 1: โหลดงานนำเสนอ
เริ่มต้นด้วยการโหลดไฟล์งานนำเสนอที่มีวัตถุ SmartArt อยู่:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## ขั้นตอนที่ 2: สำรวจรูปร่าง SmartArt
สำรวจแต่ละรูปร่างในงานนำเสนอเพื่อระบุวัตถุ SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## ขั้นตอนที่ 3: เข้าถึงโหนด SmartArt
เข้าถึงโหนด SmartArt ในตำแหน่งที่ต้องการ:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## ขั้นตอนที่ 4: ลบโหนดลูก
ลบโหนดลูกในตำแหน่งที่ระบุ:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้ว:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## บทสรุป
ด้วย Aspose.Slides สำหรับ Java การจัดการวัตถุ SmartArt ภายในงานนำเสนอจะกลายเป็นงานที่ตรงไปตรงมา ด้วยการทำตามขั้นตอนที่ระบุไว้ คุณสามารถลบโหนดในตำแหน่งที่ต้องการได้อย่างราบรื่น ช่วยเพิ่มความสามารถในการปรับแต่งการนำเสนอของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java ใช้งานได้ฟรีหรือไม่
 Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ แต่คุณสามารถสำรวจฟังก์ชันต่างๆ ของมันได้ด้วยการทดลองใช้ฟรี เยี่ยม[ลิงค์นี้](https://releases.aspose.com/) ที่จะเริ่มต้น.
### ฉันจะรับการสนับสนุนสำหรับคำค้นหาที่เกี่ยวข้องกับ Aspose.Slides ได้ที่ไหน
 หากต้องการความช่วยเหลือหรือข้อสงสัย คุณสามารถไปที่ฟอรัม Aspose.Slides[ที่นี่](https://forum.aspose.com/c/slides/11).
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/) เพื่อวัตถุประสงค์ในการประเมินผล
### ฉันจะซื้อ Aspose.Slides สำหรับ Java ได้อย่างไร
 หากต้องการซื้อ Aspose.Slides สำหรับ Java โปรดไปที่หน้าการซื้อ[ที่นี่](https://purchase.aspose.com/buy).
### ฉันจะหาเอกสารประกอบโดยละเอียดสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถเข้าถึงเอกสารที่ครอบคลุม[ที่นี่](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
