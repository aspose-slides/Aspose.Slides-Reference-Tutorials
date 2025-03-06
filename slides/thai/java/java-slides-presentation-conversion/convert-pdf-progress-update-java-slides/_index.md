---
title: แปลงเป็น PDF ด้วย Progress Update ใน Java Slides
linktitle: แปลงเป็น PDF ด้วย Progress Update ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: แปลง PowerPoint เป็น PDF ด้วยการอัปเดตความคืบหน้าใน Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดและการติดตามความคืบหน้าเพื่อการแปลงที่ราบรื่น
weight: 36
url: /th/java/presentation-conversion/convert-pdf-progress-update-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลง PowerPoint เป็น PDF พร้อมการอัปเดตความคืบหน้าใน Java โดยใช้ Aspose.Slides สำหรับ Java

ในคำแนะนำทีละขั้นตอนนี้ เราจะสาธิตวิธีการแปลงงานนำเสนอ PowerPoint (PPTX) เป็นไฟล์ PDF ใน Java โดยใช้ Aspose.Slides สำหรับ Java นอกจากนี้ เราจะรวมการอัปเดตความคืบหน้าระหว่างกระบวนการแปลงด้วย

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ตั้งค่าสภาพแวดล้อมการพัฒนา Java
-  เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://downloads.aspose.com/slides/java).

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java Library

ในการเริ่มต้น คุณต้องนำเข้าไลบรารี Aspose.Slides ไปยังโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไฟล์ Aspose.Slides JAR ลงใน classpath ของคุณแล้ว

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: สร้างคลาส Java

 สร้างคลาส Java ที่คุณจะทำการแปลง PowerPoint เป็น PDF มาตั้งชื่อกันเถอะ`PowerPointToPdfConverter`.

```java
public class PowerPointToPdfConverter {
    public static void main(String[] args) {
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
    }
}
```

## ขั้นตอนที่ 3: ใช้การเรียกกลับความคืบหน้า

 เราจะใช้ตัวจัดการการโทรกลับความคืบหน้าเพื่อรับการอัปเดตระหว่างกระบวนการแปลง มาสร้างคลาสที่ชื่อว่า`ExportProgressHandler` เพื่อจุดประสงค์นี้.

```java
class ExportProgressHandler implements IProgressCallback {
    public void reporting(double progressValue) {
        // ใช้ค่าเปอร์เซ็นต์ความคืบหน้าที่นี่
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
    }
}
```

## ขั้นตอนที่ 4: แทนที่ 'ไดเรกทอรีเอกสารของคุณ'

 แทนที่`"Your Document Directory"` ใน`PowerPointToPdfConverter` คลาสพร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณและไดเร็กทอรีเอาต์พุตที่ต้องการ

## ขั้นตอนที่ 5: คอมไพล์และรัน

คอมไพล์คลาส Java ของคุณและรันไฟล์`PowerPointToPdfConverter` ระดับ. มันจะแปลงงานนำเสนอ PowerPoint เป็นไฟล์ PDF ในขณะที่ให้การอัปเดตความคืบหน้าในคอนโซล

## กรอกซอร์สโค้ดสำหรับการแปลงเป็น PDF พร้อมอัปเดตความคืบหน้าใน Java Slides

```java
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "ConvertToPDF.pptx");
        try
        {
            ISaveOptions saveOptions = new PdfOptions();
            saveOptions.setProgressCallback(new ExportProgressHandler());
            presentation.save(dataDir + "ConvertToPDF.pdf", SaveFormat.Pdf, saveOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
    }
}
class ExportProgressHandler implements IProgressCallback
{
    public void reporting(double progressValue)
    {
        // ใช้ค่าเปอร์เซ็นต์ความคืบหน้าที่นี่
        long progress = Math.round(progressValue);
        System.out.println(progress + "% file converted");
```

## บทสรุป

ในคำแนะนำทีละขั้นตอนนี้ เราได้ศึกษาวิธีแปลงงานนำเสนอ PowerPoint (PPTX) เป็นไฟล์ PDF ใน Java โดยใช้ Aspose.Slides สำหรับ Java นอกจากนี้เรายังใช้การอัปเดตความคืบหน้าในระหว่างกระบวนการแปลงเพื่อติดตามสถานะของการดำเนินการ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose ที่[ที่นี่](https://downloads.aspose.com/slides/java).

###  มีจุดประสงค์อะไร.`IProgressCallback`?

`IProgressCallback` เป็นอินเทอร์เฟซที่ Aspose.Slides สำหรับ Java จัดทำขึ้นเพื่อใช้การรายงานความคืบหน้าระหว่างการดำเนินการส่งออก ช่วยให้คุณสามารถติดตามความคืบหน้าของงานต่างๆ เช่น การแปลงงานนำเสนอเป็น PDF

### ฉันสามารถใช้ Aspose.Slides สำหรับ Java สำหรับการดำเนินการ PowerPoint อื่นๆ ได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java มีฟังก์ชันการทำงานที่ครอบคลุมสำหรับการทำงานกับงานนำเสนอ PowerPoint รวมถึงการสร้าง การแก้ไข และการแปลงเป็นรูปแบบต่างๆ

### ฉันจะปรับแต่งตัวเลือกการแปลง PDF ได้อย่างไร

 คุณสามารถปรับแต่งตัวเลือกการแปลง PDF ได้โดยการแก้ไข`PdfOptions` วัตถุก่อนที่จะเรียก`presentation.save` วิธี. ซึ่งรวมถึงการตั้งค่าคุณสมบัติ เช่น ขนาดหน้า คุณภาพ และอื่นๆ

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
