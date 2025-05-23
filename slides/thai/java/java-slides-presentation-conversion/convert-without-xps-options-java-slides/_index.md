---
"description": "เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ XPS โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "แปลงโดยไม่ใช้ตัวเลือก XPS ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แปลงโดยไม่ใช้ตัวเลือก XPS ใน Java Slides"
"url": "/th/java/presentation-conversion/convert-without-xps-options-java-slides/"
"weight": 33
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แปลงโดยไม่ใช้ตัวเลือก XPS ใน Java Slides


## บทนำการแปลง PowerPoint เป็น XPS โดยไม่ต้องใช้ตัวเลือก XPS ใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร XPS (XML Paper Specification) โดยใช้ Aspose.Slides สำหรับ Java โดยไม่ต้องระบุตัวเลือก XPS ใดๆ เราจะให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับ Java แก่คุณเพื่อให้บรรลุภารกิจนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. Aspose.Slides สำหรับ Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [Aspose.Slides สำหรับเว็บไซต์ Java](https://downloads-aspose.com/slides/java).

2. สภาพแวดล้อมการพัฒนา Java: คุณควรมีการตั้งค่าสภาพแวดล้อมการพัฒนา Java บนคอมพิวเตอร์ของคุณ

## ขั้นตอนที่ 1: นำเข้า Aspose.Slides สำหรับ Java

ในโปรเจ็กต์ Java ของคุณ ให้นำเข้า Aspose.Slides ที่จำเป็นสำหรับคลาส Java ไปที่จุดเริ่มต้นของไฟล์ Java ของคุณ:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ PowerPoint

ตอนนี้เราจะโหลดงานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็น XPS แทนที่ `"Your Document Directory"` โดยมีเส้นทางจริงไปยังไฟล์การนำเสนอ PowerPoint ของคุณ:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

ให้แน่ใจว่าคุณเปลี่ยน `"Convert_XPS.pptx"` ด้วยชื่อจริงของไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 3: บันทึกเป็น XPS โดยไม่มีตัวเลือก XPS

ด้วย Aspose.Slides สำหรับ Java คุณสามารถบันทึกงานนำเสนอที่โหลดเป็นเอกสาร XPS ได้อย่างง่ายดายโดยไม่ต้องระบุตัวเลือก XPS ใดๆ คุณสามารถทำได้ดังนี้:

```java
try {
    // บันทึกการนำเสนอลงในเอกสาร XPS
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

บล็อกโค้ดนี้จะบันทึกการนำเสนอเป็นเอกสาร XPS ที่มีชื่อ `"XPS_Output_Without_XPSOption_out.xps"`คุณสามารถเปลี่ยนชื่อไฟล์เอาท์พุตได้ตามต้องการ

## โค้ดต้นฉบับสมบูรณ์สำหรับการแปลงโดยไม่มีตัวเลือก XPS ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของวัตถุการนำเสนอที่แสดงไฟล์การนำเสนอ
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการแปลงงานนำเสนอ PowerPoint เป็นเอกสาร XPS โดยไม่ต้องระบุตัวเลือก XPS ใดๆ โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งกระบวนการแปลงเพิ่มเติมได้โดยสำรวจตัวเลือกที่ Aspose.Slides สำหรับ Java ให้ไว้ สำหรับคุณลักษณะขั้นสูงเพิ่มเติมและเอกสารประกอบแบบเจาะลึก โปรดไปที่ [เอกสาร Aspose.Slides สำหรับ Java](https://docs-aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะระบุตัวเลือก XPS ขณะแปลงได้อย่างไร

หากต้องการระบุตัวเลือก XPS ในขณะแปลงงานนำเสนอ PowerPoint คุณสามารถใช้ `XpsOptions` คลาสและกำหนดคุณสมบัติต่างๆ เช่น การบีบอัดรูปภาพและการฝังแบบอักษร หากคุณมีข้อกำหนดเฉพาะสำหรับการแปลง XPS โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ Java](https://docs.aspose.com/slides/java/) สำหรับรายละเอียดเพิ่มเติม

### มีตัวเลือกเพิ่มเติมสำหรับการบันทึกในรูปแบบอื่นหรือไม่

ใช่ Aspose.Slides สำหรับ Java มีรูปแบบเอาต์พุตหลากหลายนอกเหนือจาก XPS เช่น PDF, TIFF และ HTML คุณสามารถระบุรูปแบบเอาต์พุตที่ต้องการได้โดยการเปลี่ยนแปลง `SaveFormat` พารามิเตอร์เมื่อเรียกใช้งาน `save` วิธีการ โปรดดูเอกสารประกอบเพื่อดูรายการรูปแบบที่รองรับทั้งหมด

### ฉันจะจัดการข้อยกเว้นในระหว่างกระบวนการแปลงได้อย่างไร

คุณสามารถนำการจัดการข้อยกเว้นมาใช้เพื่อจัดการข้อผิดพลาดที่อาจเกิดขึ้นระหว่างกระบวนการแปลงได้อย่างเหมาะสม ดังที่แสดงในโค้ด `try` และ `finally` บล็อกถูกใช้เพื่อให้แน่ใจว่ามีการกำจัดทรัพยากรอย่างเหมาะสมแม้ว่าจะเกิดข้อยกเว้นก็ตาม

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}