---
title: เพิ่มรูปภาพ Blob เพื่อนำเสนอใน Java Slides
linktitle: เพิ่มรูปภาพ Blob เพื่อนำเสนอใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มรูปภาพ Blob ลงในงานนำเสนอ Java Slides ได้อย่างง่ายดาย ปฏิบัติตามคำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดโดยใช้ Aspose.Slides สำหรับ Java
weight: 10
url: /th/java/image-handling/add-blob-image-to-presentation-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## รู้เบื้องต้นเกี่ยวกับการเพิ่มรูปภาพ Blob เพื่อนำเสนอใน Java Slides

ในคู่มือที่ครอบคลุมนี้ เราจะสำรวจวิธีเพิ่มรูปภาพ Blob ลงในงานนำเสนอโดยใช้ Java Slides Aspose.Slides สำหรับ Java มีคุณสมบัติที่มีประสิทธิภาพสำหรับการจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม เมื่อสิ้นสุดบทช่วยสอนนี้ คุณจะมีความเข้าใจที่ชัดเจนเกี่ยวกับวิธีการรวมรูปภาพ Blob เข้ากับงานนำเสนอของคุณ มาดำน้ำกันเถอะ!

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).
- รูปภาพ Blob ที่คุณต้องการเพิ่มลงในงานนำเสนอของคุณ

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ในโค้ด Java ของคุณ คุณต้องนำเข้าไลบรารีที่จำเป็นสำหรับ Aspose.Slides ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
import com.aspose.slides.*;
import java.io.FileInputStream;
```

## ขั้นตอนที่ 2: ตั้งค่าเส้นทาง

 กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณที่คุณจัดเก็บอิมเมจ Blob แทนที่`"Your Document Directory"` กับเส้นทางที่แท้จริง

```java
String dataDir = "Your Document Directory";
String pathToBlobImage = dataDir + "blob_image.jpg";
```

## ขั้นตอนที่ 3: โหลดรูปภาพ Blob

ถัดไป โหลดอิมเมจ Blob จากเส้นทางที่ระบุ

```java
FileInputStream fip = new FileInputStream(pathToBlobImage);
```

## ขั้นตอนที่ 4: สร้างงานนำเสนอใหม่

สร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides

```java
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 5: เพิ่มรูปภาพ Blob

 ตอนนี้ได้เวลาเพิ่มรูปภาพ Blob ลงในงานนำเสนอแล้ว เราใช้`addImage`วิธีการเพื่อให้บรรลุเป้าหมายนี้

```java
IPPImage img = pres.getImages().addImage(fip, LoadingStreamBehavior.KeepLocked);
pres.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, 300, 200, img);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยรูปภาพ Blob ที่เพิ่มเข้ามา

```java
pres.save(dataDir + "presentationWithBlobImage.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับเพิ่มรูปภาพ Blob เพื่อนำเสนอใน Java Slides

```java
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        String pathToLargeImage = dataDir + "large_image.jpg";
        // สร้างงานนำเสนอใหม่ซึ่งจะมีรูปภาพนี้
        Presentation pres = new Presentation();
        try
        {
            // สมมติว่าเรามีไฟล์ภาพขนาดใหญ่ที่เราต้องการรวมไว้ในงานนำเสนอ
            FileInputStream fip = new FileInputStream(dataDir + "large_image.jpg");
            try
            {
                // มาเพิ่มรูปภาพในงานนำเสนอ - เราเลือกพฤติกรรม KeepLocked เพราะเราไม่ทำ
                // มีเจตนาที่จะเข้าถึงไฟล์ "largeImage.png"
                IPPImage img = pres.getImages().addImage(fip, LoadingStreamBehavior.KeepLocked);
                pres.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, 300, 200, img);
                // บันทึกการนำเสนอ ถึงแม้ว่าผลงานการนำเสนอจะเป็นอย่างไร
                // ขนาดใหญ่ การใช้หน่วยความจำจะต่ำตลอดอายุการใช้งานของวัตถุ pres
                pres.save(dataDir + "presentationWithLargeImage.pptx", SaveFormat.Pptx);
            }
            finally
            {
                fip.close();
            }
        }
        catch (java.io.IOException e)
        {
            e.printStackTrace();
        }
        finally
        {
            pres.dispose();
        }
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีเพิ่มรูปภาพ Blob ลงในงานนำเสนอใน Java Slides โดยใช้ Aspose.Slides เรียบร้อยแล้ว ทักษะนี้สามารถประเมินค่าได้เมื่อคุณต้องการปรับปรุงการนำเสนอของคุณด้วยรูปภาพที่กำหนดเอง ทดลองใช้รูปภาพและเค้าโครงต่างๆ เพื่อสร้างสไลด์ที่สวยงามตระการตา

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

Aspose.Slides สำหรับ Java สามารถติดตั้งได้อย่างง่ายดายโดยการดาวน์โหลดไลบรารีจากเว็บไซต์[ที่นี่](https://releases.aspose.com/slides/java/)- ปฏิบัติตามคำแนะนำในการติดตั้งที่ให้ไว้เพื่อรวมเข้ากับโปรเจ็กต์ Java ของคุณ

### ฉันสามารถเพิ่มรูปภาพ Blob หลายรูปในงานนำเสนอเดียวได้หรือไม่

ได้ คุณสามารถเพิ่มรูปภาพ Blob หลายรูปในงานนำเสนอเดียวได้ เพียงทำซ้ำขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้สำหรับแต่ละภาพที่คุณต้องการรวม

### รูปแบบภาพที่แนะนำสำหรับการนำเสนอคืออะไร?

ขอแนะนำให้ใช้รูปแบบรูปภาพทั่วไป เช่น JPEG หรือ PNG ในการนำเสนอ Aspose.Slides สำหรับ Java รองรับรูปแบบภาพที่หลากหลาย ทำให้มั่นใจได้ถึงความเข้ากันได้กับซอฟต์แวร์การนำเสนอส่วนใหญ่

### ฉันจะปรับแต่งตำแหน่งและขนาดของรูปภาพ Blob ที่เพิ่มได้อย่างไร

 คุณสามารถปรับตำแหน่งและขนาดของรูปภาพ Blob ที่เพิ่มได้โดยการแก้ไขพารามิเตอร์ใน`addPictureFrame` วิธี. ค่าสี่ค่า (พิกัด x, พิกัด y, ความกว้าง และความสูง) จะกำหนดตำแหน่งและขนาดของกรอบภาพ

### Aspose.Slides เหมาะสำหรับงาน PowerPoint อัตโนมัติขั้นสูงหรือไม่

อย่างแน่นอน! Aspose.Slides นำเสนอความสามารถขั้นสูงสำหรับการทำงานอัตโนมัติของ PowerPoint รวมถึงการสร้างสไลด์ การแก้ไข และการดึงข้อมูล เป็นเครื่องมือที่มีประสิทธิภาพในการปรับปรุงงานที่เกี่ยวข้องกับ PowerPoint ของคุณ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
