---
title: แปลงโดยไม่มีตัวเลือก XPS ใน Java Slides
linktitle: แปลงโดยไม่มีตัวเลือก XPS ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ XPS โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
weight: 33
url: /th/java/presentation-conversion/convert-without-xps-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## บทนำ แปลง PowerPoint เป็น XPS โดยไม่มีตัวเลือก XPS ใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร XPS (XML Paper Specification) โดยใช้ Aspose.Slides สำหรับ Java โดยไม่ต้องระบุตัวเลือก XPS ใดๆ เราจะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ด Java แก่คุณเพื่อให้บรรลุภารกิจนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณ คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเว็บไซต์ Java](https://downloads.aspose.com/slides/java).

2. สภาพแวดล้อมการพัฒนา Java: คุณควรตั้งค่าสภาพแวดล้อมการพัฒนา Java บนคอมพิวเตอร์ของคุณ

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ในโปรเจ็กต์ Java ของคุณ ให้นำเข้า Aspose.Slides ที่จำเป็นสำหรับคลาส Java ที่จุดเริ่มต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

ตอนนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น XPS แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไฟล์งานนำเสนอ PowerPoint ของคุณ:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

 ตรวจสอบให้แน่ใจว่าคุณเปลี่ยน`"Convert_XPS.pptx"` ด้วยชื่อจริงของไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 3: บันทึกเป็น XPS โดยไม่มีตัวเลือก XPS

ด้วย Aspose.Slides สำหรับ Java คุณสามารถบันทึกงานนำเสนอที่โหลดเป็นเอกสาร XPS ได้อย่างง่ายดายโดยไม่ต้องระบุตัวเลือก XPS ใด ๆ ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
try {
    // บันทึกการนำเสนอลงในเอกสาร XPS
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

 บล็อกโค้ดนี้จะบันทึกงานนำเสนอเป็นเอกสาร XPS พร้อมชื่อ`"XPS_Output_Without_XPSOption_out.xps"`- คุณสามารถเปลี่ยนชื่อไฟล์เอาต์พุตได้ตามต้องการ

## กรอกซอร์สโค้ดสำหรับการแปลงโดยไม่มีตัวเลือก XPS ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// บันทึกการนำเสนอลงในเอกสาร XPS
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

 ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นเอกสาร XPS โดยไม่ต้องระบุตัวเลือก XPS ใด ๆ โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งกระบวนการแปลงเพิ่มเติมได้โดยการสำรวจตัวเลือกที่ Aspose.Slides สำหรับ Java มอบให้ สำหรับคุณสมบัติขั้นสูงเพิ่มเติมและเอกสารเชิงลึก โปรดไปที่[Aspose.Slides สำหรับเอกสาร Java](https://docs.aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะระบุตัวเลือก XPS ขณะแปลงได้อย่างไร

 หากต้องการระบุตัวเลือก XPS ขณะแปลงงานนำเสนอ PowerPoint คุณสามารถใช้`XpsOptions` และตั้งค่าคุณสมบัติต่างๆ เช่น การบีบอัดรูปภาพ และการฝังแบบอักษร หากคุณมีข้อกำหนดเฉพาะสำหรับการแปลง XPS โปรดดูที่[Aspose.Slides สำหรับเอกสาร Java](https://docs.aspose.com/slides/java/) สำหรับรายละเอียดเพิ่มเติม

### มีตัวเลือกเพิ่มเติมสำหรับการบันทึกในรูปแบบอื่นหรือไม่?

 ใช่ Aspose.Slides สำหรับ Java มีรูปแบบเอาต์พุตที่หลากหลายนอกเหนือจาก XPS เช่น PDF, TIFF และ HTML คุณสามารถระบุรูปแบบเอาต์พุตที่ต้องการได้โดยการเปลี่ยน`SaveFormat` พารามิเตอร์เมื่อเรียก`save` วิธี. โปรดดูเอกสารประกอบสำหรับรายการรูปแบบที่รองรับทั้งหมด

### ฉันจะจัดการกับข้อยกเว้นระหว่างกระบวนการแปลงได้อย่างไร

 คุณสามารถใช้การจัดการข้อยกเว้นเพื่อจัดการกับข้อผิดพลาดใดๆ ที่อาจเกิดขึ้นระหว่างกระบวนการแปลงได้อย่างสง่างาม ตามที่แสดงในรหัสก`try` และ`finally` บล็อกถูกใช้เพื่อให้แน่ใจว่ามีการกำจัดทรัพยากรอย่างเหมาะสม แม้ว่าจะมีข้อยกเว้นเกิดขึ้นก็ตาม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
