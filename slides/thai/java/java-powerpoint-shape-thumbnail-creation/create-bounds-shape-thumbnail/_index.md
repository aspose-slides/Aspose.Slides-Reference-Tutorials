---
"description": "เรียนรู้วิธีสร้างรูปขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนทีละขั้นตอนนี้จะแนะนำคุณตลอดกระบวนการ"
"linktitle": "สร้างภาพขนาดย่อของขอบเขตรูปร่าง"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างภาพขนาดย่อของขอบเขตรูปร่าง"
"url": "/th/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างภาพขนาดย่อของขอบเขตรูปร่าง

## การแนะนำ
Aspose.Slides สำหรับ Java เป็นไลบรารีอันทรงพลังที่ช่วยให้ผู้พัฒนา Java สามารถสร้าง จัดการ และแปลงงานนำเสนอ PowerPoint ได้ด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
2. ดาวน์โหลดและเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## แพ็คเกจนำเข้า
ตรวจสอบให้แน่ใจว่าคุณนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณต้องการ และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: สร้างอินสแตนซ์ของวัตถุการนำเสนอ
สร้างตัวอย่าง `Presentation` วัตถุโดยระบุเส้นทางไปยังไฟล์การนำเสนอ PowerPoint ของคุณ
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## ขั้นตอนที่ 3: สร้างภาพขนาดย่อของขอบเขต
ต่อไปเรามาสร้างภาพย่อของรูปร่างพร้อมขอบเขตจากการนำเสนอกัน
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างภาพขนาดย่อของรูปร่างที่มีขอบเขตโดยใช้ Aspose.Slides สำหรับ Java เมื่อทำตามขั้นตอนเหล่านี้ คุณก็สามารถสร้างภาพขนาดย่อของรูปร่างในงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดายด้วยโปรแกรม
## คำถามที่พบบ่อย
### ฉันสามารถสร้างภาพขนาดย่อสำหรับรูปร่างเฉพาะภายในสไลด์ได้หรือไม่
ใช่ คุณสามารถเข้าถึงรูปร่างแต่ละรูปร่างภายในสไลด์และสร้างภาพขนาดย่อสำหรับรูปร่างเหล่านั้นได้โดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java สามารถใช้งานร่วมกับไฟล์ PowerPoint ทุกเวอร์ชันได้หรือไม่
Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint ต่างๆ รวมถึง PPT, PPTX, PPS, PPSX และอื่นๆ อีกมากมาย
### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของภาพขนาดย่อที่สร้างขึ้นได้หรือไม่
ใช่ คุณสามารถปรับเปลี่ยนคุณสมบัติของภาพขนาดย่อ เช่น ขนาดและคุณภาพ ตามความต้องการของคุณได้
### Aspose.Slides สำหรับ Java รองรับฟีเจอร์อื่นนอกเหนือจากการสร้างภาพขนาดย่อหรือไม่
ใช่ Aspose.Slides สำหรับ Java มีฟังก์ชันมากมายสำหรับการทำงานกับการนำเสนอ PowerPoint รวมถึงการจัดการสไลด์ การแยกข้อความ และการสร้างแผนภูมิ
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Slides สำหรับ Java หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้งานฟรีได้จาก [ที่นี่](https://releases-aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}