---
"description": "เรียนรู้วิธีสร้าง Zoom Frame ที่น่าสนใจใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ทำตามคำแนะนำของเราเพื่อเพิ่มองค์ประกอบแบบโต้ตอบให้กับงานนำเสนอของคุณ"
"linktitle": "สร้างกรอบซูมใน PowerPoint"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สร้างกรอบซูมใน PowerPoint"
"url": "/th/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สร้างกรอบซูมใน PowerPoint

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ที่น่าสนใจถือเป็นศิลปะ และบางครั้งการเพิ่มรายละเอียดเล็กๆ น้อยๆ ก็สามารถสร้างความแตกต่างได้อย่างมาก คุณลักษณะดังกล่าวประการหนึ่งคือ Zoom Frame ซึ่งช่วยให้คุณซูมเข้าไปในสไลด์หรือรูปภาพที่ต้องการได้ เพื่อสร้างงานนำเสนอที่โต้ตอบได้แบบไดนามิก ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้าง Zoom Frame ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- Java Development Kit (JDK) ติดตั้งอยู่บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น IntelliJ IDEA หรือ Eclipse
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java
## แพ็คเกจนำเข้า
ในการเริ่มต้น คุณต้องนำเข้าแพ็กเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ การนำเข้าเหล่านี้จะช่วยให้เข้าถึงฟังก์ชัน Aspose.Slides ที่จำเป็นสำหรับบทช่วยสอนนี้
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ
ขั้นแรก เราต้องสร้างการนำเสนอใหม่และเพิ่มสไลด์สองสามอันลงไป
```java
// ชื่อไฟล์เอาท์พุต
String resultPath = "ZoomFramePresentation.pptx";
// เส้นทางไปยังภาพต้นฉบับ
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // เพิ่มสไลด์ใหม่ลงในการนำเสนอ
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## ขั้นตอนที่ 2: ปรับแต่งพื้นหลังสไลด์
เราต้องการให้สไลด์ของเราโดดเด่นในด้านภาพโดยการเพิ่มสีพื้นหลัง
### การตั้งค่าพื้นหลังสำหรับสไลด์ที่สอง
```java
    // สร้างพื้นหลังให้กับสไลด์ที่สอง
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // สร้างกล่องข้อความสำหรับสไลด์ที่สอง
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### การตั้งค่าพื้นหลังสำหรับสไลด์ที่สาม
```java
    // สร้างพื้นหลังให้กับสไลด์ที่สาม
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // สร้างกล่องข้อความสำหรับสไลด์ที่สาม
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## ขั้นตอนที่ 3: การเพิ่มเฟรมซูม
ตอนนี้เรามาเพิ่ม Zoom Frame ให้กับงานนำเสนอกัน เราจะเพิ่ม Zoom Frame หนึ่งอันพร้อมภาพตัวอย่างสไลด์และอีกอันพร้อมรูปภาพที่กำหนดเอง
### การเพิ่มเฟรมซูมด้วยการดูตัวอย่างสไลด์
```java
    // เพิ่มวัตถุ ZoomFrame ด้วยการดูตัวอย่างสไลด์
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### การเพิ่มกรอบซูมด้วยรูปภาพที่กำหนดเอง
```java
    // เพิ่มวัตถุ ZoomFrame ด้วยรูปภาพที่กำหนดเอง
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## ขั้นตอนที่ 4: ปรับแต่งเฟรมการซูม
เพื่อให้ Zoom Frames ของเราโดดเด่น เราจะปรับแต่งรูปลักษณ์ของพวกมัน
### การปรับแต่งเฟรมซูมที่สอง
```java
    // ตั้งค่ารูปแบบเฟรมซูมสำหรับวัตถุ zoomFrame2
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### การซ่อนพื้นหลังสำหรับเฟรมซูมแรก
```java
    // อย่าแสดงพื้นหลังสำหรับวัตถุ zoomFrame1
    zoomFrame1.setShowBackground(false);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้ายเราบันทึกการนำเสนอของเราไปยังเส้นทางที่ระบุ
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
การสร้าง Zoom Frame ใน PowerPoint โดยใช้ Aspose.Slides สำหรับ Java จะช่วยปรับปรุงการโต้ตอบและการมีส่วนร่วมกับงานนำเสนอของคุณได้อย่างมาก เพียงทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณก็สามารถเพิ่มทั้งภาพตัวอย่างสไลด์และรูปภาพที่กำหนดเองเป็น Zoom Frame ได้อย่างง่ายดาย และปรับแต่งให้เหมาะกับธีมของงานนำเสนอของคุณ ขอให้สนุกกับการนำเสนอ!
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร?
Aspose.Slides สำหรับ Java เป็น API อันทรงพลังสำหรับการสร้างและจัดการการนำเสนอ PowerPoint ด้วยโปรแกรม
### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จาก [เว็บไซต์](https://releases.aspose.com/slides/java/) และเพิ่มลงในสิ่งที่ต้องมีของโครงการของคุณ
### ฉันสามารถปรับแต่งรูปลักษณ์ของ Zoom Frames ได้หรือไม่
ใช่ Aspose.Slides ช่วยให้คุณปรับแต่งคุณสมบัติต่างๆ ของ Zoom Frames เช่น สไตล์เส้น สี และการมองเห็นพื้นหลัง
### สามารถเพิ่มรูปภาพลงใน Zoom Frames ได้หรือไม่?
แน่นอน! คุณสามารถเพิ่มรูปภาพที่กำหนดเองลงใน Zoom Frames ได้โดยการอ่านไฟล์รูปภาพและเพิ่มลงในงานนำเสนอ
### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน
คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่ [หน้าเอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}