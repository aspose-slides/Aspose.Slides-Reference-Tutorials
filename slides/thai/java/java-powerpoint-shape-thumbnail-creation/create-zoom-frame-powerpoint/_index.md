---
title: สร้างกรอบการซูมใน PowerPoint
linktitle: สร้างกรอบการซูมใน PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้าง Zoom Frames ที่น่าสนใจใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปฏิบัติตามคำแนะนำของเราเพื่อเพิ่มองค์ประกอบเชิงโต้ตอบให้กับงานนำเสนอของคุณ
type: docs
weight: 17
url: /th/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---
## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจนั้นเป็นศิลปะอย่างหนึ่ง และบางครั้งการเพิ่มเติมเพียงเล็กน้อยก็สามารถสร้างความแตกต่างได้อย่างมาก คุณสมบัติอย่างหนึ่งคือ Zoom Frame ซึ่งช่วยให้คุณสามารถซูมเข้าไปในสไลด์หรือรูปภาพที่ต้องการ สร้างการนำเสนอแบบไดนามิกและโต้ตอบได้ ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้าง Zoom Frame ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณจะต้องนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ การนำเข้าเหล่านี้จะช่วยให้สามารถเข้าถึงฟังก์ชัน Aspose.Slides ที่จำเป็นสำหรับบทช่วยสอนนี้
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
ขั้นแรก เราต้องสร้างงานนำเสนอใหม่และเพิ่มสไลด์สองสามสไลด์ลงไป
```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "ZoomFramePresentation.pptx";
// เส้นทางไปยังรูปภาพต้นฉบับ
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // เพิ่มสไลด์ใหม่ให้กับงานนำเสนอ
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## ขั้นตอนที่ 2: การปรับแต่งพื้นหลังสไลด์
เราต้องการทำให้สไลด์ของเราดูแตกต่างด้วยการเพิ่มสีพื้นหลัง
### การตั้งค่าพื้นหลังสำหรับสไลด์ที่สอง
```java
    // สร้างพื้นหลังสำหรับสไลด์ที่สอง
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // สร้างกล่องข้อความสำหรับสไลด์ที่สอง
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### การตั้งค่าพื้นหลังสำหรับสไลด์ที่สาม
```java
    // สร้างพื้นหลังสำหรับสไลด์ที่สาม
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // สร้างกล่องข้อความสำหรับสไลด์ที่สาม
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## ขั้นตอนที่ 3: การเพิ่มเฟรมการซูม
ตอนนี้ มาเพิ่ม Zoom Frames ให้กับงานนำเสนอกันดีกว่า เราจะเพิ่ม Zoom Frame หนึ่งเฟรมพร้อมการแสดงตัวอย่างสไลด์ และอีกเฟรมหนึ่งพร้อมรูปภาพที่กำหนดเอง
### การเพิ่มกรอบการซูมด้วยการแสดงตัวอย่างสไลด์
```java
    // เพิ่มวัตถุ ZoomFrame ด้วยการแสดงตัวอย่างสไลด์
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### การเพิ่มกรอบการซูมด้วยรูปภาพที่กำหนดเอง
```java
    // เพิ่มวัตถุ ZoomFrame ด้วยรูปภาพที่กำหนดเอง
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## ขั้นตอนที่ 4: การปรับแต่งเฟรมการซูม
เพื่อให้ Zoom Frames ของเราโดดเด่น เราจะปรับแต่งรูปลักษณ์ของมัน
### การปรับแต่งเฟรมการซูมที่สอง
```java
    // ตั้งค่ารูปแบบเฟรมการซูมสำหรับวัตถุ ZoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### การซ่อนพื้นหลังสำหรับเฟรมการซูมแรก
```java
    // อย่าแสดงพื้นหลังสำหรับวัตถุ ZoomFrame1
    zoomFrame1.setShowBackground(false);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้าย เราบันทึกการนำเสนอของเราไปยังเส้นทางที่ระบุ
```java
    // บันทึกการนำเสนอ
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## บทสรุป
การสร้างเฟรมการซูมใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สามารถปรับปรุงการโต้ตอบและการมีส่วนร่วมของงานนำเสนอของคุณได้อย่างมาก ด้วยการทำตามขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้ คุณสามารถเพิ่มทั้งตัวอย่างสไลด์และรูปภาพที่กำหนดเองเป็น Zoom Frames ได้อย่างง่ายดาย โดยปรับแต่งให้เข้ากับธีมของงานนำเสนอของคุณ มีความสุขในการนำเสนอ!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่ทรงพลังสำหรับการสร้างและจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก[เว็บไซต์](https://releases.aspose.com/slides/java/) และเพิ่มลงในการขึ้นต่อกันของโครงการของคุณ
### ฉันสามารถปรับแต่งรูปลักษณ์ของ Zoom Frames ได้หรือไม่?
ใช่ Aspose.Slides ช่วยให้คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของ Zoom Frames ได้ เช่น สไตล์เส้น สี และการมองเห็นพื้นหลัง
### สามารถเพิ่มรูปภาพลงใน Zoom Frames ได้หรือไม่?
อย่างแน่นอน! คุณสามารถเพิ่มรูปภาพแบบกำหนดเองลงใน Zoom Frames ได้โดยการอ่านไฟล์รูปภาพและเพิ่มลงในงานนำเสนอ
### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน
 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่[Aspose.Slides สำหรับหน้าเอกสารประกอบ Java](https://reference.aspose.com/slides/java/).