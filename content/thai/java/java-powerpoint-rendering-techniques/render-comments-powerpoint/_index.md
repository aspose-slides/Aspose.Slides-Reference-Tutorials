---
title: แสดงความคิดเห็นใน PowerPoint
linktitle: แสดงความคิดเห็นใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแสดงความคิดเห็นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับแต่งรูปลักษณ์และสร้างตัวอย่างภาพได้อย่างมีประสิทธิภาพ
type: docs
weight: 10
url: /th/java/java-powerpoint-rendering-techniques/render-comments-powerpoint/
---
## การแนะนำ
ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการแสดงความคิดเห็นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การแสดงความเห็นอาจมีประโยชน์สำหรับวัตถุประสงค์ต่างๆ เช่น การสร้างภาพตัวอย่างการนำเสนอพร้อมความคิดเห็นรวมอยู่ด้วย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณแล้ว
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. IDE: คุณต้องมี Integrated Development Environment (IDE) เช่น Eclipse หรือ IntelliJ IDEA เพื่อเขียนและรันโค้ด Java
## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโค้ด Java ของคุณ:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าสภาพแวดล้อม
ขั้นแรก ให้ตั้งค่าสภาพแวดล้อม Java ของคุณโดยรวมไลบรารี Aspose.Slides ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ คุณสามารถทำได้โดยการดาวน์โหลดไลบรารีจากลิงก์ที่ให้มา และเพิ่มลงในเส้นทางการ build ของโปรเจ็กต์ของคุณ
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
โหลดไฟล์งานนำเสนอ PowerPoint ที่มีความคิดเห็นที่คุณต้องการแสดง
```java
String dataDir = "path/to/your/presentation/";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```
## ขั้นตอนที่ 3: กำหนดค่าตัวเลือกการแสดงผล
กำหนดค่าตัวเลือกการเรนเดอร์เพื่อปรับแต่งวิธีแสดงข้อคิดเห็น
```java
IRenderingOptions renderOptions = new RenderingOptions();
renderOptions.getNotesCommentsLayouting().setCommentsAreaColor(Color.RED);
renderOptions.getNotesCommentsLayouting().setCommentsAreaWidth(200);
renderOptions.getNotesCommentsLayouting().setCommentsPosition(CommentsPositions.Right);
renderOptions.getNotesCommentsLayouting().setNotesPosition(NotesPositions.BottomTruncated);
```
## ขั้นตอนที่ 4: แสดงความคิดเห็นต่อรูปภาพ
แสดงความคิดเห็นไปยังไฟล์รูปภาพโดยใช้ตัวเลือกการเรนเดอร์ที่ระบุ
```java
try {
    BufferedImage image = new BufferedImage(740, 960, BufferedImage.TYPE_INT_ARGB);
    Graphics2D graphics = image.createGraphics();
    try {
        pres.getSlides().get_Item(0).renderToGraphics(renderOptions, graphics);
    } finally {
        if (graphics != null) graphics.dispose();
    }
    ImageIO.write(image, "png", new File(resultPath));
} finally {
    if (pres != null) pres.dispose();
}
```

## บทสรุป
ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีแสดงความคิดเห็นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถสร้างตัวอย่างรูปภาพของงานนำเสนอพร้อมความคิดเห็นรวมอยู่ด้วย ซึ่งจะช่วยปรับปรุงการแสดงภาพไฟล์ PowerPoint ของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถแสดงความคิดเห็นจากหลายสไลด์ได้หรือไม่
ได้ คุณสามารถวนซ้ำสไลด์ทั้งหมดในงานนำเสนอและแสดงความคิดเห็นจากแต่ละสไลด์แยกกัน
### เป็นไปได้ไหมที่จะปรับแต่งลักษณะที่ปรากฏของความคิดเห็นที่แสดงผล?
แน่นอน คุณสามารถปรับพารามิเตอร์ต่างๆ เช่น สี ขนาด และตำแหน่งของพื้นที่แสดงความคิดเห็นได้ตามความต้องการของคุณ
### Aspose.Slides รองรับการแสดงความคิดเห็นในรูปแบบภาพอื่นนอกเหนือจาก PNG หรือไม่
ใช่ นอกจาก PNG แล้ว คุณยังสามารถแสดงความคิดเห็นในรูปแบบภาพอื่นๆ ที่รองรับโดยคลาส ImageIO ของ Java ได้
### ฉันสามารถแสดงความคิดเห็นโดยทางโปรแกรมโดยไม่ต้องแสดงใน PowerPoint ได้หรือไม่
ใช่ เมื่อใช้ Aspose.Slides คุณสามารถแสดงความคิดเห็นกับรูปภาพได้โดยไม่ต้องเปิดแอปพลิเคชัน PowerPoint
### มีวิธีแสดงความคิดเห็นโดยตรงไปยังเอกสาร PDF หรือไม่
ใช่ Aspose.Slides มีฟังก์ชันในการแสดงความคิดเห็นโดยตรงไปยังเอกสาร PDF ช่วยให้สามารถผสานรวมเข้ากับเวิร์กโฟลว์เอกสารของคุณได้อย่างราบรื่น