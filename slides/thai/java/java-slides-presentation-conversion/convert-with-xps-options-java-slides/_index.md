---
title: แปลงด้วยตัวเลือก XPS ใน Java Slides
linktitle: แปลงด้วยตัวเลือก XPS ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ XPS ใน Java โดยใช้ Aspose.Slides ปรับแต่งตัวเลือกสำหรับกระบวนการแปลงที่ราบรื่น
weight: 34
url: /th/java/presentation-conversion/convert-with-xps-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการแปลงด้วยตัวเลือก XPS ใน Java Slides

ในโลกของการเขียนโปรแกรม Java การทำงานกับไฟล์การนำเสนอถือเป็นงานทั่วไป ไม่ว่าคุณจะสร้างรายงานแบบไดนามิกหรือสไลด์โชว์เชิงโต้ตอบ การมีเครื่องมือและไลบรารีที่เหมาะสมสามารถช่วยให้งานของคุณง่ายขึ้นอย่างมาก เครื่องมืออันทรงพลังอย่างหนึ่งคือ Aspose.Slides สำหรับ Java ซึ่งเป็น API ที่ช่วยให้คุณจัดการและแปลงงานนำเสนอ PowerPoint ได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มในโครงการของคุณ
- ไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการแปลงเป็นรูปแบบ XPS

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

 ในโปรเจ็กต์ Java ของคุณ ให้นำเข้าไลบรารีที่จำเป็นสำหรับ Aspose.Slides เพื่อให้ทำงานได้ ซึ่งรวมถึงการนำเข้าไฟล์`com.aspose.slides` แพ็คเกจเพื่อเข้าถึงคลาสและวิธีการ

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: ระบุไดเร็กทอรีเอกสาร

 กำหนดเส้นทางไปยังไดเร็กทอรีที่มีไฟล์งานนำเสนอของคุณอยู่ แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ของคุณ

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: โหลดการนำเสนอ

 สร้างอินสแตนซ์ของ`Presentation` ชั้นเรียนแล้วโหลดไฟล์งานนำเสนอ PowerPoint ที่คุณต้องการแปลง ในโค้ดที่ให้มา เราจะโหลดงานนำเสนอชื่อ "Convert_XPS_Options.pptx"

```java
Presentation pres = new Presentation(dataDir + "Convert_XPS_Options.pptx");
```

## ขั้นตอนที่ 4: ปรับแต่งตัวเลือกการแปลง

หากต้องการปรับแต่งกระบวนการแปลง คุณสามารถสร้างอินสแตนซ์ของ`XpsOptions` ระดับ. ในตัวอย่าง เราตั้งค่าตัวเลือกในการบันทึก metafiles เป็นภาพ PNG

```java
XpsOptions opts = new XpsOptions();
opts.setSaveMetafilesAsPng(true);
```

สำรวจตัวเลือกอื่นๆ ที่ให้บริการโดย Aspose.Slides ได้ตามสบาย เพื่อปรับแต่งการแปลงของคุณตามความต้องการของคุณ

## ขั้นตอนที่ 5: ทำการแปลง

 เมื่อคุณได้โหลดงานนำเสนอและปรับแต่งตัวเลือกการแปลงแล้ว ก็ถึงเวลาดำเนินการแปลงจริง ใช้`save` วิธีการของ`Presentation` คลาสเพื่อบันทึกการนำเสนอในรูปแบบ XPS

```java
pres.save(dataDir + "XPS_With_Options_out.xps", SaveFormat.Xps, opts);
```

## ขั้นตอนที่ 6: ทรัพยากรการล้างข้อมูล

 สุดท้ายนี้ อย่าลืมปล่อยทรัพยากรที่ได้รับการจัดสรรโดยการกำจัดทิ้ง`Presentation` วัตถุ.

```java
if (pres != null) pres.dispose();
```

## กรอกซอร์สโค้ดสำหรับการแปลงด้วยตัวเลือก XPS ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation pres = new Presentation(dataDir + "Convert_XPS_Options.pptx");
try
{
	// สร้างอินสแตนซ์คลาส TiffOptions
	XpsOptions opts = new XpsOptions();
	// บันทึก MetaFiles เป็น PNG
	opts.setSaveMetafilesAsPng(true);
	// บันทึกการนำเสนอลงในเอกสาร XPS
	pres.save(dataDir + "XPS_With_Options_out.xps", SaveFormat.Xps, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีแปลงงานนำเสนอ PowerPoint เป็นรูปแบบ XPS ใน Java ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ไลบรารีอันทรงพลังนี้ให้ความยืดหยุ่นในการปรับแต่งกระบวนการแปลงให้เหมาะกับความต้องการของคุณ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์ Aspose เยี่ยม[ที่นี่](https://releases.aspose.com/slides/java/) เพื่อเข้าถึงลิงค์ดาวน์โหลด

### มีข้อกำหนดสิทธิ์การใช้งานสำหรับการใช้ Aspose.Slides สำหรับ Java หรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีเชิงพาณิชย์ และคุณต้องมีใบอนุญาตที่ถูกต้องเพื่อใช้ในโปรเจ็กต์ของคุณ คุณสามารถขอรับใบอนุญาตได้จากเว็บไซต์ Aspose

### ฉันสามารถแปลงงานนำเสนอ PowerPoint เป็นรูปแบบอื่นนอกเหนือจาก XPS ได้หรือไม่

อย่างแน่นอน! Aspose.Slides สำหรับ Java รองรับรูปแบบการส่งออกที่หลากหลาย รวมถึง PDF, HTML และอื่นๆ คุณสามารถดูเอกสารประกอบเพื่อดูรายละเอียดเกี่ยวกับการแปลงเป็นรูปแบบต่างๆ ได้

### ฉันจะจัดการข้อยกเว้นขณะใช้ Aspose.Slides สำหรับ Java ได้อย่างไร

ในการจัดการกับข้อยกเว้น คุณสามารถใช้บล็อก try-catch รอบโค้ดของคุณเมื่อทำงานกับ Aspose.Slides โปรดดูเอกสารประกอบสำหรับแนวทางการจัดการข้อยกเว้นเฉพาะ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
