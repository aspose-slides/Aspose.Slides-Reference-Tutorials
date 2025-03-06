---
title: รับพิกัดตำแหน่งของส่วนใน Java Slides
linktitle: รับพิกัดตำแหน่งของส่วนใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีดึงพิกัดส่วนข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ควบคุมตำแหน่งข้อความในงานนำเสนอ PowerPoint ได้อย่างแม่นยำ
weight: 12
url: /th/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับพิกัดตำแหน่งของส่วนใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการรับพิกัดตำแหน่งของส่วนใน Java Slides

ในคู่มือที่ครอบคลุมนี้ เราจะสำรวจวิธีดึงข้อมูลพิกัดตำแหน่งของส่วนภายในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API คุณจะได้เรียนรู้วิธีการเข้าถึงและจัดการส่วนข้อความในสไลด์และแยกพิกัด X และ Y บทช่วยสอนทีละขั้นตอนนี้ประกอบด้วยตัวอย่างซอร์สโค้ดและข้อมูลเชิงลึกอันมีค่าเพื่อช่วยให้คุณเชี่ยวชาญงานนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเรื่องการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและกำหนดค่า
- Java Integrated Development Environment (IDE) ที่คุณเลือก

ตอนนี้เรามาเริ่มต้นใช้งานกันดีกว่า

## ขั้นตอนที่ 1: การตั้งค่าโครงการของคุณ

ก่อนที่เราจะสามารถทำงานกับ Aspose.Slides สำหรับ Java ได้ เราจำเป็นต้องตั้งค่าโปรเจ็กต์ Java และกำหนดค่าไลบรารีก่อน ทำตามขั้นตอนเหล่านี้เพื่อเตรียมโครงการของคุณให้พร้อม:

1. สร้างโครงการ Java ใหม่ใน IDE ของคุณ
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับการขึ้นต่อกันของโปรเจ็กต์ของคุณ
3. นำเข้าคลาส Aspose.Slides ที่จำเป็นที่จุดเริ่มต้นของไฟล์ Java ของคุณ

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## ขั้นตอนที่ 2: กำลังโหลดการนำเสนอ

 ในขั้นตอนนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่มีสไลด์ที่เราต้องการใช้งาน แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## ขั้นตอนที่ 3: การเข้าถึงส่วนข้อความและพิกัด

ตอนนี้ เราจะเข้าถึงส่วนข้อความภายในสไลด์และดึงข้อมูลพิกัด X และ Y เราจะทำซ้ำตามย่อหน้าและส่วนต่างๆ เพื่อให้บรรลุเป้าหมายนี้ นี่คือข้อมูลโค้ด:

```java
try
{
    IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
    ITextFrame textFrame = shape.getTextFrame();
    for (IParagraph paragraph : textFrame.getParagraphs())
    {
        for (IPortion portion : paragraph.getPortions())
        {
            Point2D.Float point = portion.getCoordinates();
            System.out.println("Coordinates X =" + point.getX() + " Coordinates Y =" + point.getY());
        }
    }
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

รหัสนี้จะดึงพิกัด X และ Y สำหรับแต่ละส่วนของข้อความในสไลด์ที่ระบุ คุณสามารถปรับเปลี่ยนให้เหมาะกับความต้องการเฉพาะของคุณได้

## กรอกซอร์สโค้ดเพื่อรับพิกัดตำแหน่งของส่วนใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	for (IParagraph paragraph : textFrame.getParagraphs())
	{
		for (IPortion portion : paragraph.getPortions())
		{
			Point2D.Float point = portion.getCoordinates();
			System.out.println("Corrdinates X =" + point.getX() + " Corrdinates Y =" + point.getY());
		}
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการรับพิกัดตำแหน่งของส่วนข้อความภายในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ความรู้นี้จะมีประโยชน์อย่างยิ่งเมื่อคุณต้องการการควบคุมการจัดวางองค์ประกอบข้อความในงานนำเสนอ PowerPoint ของคุณอย่างแม่นยำ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์โดยใช้ลิงก์ต่อไปนี้:[ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

### ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 เอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java มีอยู่ที่:[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/)

### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์ของฉันได้หรือไม่

ได้ Aspose.Slides สำหรับ Java สามารถใช้ในโครงการเชิงพาณิชย์ได้ อย่างไรก็ตาม โปรดตรวจสอบข้อกำหนดสิทธิ์การใช้งานที่ได้รับจาก Aspose

### Aspose.Slides สำหรับ Java เข้ากันได้กับรูปแบบไฟล์ PowerPoint ที่แตกต่างกันหรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint หลากหลาย รวมถึง PPTX, PPT และอื่นๆ

### ฉันจะรับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถเข้าถึงการสนับสนุนและทรัพยากรเพิ่มเติมได้จากเว็บไซต์ Aspose มีฟอรัม เอกสาร และตัวเลือกการสนับสนุนระดับพรีเมียมสำหรับผู้ใช้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
