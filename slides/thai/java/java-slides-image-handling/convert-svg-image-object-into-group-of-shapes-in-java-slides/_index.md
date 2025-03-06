---
title: แปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides
linktitle: แปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ด
weight: 13
url: /th/java/image-handling/convert-svg-image-object-into-group-of-shapes-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides

ในคู่มือที่ครอบคลุมนี้ เราจะสำรวจวิธีแปลงออบเจ็กต์รูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API ไลบรารีอันทรงพลังนี้ช่วยให้นักพัฒนาจัดการงานนำเสนอ PowerPoint ด้วยการเขียนโปรแกรม ทำให้เป็นเครื่องมืออันมีค่าสำหรับงานต่างๆ รวมถึงการจัดการรูปภาพด้วย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ดและคำแนะนำทีละขั้นตอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  Aspose.Slides สำหรับไลบรารี Java คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

เมื่อเตรียมทุกอย่างเรียบร้อยแล้ว เรามาเริ่มกันเลย

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ในการเริ่มต้น คุณจะต้องนำเข้าไลบรารีที่จำเป็นสำหรับโปรเจ็กต์ Java ของคุณ ตรวจสอบให้แน่ใจว่าได้รวม Aspose.Slides สำหรับ Java

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

 ถัดไป คุณจะต้องโหลดงานนำเสนอ PowerPoint ที่มีวัตถุรูปภาพ SVG แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "image.pptx");
```

## ขั้นตอนที่ 3: ดึงภาพ SVG

ตอนนี้ขอดึงวัตถุรูปภาพ SVG จากงานนำเสนอ PowerPoint เราจะถือว่ารูปภาพ SVG อยู่บนสไลด์แรกและเป็นรูปร่างแรกบนสไลด์นั้น

```java
try
{
    PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
```

## ขั้นตอนที่ 4: แปลงรูปภาพ SVG เป็นกลุ่มของรูปร่าง

เมื่อมีรูปภาพ SVG อยู่ในมือ ตอนนี้เราสามารถแปลงมันเป็นกลุ่มของรูปร่างได้แล้ว ซึ่งสามารถทำได้โดยการเพิ่มรูปร่างกลุ่มใหม่ลงในสไลด์และลบรูปภาพ SVG ต้นฉบับออก

```java
    if (svgImage != null)
    {
        // แปลงภาพ svg ให้เป็นกลุ่มของรูปร่าง
        IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes()
                .addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                        pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());

        // ลบรูปภาพ SVG ต้นฉบับออกจากงานนำเสนอ
        pres.getSlides().get_Item(0).getShapes().remove(pFrame);
    }
```

## ขั้นตอนที่ 5: บันทึกงานนำเสนอที่แก้ไข

เมื่อคุณแปลงรูปภาพ SVG เป็นกลุ่มรูปร่างได้สำเร็จ ให้บันทึกงานนำเสนอที่แก้ไขแล้วเป็นไฟล์ใหม่

```java
    pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
}
finally
{
    pres.dispose();
}
```

ยินดีด้วย! ตอนนี้คุณได้เรียนรู้วิธีแปลงออบเจ็กต์รูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API แล้ว

## กรอกซอร์สโค้ดสำหรับการแปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างใน Java Slides

```java
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "image.pptx");
        try
        {
            PictureFrame pFrame = (PictureFrame) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ISvgImage svgImage = pFrame.getPictureFormat().getPicture().getImage().getSvgImage();
            if (svgImage != null)
            {
                // แปลงภาพ svg เป็นกลุ่มของรูปร่าง
                IGroupShape groupShape = pres.getSlides().get_Item(0).getShapes().
                        addGroupShape(svgImage, pFrame.getFrame().getX(), pFrame.getFrame().getY(),
                                pFrame.getFrame().getWidth(), pFrame.getFrame().getHeight());
                // ลบรูปภาพ SVG ต้นฉบับออกจากการนำเสนอ
                pres.getSlides().get_Item(0).getShapes().remove(pFrame);
            }
            pres.save(dataDir + "image_group.pptx", SaveFormat.Pptx);
        }
        finally
        {
            pres.dispose();
        }
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจกระบวนการแปลงวัตถุรูปภาพ SVG เป็นกลุ่มของรูปร่างภายในงานนำเสนอ PowerPoint โดยใช้ Java และ Aspose.Slides สำหรับไลบรารี Java ฟังก์ชันนี้เปิดโอกาสมากมายในการปรับปรุงการนำเสนอของคุณด้วยเนื้อหาแบบไดนามิก

## คำถามที่พบบ่อย

### ฉันสามารถแปลงรูปแบบรูปภาพอื่นๆ เป็นกลุ่มรูปร่างโดยใช้ Aspose.Slides ได้หรือไม่

ใช่ Aspose.Slides รองรับรูปแบบรูปภาพที่หลากหลาย ไม่ใช่แค่ SVG คุณสามารถแปลงรูปแบบเช่น PNG, JPEG และอื่นๆ เป็นกลุ่มของรูปร่างภายในงานนำเสนอ PowerPoint

### Aspose.Slides เหมาะสำหรับการนำเสนอ PowerPoint อัตโนมัติหรือไม่

อย่างแน่นอน! Aspose.Slides นำเสนอฟีเจอร์อันทรงพลังสำหรับการนำเสนอ PowerPoint โดยอัตโนมัติ ทำให้เป็นเครื่องมืออันมีค่าสำหรับงานต่างๆ เช่น การสร้าง การแก้ไข และการจัดการสไลด์โดยทางโปรแกรม

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides ต้องมีใบอนุญาตที่ถูกต้องสำหรับการใช้งานเชิงพาณิชย์ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose อย่างไรก็ตาม มีการทดลองใช้ฟรีเพื่อวัตถุประสงค์ในการประเมินผล

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของรูปร่างที่แปลงแล้วได้หรือไม่

แน่นอน! คุณสามารถปรับแต่งรูปลักษณ์ ขนาด และตำแหน่งของรูปร่างที่แปลงแล้วได้ตามความต้องการของคุณ Aspose.Slides มี API ที่ครอบคลุมสำหรับการจัดการรูปร่าง
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
