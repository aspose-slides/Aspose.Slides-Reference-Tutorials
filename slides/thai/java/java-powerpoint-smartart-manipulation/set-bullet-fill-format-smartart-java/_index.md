---
title: ตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java
linktitle: ตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides คำแนะนำทีละขั้นตอนเพื่อการจัดการการนำเสนอที่มีประสิทธิภาพ
weight: 18
url: /th/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
ในขอบเขตของการเขียนโปรแกรม Java การจัดการงานนำเสนออย่างมีประสิทธิภาพเป็นข้อกำหนดทั่วไป โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับองค์ประกอบ SmartArt Aspose.Slides สำหรับ Java กลายเป็นเครื่องมืออันทรงพลังสำหรับงานดังกล่าว โดยมีฟังก์ชันการทำงานมากมายในการจัดการการนำเสนอโดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### ชุดพัฒนาจาวา (JDK)
 คุณต้องติดตั้ง JDK บนระบบของคุณ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) และปฏิบัติตามคำแนะนำในการติดตั้ง
### Aspose.Slides สำหรับ Java
 ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/)- ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้ในเอกสารประกอบสำหรับระบบปฏิบัติการเฉพาะของคุณ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นไปยังโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#มาแจกแจงตัวอย่างที่ให้ไว้เป็นหลายขั้นตอนเพื่อความเข้าใจที่ชัดเจนเกี่ยวกับวิธีตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
ขั้นแรก สร้างอินสแตนซ์ใหม่ของคลาสการนำเสนอ ซึ่งแสดงถึงงานนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่ม SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
ถัดไป เพิ่มรูปร่าง SmartArt ลงในสไลด์ บรรทัดโค้ดนี้จะเริ่มต้นรูปร่าง SmartArt ใหม่ด้วยขนาดและเค้าโครงที่ระบุ
## ขั้นตอนที่ 3: เข้าถึงโหนด SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
ตอนนี้ เข้าถึงโหนดแรก (หรือโหนดที่ต้องการ) ภายในรูปร่าง SmartArt เพื่อแก้ไขคุณสมบัติ
## ขั้นตอนที่ 4: ตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อย
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
ที่นี่ เราจะตรวจสอบว่ารองรับรูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยหรือไม่ หากเป็นเช่นนั้น เราจะโหลดไฟล์รูปภาพและตั้งค่าเป็นสัญลักษณ์แสดงหัวข้อย่อยสำหรับโหนด SmartArt
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุ

## บทสรุป
ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่ารูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides เรียบร้อยแล้ว ความสามารถนี้เปิดโลกแห่งความเป็นไปได้สำหรับการนำเสนอแบบไดนามิกและดึงดูดสายตาในแอปพลิเคชัน Java
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างงานนำเสนอตั้งแต่เริ่มต้นได้หรือไม่
อย่างแน่นอน! Aspose.Slides มี API ที่ครอบคลุมสำหรับการสร้าง แก้ไข และจัดการงานนำเสนอทั้งหมดผ่านโค้ด
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
ใช่ Aspose.Slides รับประกันความเข้ากันได้กับ Microsoft PowerPoint เวอร์ชันต่างๆ ช่วยให้สามารถผสานรวมเข้ากับขั้นตอนการทำงานของคุณได้อย่างราบรื่น
### ฉันสามารถปรับแต่งองค์ประกอบ SmartArt นอกเหนือจากรูปแบบการเติมสัญลักษณ์แสดงหัวข้อย่อยได้หรือไม่
แท้จริงแล้ว Aspose.Slides ช่วยให้คุณสามารถปรับแต่งทุกแง่มุมของรูปร่าง SmartArt รวมถึงเค้าโครง สไตล์ เนื้อหา และอื่นๆ อีกมากมาย
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถสำรวจคุณสมบัติของ Aspose.Slides ได้ด้วยการทดลองใช้ฟรี เพียงดาวน์โหลดจาก[เว็บไซต์](https://releases.aspose.com/slides/java/) และเริ่มสำรวจ
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 หากมีข้อสงสัยหรือความช่วยเหลือ คุณสามารถไปที่ฟอรัม Aspose.Slides ได้ที่[ลิงค์นี้](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
