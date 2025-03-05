---
title: เพิ่มรูปภาพภายในเซลล์ตารางใน Java PowerPoint
linktitle: เพิ่มรูปภาพภายในเซลล์ตารางใน Java PowerPoint
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มรูปภาพภายในเซลล์ตารางในงานนำเสนอ Java PowerPoint พร้อมคำแนะนำทีละขั้นตอนโดยละเอียดโดยใช้ Aspose.Slides สำหรับ Java
type: docs
weight: 10
url: /th/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---
## การแนะนำ
หากคุณต้องการปรับปรุงงานนำเสนอ Java PowerPoint ของคุณด้วยการฝังรูปภาพภายในเซลล์ตาราง แสดงว่าคุณมาถูกที่แล้ว! วันนี้ เราจะมาเจาะลึกคำแนะนำโดยละเอียดทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ Java บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการทั้งหมด เพื่อให้มั่นใจว่าแม้แต่มือใหม่ก็สามารถทำตามได้และบรรลุผลลัพธ์ที่น่าทึ่ง
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีทุกสิ่งที่คุณต้องการ:
1.  Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนเครื่องของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์ของออราเคิล](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดไลบรารี Aspose.Slides จากไฟล์[เว็บไซต์](https://releases.aspose.com/slides/java/).
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE): เราแนะนำให้ใช้ IntelliJ IDEA หรือ Eclipse สำหรับการพัฒนา Java
4. ไฟล์รูปภาพ: เตรียมไฟล์รูปภาพที่คุณต้องการฝังไว้ในเซลล์ตาราง PowerPoint ของคุณ
ตอนนี้คุณมีข้อกำหนดเบื้องต้นทั้งหมดแล้ว มาดูการนำเข้าแพ็คเกจที่จำเป็นและเขียนโค้ดกันดีกว่า
## แพ็คเกจนำเข้า
ขั้นแรก อิมพอร์ตแพ็คเกจที่จำเป็นลงในโปรเจ็กต์ Java ของคุณ แพ็คเกจเหล่านี้จะช่วยให้คุณใช้ฟังก์ชันต่างๆ ที่ได้รับจาก Aspose.Slides และการจัดการรูปภาพของ Java
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
เรามาแบ่งตัวอย่างออกเป็นหลายขั้นตอนเพื่อให้ง่ายต่อการปฏิบัติตาม
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
เริ่มต้นด้วยการตั้งค่าวัตถุการนำเสนอและเข้าถึงสไลด์แรก
```java
// กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุคลาสการนำเสนอ
Presentation presentation = new Presentation();
```
ข้อมูลโค้ดนี้เริ่มต้นงานนำเสนอ PowerPoint ใหม่และเตรียมพร้อมสำหรับการแก้ไขเพิ่มเติม
## ขั้นตอนที่ 2: เข้าถึงสไลด์แรก
จากนั้น เข้าถึงสไลด์แรกของงานนำเสนอ สไลด์นี้จะเป็นผืนผ้าใบที่เราจะเพิ่มตาราง
```java
try {
    // เข้าถึงสไลด์แรก
    ISlide slide = presentation.getSlides().get_Item(0);
```
## ขั้นตอนที่ 3: กำหนดขนาดตาราง
กำหนดความกว้างของคอลัมน์และความสูงของแถวสำหรับตาราง ขั้นตอนนี้สำคัญมากเพื่อให้แน่ใจว่าเซลล์ตารางของคุณมีขนาดที่ถูกต้อง
```java
    // กำหนดคอลัมน์ที่มีความกว้างและแถวที่มีความสูง
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## ขั้นตอนที่ 4: เพิ่มตารางลงในสไลด์
เพิ่มรูปร่างตารางลงในสไลด์โดยใช้ขนาดที่ระบุ
```java
    // เพิ่มรูปทรงตารางเพื่อสไลด์
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## ขั้นตอนที่ 5: โหลดรูปภาพ
โหลดรูปภาพที่คุณต้องการฝังลงในเซลล์ตาราง ตรวจสอบให้แน่ใจว่าไฟล์รูปภาพมีอยู่ในไดเร็กทอรีที่คุณระบุ
```java
    // สร้างวัตถุ BufferedImage เพื่อเก็บไฟล์รูปภาพ
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // สร้างวัตถุ IPPImage โดยใช้วัตถุบิตแมป
    IPPImage imgx = presentation.getImages().addImage(image);
```
## ขั้นตอนที่ 6: เพิ่มรูปภาพลงในเซลล์ตาราง
ตอนนี้ได้เวลาเพิ่มรูปภาพลงในเซลล์แรกของตารางแล้ว กำหนดค่ารูปแบบการเติมและตั้งค่าคุณสมบัติรูปภาพ
```java
    // เพิ่มรูปภาพลงในเซลล์ตารางแรก
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## ขั้นตอนที่ 7: ปรับการครอบตัดรูปภาพ
ปรับการครอบตัดรูปภาพให้พอดีกับเซลล์หากจำเป็น ขั้นตอนนี้ช่วยให้มั่นใจว่าภาพของคุณดูเหมาะสม
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไดเร็กทอรีที่คุณต้องการ
```java
    // บันทึก PPTX ลงในดิสก์
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## บทสรุป
ได้แล้ว! ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มรูปภาพภายในเซลล์ตารางในงานนำเสนอ Java PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides คู่มือนี้ครอบคลุมทุกอย่างตั้งแต่การตั้งค่าสภาพแวดล้อมของคุณไปจนถึงการบันทึกการนำเสนอขั้นสุดท้าย ฉันหวังว่าบทช่วยสอนนี้จะช่วยให้คุณสร้างงานนำเสนอที่ดึงดูดสายตามากขึ้น
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ Java คืออะไร
Aspose.Slides สำหรับ Java เป็น API ที่มีประสิทธิภาพในการสร้าง แก้ไข และจัดการงานนำเสนอ PowerPoint ในแอปพลิเคชัน Java
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณจะได้รับ[ทดลองฟรี](https://releases.aspose.com/) เพื่อลองใช้ Aspose.Slides ก่อนซื้อ
### ฉันสามารถใช้รูปแบบภาพใดๆ กับ Aspose.Slides ได้หรือไม่
Aspose.Slides รองรับรูปแบบภาพที่หลากหลาย รวมถึง JPEG, PNG, BMP และอื่นๆ
### ฉันจะหาเอกสารรายละเอียดเพิ่มเติมได้จากที่ไหน?
 คุณสามารถอ้างถึง[เอกสารประกอบ](https://reference.aspose.com/slides/java/) สำหรับข้อมูลและตัวอย่างโดยละเอียดเพิ่มเติม
### ฉันจะซื้อ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถซื้อได้จาก[เว็บไซต์กำหนด](https://purchase.aspose.com/buy).