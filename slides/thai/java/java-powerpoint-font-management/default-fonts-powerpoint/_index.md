---
title: แบบอักษรเริ่มต้นใน PowerPoint พร้อม Aspose.Slides สำหรับ Java
linktitle: แบบอักษรเริ่มต้นใน PowerPoint พร้อม Aspose.Slides สำหรับ Java
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าแบบอักษรเริ่มต้นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java รับประกันความสม่ำเสมอและเพิ่มความดึงดูดสายตาได้อย่างง่ายดาย
weight: 11
url: /th/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint ด้วยแบบอักษรที่กำหนดเองถือเป็นข้อกำหนดทั่วไปในหลายโครงการ Aspose.Slides สำหรับ Java มอบโซลูชันที่ราบรื่นในการจัดการแบบอักษรเริ่มต้น เพื่อให้มั่นใจว่ามีความสอดคล้องกันในสภาพแวดล้อมที่แตกต่างกัน ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าแบบอักษรเริ่มต้นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
1. Java Development Kit (JDK): ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง JDK บนระบบของคุณ
2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้ง Aspose.Slides สำหรับ Java จาก[หน้าดาวน์โหลด](https://releases.aspose.com/slides/java/).
3. ความรู้ Java ขั้นพื้นฐาน: ความคุ้นเคยกับพื้นฐานภาษาการเขียนโปรแกรม Java

## แพ็คเกจนำเข้า
เริ่มต้นด้วยการนำเข้าแพ็คเกจที่จำเป็นในโปรเจ็กต์ Java ของคุณ:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## ขั้นตอนที่ 1: ตั้งค่าแบบอักษรเริ่มต้น
กำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณและสร้างตัวเลือกการโหลดเพื่อระบุแบบอักษรปกติและแบบอักษรเอเชียเริ่มต้น:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
โหลดงานนำเสนอ PowerPoint โดยใช้ตัวเลือกการโหลดที่กำหนดไว้:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## ขั้นตอนที่ 3: สร้างผลลัพธ์
สร้างเอาต์พุตต่างๆ เช่น ภาพขนาดย่อของสไลด์, ไฟล์ PDF และ XPS:
```java
try {
    // สร้างภาพขนาดย่อของสไลด์
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // สร้าง PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // สร้าง XPS
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## บทสรุป
การตั้งค่าแบบอักษรเริ่มต้นในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java นั้นตรงไปตรงมาและมีประสิทธิภาพ ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรับประกันความสอดคล้องของรูปแบบตัวอักษรบนแพลตฟอร์มและสภาพแวดล้อมที่แตกต่างกัน ซึ่งช่วยเพิ่มความน่าดึงดูดทางสายตาให้กับงานนำเสนอของคุณ
## คำถามที่พบบ่อย
### ฉันสามารถใช้แบบอักษรที่กำหนดเองกับ Aspose.Slides สำหรับ Java ได้หรือไม่
ได้ คุณสามารถระบุแบบอักษรที่กำหนดเองในงานนำเสนอของคุณโดยใช้ Aspose.Slides สำหรับ Java
### Aspose.Slides สำหรับ Java เข้ากันได้กับ PowerPoint ทุกรุ่นหรือไม่
Aspose.Slides สำหรับ Java รองรับ PowerPoint เวอร์ชันต่างๆ มากมาย จึงรับประกันความเข้ากันได้ในสภาพแวดล้อมที่แตกต่างกัน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ Java ผ่านทาง[กำหนดฟอรั่ม](https://forum.aspose.com/c/slides/11).
### ฉันสามารถลองใช้ Aspose.Slides สำหรับ Java ก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถสำรวจ Aspose.Slides สำหรับ Java ได้ผ่านการทดลองใช้ฟรีที่[releases.aspose.com](https://releases.aspose.com/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน
 คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ Java ได้จาก[หน้าซื้อ](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
