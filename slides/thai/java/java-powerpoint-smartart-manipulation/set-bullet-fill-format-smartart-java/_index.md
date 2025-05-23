---
"description": "เรียนรู้วิธีตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides คำแนะนำทีละขั้นตอนสำหรับการจัดการงานนำเสนออย่างมีประสิทธิภาพ"
"linktitle": "ตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java"
"url": "/th/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java

## การแนะนำ
ในแวดวงการเขียนโปรแกรม Java การจัดการการนำเสนออย่างมีประสิทธิภาพถือเป็นข้อกำหนดทั่วไป โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับองค์ประกอบ SmartArt Aspose.Slides สำหรับ Java เป็นเครื่องมืออันทรงพลังสำหรับงานดังกล่าว โดยมีฟังก์ชันต่างๆ มากมายสำหรับจัดการการนำเสนอด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides ทีละขั้นตอน
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### ชุดพัฒนา Java (JDK)
คุณต้องติดตั้ง JDK ไว้ในระบบของคุณ คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) และปฏิบัติตามคำแนะนำในการติดตั้ง
### Aspose.Slides สำหรับ Java
ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก [ลิงค์ดาวน์โหลด](https://releases.aspose.com/slides/java/). ปฏิบัติตามคำแนะนำในการติดตั้งที่ระบุไว้ในเอกสารประกอบสำหรับระบบปฏิบัติการเฉพาะของคุณ

## แพ็คเกจนำเข้า
ในการเริ่มต้น ให้นำเข้าแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
มาแบ่งตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ เพื่อความเข้าใจที่ชัดเจนว่าต้องตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java กับ Aspose.Slides อย่างไร
## ขั้นตอนที่ 1: สร้างวัตถุการนำเสนอ
```java
Presentation presentation = new Presentation();
```
ขั้นแรก ให้สร้างอินสแตนซ์ใหม่ของคลาส Presentation ซึ่งแสดงการนำเสนอ PowerPoint
## ขั้นตอนที่ 2: เพิ่ม SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
ขั้นตอนต่อไป เพิ่มรูปร่าง SmartArt ลงในสไลด์ บรรทัดโค้ดนี้จะเริ่มต้นรูปร่าง SmartArt ใหม่โดยมีขนาดและเค้าโครงที่ระบุ
## ขั้นตอนที่ 3: เข้าถึง SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
ตอนนี้ให้เข้าถึงโหนดแรก (หรือโหนดใดๆ ที่ต้องการ) ภายในรูปร่าง SmartArt เพื่อปรับเปลี่ยนคุณสมบัติ
## ขั้นตอนที่ 4: ตั้งค่ารูปแบบการเติมหัวข้อย่อย
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
ที่นี่ เราจะตรวจสอบว่ารูปแบบการเติมหัวเรื่องได้รับการรองรับหรือไม่ หากรองรับ เราจะโหลดไฟล์รูปภาพและตั้งค่าเป็นการเติมหัวเรื่องสำหรับโหนด SmartArt
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
สุดท้ายให้บันทึกการนำเสนอที่แก้ไขแล้วไปยังตำแหน่งที่ระบุ

## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีตั้งค่ารูปแบบการเติมหัวข้อย่อยใน SmartArt โดยใช้ Java ด้วย Aspose.Slides สำเร็จแล้ว ความสามารถนี้เปิดโลกแห่งความเป็นไปได้สำหรับการนำเสนอแบบไดนามิกและสวยงามในแอปพลิเคชัน Java
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java เพื่อสร้างงานนำเสนอตั้งแต่เริ่มต้นได้หรือไม่
แน่นอน! Aspose.Slides มอบ API ที่ครอบคลุมสำหรับการสร้าง ปรับเปลี่ยน และจัดการการนำเสนอทั้งหมดโดยใช้โค้ด
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ได้หรือไม่
ใช่ Aspose.Slides รับประกันความเข้ากันได้กับ Microsoft PowerPoint เวอร์ชันต่างๆ ช่วยให้สามารถบูรณาการเข้ากับเวิร์กโฟลว์ของคุณได้อย่างราบรื่น
### ฉันสามารถปรับแต่งองค์ประกอบ SmartArt ได้มากกว่ารูปแบบการเติมหัวข้อย่อยหรือไม่
Aspose.Slides ช่วยให้คุณสามารถปรับแต่งทุกแง่มุมของรูปทรง SmartArt ได้ รวมถึงเค้าโครง สไตล์ เนื้อหา และอื่นๆ อีกมากมาย
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถทดลองใช้งานฟีเจอร์ของ Aspose.Slides ได้ด้วยการทดลองใช้ฟรี เพียงดาวน์โหลดจาก [เว็บไซต์](https://releases.aspose.com/slides/java/) และเริ่มออกสำรวจ
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
หากมีคำถามหรือต้องการความช่วยเหลือ สามารถเข้าไปที่ฟอรัม Aspose.Slides ได้ที่ [ลิงค์นี้](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}