---
"description": "เรียนรู้วิธีสร้างภาพขนาดย่อของปัจจัยการปรับขนาดใน Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำที่ทำตามได้ง่ายพร้อมคำแนะนำทีละขั้นตอน"
"linktitle": "สร้างภาพย่อของปัจจัยการปรับขนาด"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างภาพย่อของปัจจัยการปรับขนาด"
"url": "/th/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพย่อของปัจจัยการปรับขนาด

## การแนะนำ
ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างภาพย่อแบบปรับขนาดโดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำทีละขั้นตอนเหล่านี้เพื่อให้ได้ผลลัพธ์ตามต้องการ
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- ดาวน์โหลดและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโครงการ Java ของคุณแล้ว
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
ขั้นแรก นำเข้าแพ็กเกจที่จำเป็นสำหรับการทำงานกับ Aspose.Slides ในโค้ด Java ของคุณ 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

ตอนนี้เรามาแบ่งตัวอย่างที่ให้มาเป็นขั้นตอนต่างๆ กัน:
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสาร
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณซึ่งไฟล์งานนำเสนอ PowerPoint ตั้งอยู่
```java
String dataDir = "Your Document Directory";
```
แทนที่ `"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีเอกสารจริงของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
สร้างอินสแตนซ์ของคลาสการนำเสนอเพื่อแสดงไฟล์การนำเสนอ PowerPoint
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
ให้แน่ใจว่าจะเปลี่ยน `"HelloWorld.pptx"` ด้วยชื่อไฟล์งานนำเสนอ PowerPoint ของคุณ
## ขั้นตอนที่ 3: สร้างภาพขนาดเต็ม
สร้างภาพเต็มขนาดของสไลด์ที่ต้องการจากการนำเสนอ
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
โค้ดนี้จะดึงภาพขนาดย่อของรูปร่างแรกในสไลด์แรกของการนำเสนอ
## ขั้นตอนที่ 4: บันทึกภาพ
บันทึกภาพที่สร้างไปยังดิสก์ในรูปแบบ PNG
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
ให้แน่ใจว่าจะเปลี่ยน `"Scaling Factor Thumbnail_out.png"` พร้อมชื่อไฟล์เอาท์พุตที่ต้องการ

## บทสรุป
สรุปแล้ว คุณได้สร้างภาพย่อของปัจจัยการปรับขนาดสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนที่ให้ไว้ คุณสามารถรวมฟังก์ชันนี้เข้ากับแอปพลิเคชัน Java ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Slides สำหรับ Java กับ Java IDE ใดๆ ได้หรือไม่
ใช่ Aspose.Slides สำหรับ Java สามารถใช้ร่วมกับ Java Integrated Development Environment (IDE) เช่น Eclipse, IntelliJ IDEA หรือ NetBeans ได้
### มี Aspose.Slides สำหรับ Java ให้ทดลองใช้งานฟรีหรือไม่
ใช่ คุณสามารถใช้ประโยชน์จากการทดลองใช้ Aspose.Slides สำหรับ Java ได้ฟรีโดยเข้าไปที่ [เว็บไซต์](https://releases-aspose.com/).
### ฉันสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
คุณสามารถค้นหาการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้ที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### ฉันสามารถซื้อ Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถซื้อ Aspose.Slides สำหรับ Java ได้จาก [หน้าการซื้อ](https://purchase-aspose.com/buy).
### ฉันต้องมีใบอนุญาตชั่วคราวเพื่อใช้ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถขอใบอนุญาตชั่วคราวได้จาก [หน้าใบอนุญาตชั่วคราว](https://purchase-aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}