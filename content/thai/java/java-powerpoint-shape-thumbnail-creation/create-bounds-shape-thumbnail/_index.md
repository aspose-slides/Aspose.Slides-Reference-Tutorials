---
title: สร้างรูปขนาดย่อของรูปร่างขอบเขต
linktitle: สร้างรูปขนาดย่อของรูปร่างขอบเขต
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนแบบทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ
type: docs
weight: 10
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## การแนะนำ
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนา Java สามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
2.  Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ไปยังการขึ้นต่อกันของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
 ยกตัวอย่าง`Presentation` วัตถุโดยระบุเส้นทางไปยังไฟล์งานนำเสนอ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## ขั้นตอนที่ 3: สร้างรูปขนาดย่อของรูปร่างขอบเขต
ตอนนี้ เรามาสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตจากการนำเสนอกันดีกว่า
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณจะสามารถสร้างรูปขนาดย่อของรูปร่างในงานนำเสนอ PowerPoint ของคุณโดยทางโปรแกรมได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### ฉันสามารถสร้างรูปขนาดย่อสำหรับรูปร่างเฉพาะภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถเข้าถึงแต่ละรูปร่างภายในสไลด์และสร้างภาพขนาดย่อสำหรับรูปร่างเหล่านั้นได้โดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java เข้ากันได้กับไฟล์ PowerPoint ทุกเวอร์ชันหรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint หลากหลาย รวมถึง PPT, PPTX, PPS, PPSX และอื่นๆ
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของภาพขนาดย่อที่สร้างขึ้นได้หรือไม่
ได้ คุณสามารถปรับคุณสมบัติของภาพขนาดย่อได้ เช่น ขนาดและคุณภาพ ตามความต้องการของคุณ
### Aspose.Slides สำหรับ Java รองรับคุณสมบัติอื่น ๆ นอกเหนือจากการสร้างภาพขนาดย่อหรือไม่
ใช่ Aspose.Slides สำหรับ Java มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการทำงานกับงานนำเสนอ PowerPoint รวมถึงการจัดการสไลด์ การแยกข้อความ และการสร้างแผนภูมิ
### มีรุ่นทดลองใช้งานสำหรับ Aspose.Slides สำหรับ Java หรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).