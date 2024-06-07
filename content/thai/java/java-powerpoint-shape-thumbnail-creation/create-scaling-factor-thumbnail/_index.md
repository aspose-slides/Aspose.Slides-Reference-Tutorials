---
title: สร้างภาพขนาดย่อของปัจจัยการปรับขนาด
linktitle: สร้างภาพขนาดย่อของปัจจัยการปรับขนาด
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างภาพขนาดย่อของปัจจัยการปรับขนาดใน Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำที่ปฏิบัติตามง่ายพร้อมคำแนะนำทีละขั้นตอน
type: docs
weight: 12
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างภาพขนาดย่อของปัจจัยการปรับขนาดโดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อให้ได้ผลลัพธ์ที่ต้องการ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและตั้งค่าในโปรเจ็กต์ Java ของคุณ
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็คเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโค้ด Java ของคุณ 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

ตอนนี้ เรามาแยกย่อยตัวอย่างที่ให้ไว้เป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งมีไฟล์งานนำเสนอ PowerPoint อยู่
```java
String dataDir = "Your Document Directory";
```
 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีเอกสารจริงของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์งานนำเสนอ PowerPoint
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 ให้แน่ใจว่าจะเปลี่ยน`"HelloWorld.pptx"` ด้วยชื่อไฟล์งานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 3: สร้างภาพขนาดเต็ม
สร้างภาพขนาดเต็มของสไลด์ที่ต้องการจากการนำเสนอ
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
โค้ดนี้จะดึงรูปขนาดย่อของรูปร่างแรกบนสไลด์แรกของงานนำเสนอ
## ขั้นตอนที่ 4: บันทึกภาพ
บันทึกภาพที่สร้างขึ้นลงดิสก์ในรูปแบบ PNG
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 ให้แน่ใจว่าจะเปลี่ยน`"Scaling Factor Thumbnail_out.png"` ด้วยชื่อไฟล์เอาต์พุตที่ต้องการ

## บทสรุป
โดยสรุป คุณได้สร้างภาพขนาดย่อของปัจจัยการปรับขนาดได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนที่ให้ไว้ คุณสามารถรวมฟังก์ชันการทำงานนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ Java IDE ใด ๆ ได้หรือไม่
ได้ Aspose.Slides สำหรับ Java สามารถใช้ได้กับ Java Integrated Development Environment (IDE) ใดๆ เช่น Eclipse, IntelliJ IDEA หรือ NetBeans
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถใช้ Aspose.Slides สำหรับ Java รุ่นทดลองใช้ฟรีได้โดยไปที่[เว็บไซต์](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ฉันจะซื้อ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถซื้อ Aspose.Slides สำหรับ Java ได้จาก[หน้าซื้อ](https://purchase.aspose.com/buy).
### ฉันต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[หน้าใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).