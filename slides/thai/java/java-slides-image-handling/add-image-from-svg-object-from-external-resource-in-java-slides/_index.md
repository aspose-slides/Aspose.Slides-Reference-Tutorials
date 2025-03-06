---
title: เพิ่มรูปภาพจากวัตถุ SVG จากทรัพยากรภายนอกใน Java Slides
linktitle: เพิ่มรูปภาพจากวัตถุ SVG จากทรัพยากรภายนอกใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มรูปภาพ SVG แบบเวกเตอร์จากแหล่งข้อมูลภายนอกไปยังสไลด์ Java โดยใช้ Aspose.Slides สร้างงานนำเสนอที่น่าทึ่งด้วยภาพคุณภาพสูง
weight: 12
url: /th/java/image-handling/add-image-from-svg-object-from-external-resource-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มรูปภาพจากวัตถุ SVG จากทรัพยากรภายนอกใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีเพิ่มรูปภาพจากออบเจ็กต์ SVG (Scalable Vector Graphics) จากทรัพยากรภายนอกไปยังสไลด์ Java ของคุณโดยใช้ Aspose.Slides นี่อาจเป็นคุณสมบัติที่มีค่าเมื่อคุณต้องการรวมภาพแบบเวกเตอร์ในงานนำเสนอของคุณ เพื่อให้มั่นใจว่าได้ภาพคุณภาพสูง มาดำดิ่งสู่คำแนะนำทีละขั้นตอน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
- Aspose.Slides สำหรับไลบรารี Java
- ไฟล์ภาพ SVG (เช่น "image1.svg")

## การจัดตั้งโครงการ

ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนา Java ของคุณได้รับการตั้งค่าและพร้อมสำหรับโปรเจ็กต์นี้ คุณสามารถใช้ Integrated Development Environment (IDE) ที่คุณต้องการสำหรับ Java

## ขั้นตอนที่ 1: การเพิ่ม Aspose.Slides ในโครงการของคุณ

 หากต้องการเพิ่ม Aspose.Slides ให้กับโปรเจ็กต์ของคุณ คุณสามารถใช้ Maven หรือดาวน์โหลดไลบรารีด้วยตนเองได้ อ้างอิงเอกสารประกอบได้ที่[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำโดยละเอียดเกี่ยวกับวิธีการรวมไว้ในโครงการของคุณ

## ขั้นตอนที่ 2: สร้างงานนำเสนอ

เริ่มต้นด้วยการสร้างงานนำเสนอโดยใช้ Aspose.Slides:

```java
String dataDir = "Your Document Directory";
String outPptxPath = dataDir + "presentation_external.pptx";
Presentation p = new Presentation();
```

 ตรวจสอบให้แน่ใจว่าคุณเปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 3: กำลังโหลดรูปภาพ SVG

เราจำเป็นต้องโหลดอิมเมจ SVG จากแหล่งข้อมูลภายนอก ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
```

 ในโค้ดนี้ เราอ่านเนื้อหา SVG จากไฟล์ "image1.svg" และสร้างไฟล์`ISvgImage` วัตถุ.

## ขั้นตอนที่ 4: การเพิ่มรูปภาพ SVG ลงในสไลด์

ตอนนี้ มาเพิ่มรูปภาพ SVG ลงในสไลด์กันดีกว่า:

```java
IPPImage ppImage = p.getImages().addImage(svgImage);
p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
```

เราเพิ่มรูปภาพ SVG เป็นกรอบรูปให้กับสไลด์แรกในงานนำเสนอ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอ:

```java
p.save(outPptxPath, SaveFormat.Pptx);
```

รหัสนี้จะบันทึกการนำเสนอเป็น "presentation_external.pptx" ในไดเร็กทอรีที่ระบุ

## กรอกซอร์สโค้ดสำหรับเพิ่มรูปภาพจากวัตถุ SVG จากทรัพยากรภายนอกใน Java Slides

```java
        // เส้นทางไปยังไดเร็กทอรีเอกสาร
        String dataDir = "Your Document Directory";
        String outPptxPath = dataDir + "presentation_external.pptx";
        Presentation p = new Presentation();
        try
        {
            String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
            ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
            IPPImage ppImage = p.getImages().addImage(svgImage);
            p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
            p.save(outPptxPath, SaveFormat.Pptx);
        }
        finally
        {
            if (p != null) p.dispose();
        }
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีเพิ่มรูปภาพจากวัตถุ SVG จากทรัพยากรภายนอกไปยังสไลด์ Java โดยใช้ Aspose.Slides คุณลักษณะนี้ช่วยให้คุณสามารถรวมภาพเวกเตอร์คุณภาพสูงในงานนำเสนอของคุณ ซึ่งจะช่วยเพิ่มความดึงดูดใจให้กับภาพเหล่านั้น

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งตำแหน่งของรูปภาพ SVG ที่เพิ่มบนสไลด์ได้อย่างไร

 คุณสามารถปรับตำแหน่งของรูปภาพ SVG ได้โดยการแก้ไขพิกัดใน`addPictureFrame` วิธี. พารามิเตอร์`(0, 0)` แสดงถึงพิกัด X และ Y ของมุมซ้ายบนของกรอบภาพ

### ฉันสามารถใช้วิธีนี้เพื่อเพิ่มรูปภาพ SVG หลายรูปลงในสไลด์เดียวได้หรือไม่

ได้ คุณสามารถเพิ่มรูปภาพ SVG หลายรูปลงในสไลด์เดียวได้โดยทำขั้นตอนนี้ซ้ำสำหรับแต่ละรูปภาพและปรับตำแหน่งตามลำดับ

### รูปแบบใดบ้างที่รองรับทรัพยากร SVG ภายนอก

Aspose.Slides สำหรับ Java รองรับรูปแบบ SVG หลากหลาย แต่ขอแนะนำให้ตรวจสอบให้แน่ใจว่าไฟล์ SVG ของคุณเข้ากันได้กับไลบรารีเพื่อให้ได้ผลลัพธ์ที่ดีที่สุด

### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java เข้ากันได้กับ Java เวอร์ชันล่าสุด ตรวจสอบให้แน่ใจว่าใช้ไลบรารีเวอร์ชันที่เข้ากันได้สำหรับสภาพแวดล้อม Java ของคุณ

### ฉันสามารถใช้ภาพเคลื่อนไหวกับรูปภาพ SVG ที่เพิ่มลงในสไลด์ได้หรือไม่

ใช่ คุณสามารถใช้ภาพเคลื่อนไหวกับภาพ SVG ในสไลด์ของคุณโดยใช้ Aspose.Slides เพื่อสร้างงานนำเสนอแบบไดนามิก
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
