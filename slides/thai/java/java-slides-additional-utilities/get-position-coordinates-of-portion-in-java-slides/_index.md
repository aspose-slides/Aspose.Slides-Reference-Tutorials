---
"description": "เรียนรู้การดึงพิกัดส่วนข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ควบคุมการวางข้อความในงานนำเสนอ PowerPoint ได้อย่างแม่นยำ"
"linktitle": "รับพิกัดตำแหน่งของส่วนใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รับพิกัดตำแหน่งของส่วนใน Java Slides"
"url": "/th/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รับพิกัดตำแหน่งของส่วนใน Java Slides


## การแนะนำการรับพิกัดตำแหน่งของส่วนต่างๆ ในสไลด์ Java

ในคู่มือฉบับสมบูรณ์นี้ เราจะมาสำรวจวิธีการดึงพิกัดตำแหน่งของส่วนต่างๆ ในสไลด์ Java โดยใช้ Aspose.Slides for Java API คุณจะได้เรียนรู้วิธีการเข้าถึงและจัดการส่วนข้อความในสไลด์ รวมถึงดึงพิกัด X และ Y ของข้อความเหล่านั้น บทช่วยสอนแบบทีละขั้นตอนนี้ประกอบด้วยตัวอย่างโค้ดต้นฉบับและข้อมูลเชิงลึกอันมีค่าที่จะช่วยให้คุณเชี่ยวชาญในงานนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่จะเจาะลึกการใช้งานจริง ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- ดาวน์โหลดและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java
- Java Integrated Development Environment (IDE) ที่คุณเลือก

ตอนนี้เรามาเริ่มการใช้งานกันเลย

## ขั้นตอนที่ 1: การตั้งค่าโครงการของคุณ

ก่อนที่เราจะสามารถใช้งาน Aspose.Slides สำหรับ Java ได้ เราต้องตั้งค่าโปรเจ็กต์ Java และกำหนดค่าไลบรารีเสียก่อน ปฏิบัติตามขั้นตอนเหล่านี้เพื่อเตรียมโปรเจ็กต์ของคุณให้พร้อม:

1. สร้างโครงการ Java ใหม่ใน IDE ของคุณ
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในส่วนที่ต้องมีของโปรเจ็กต์ของคุณ
3. นำเข้าคลาส Aspose.Slides ที่จำเป็นไว้ในจุดเริ่มต้นของไฟล์ Java ของคุณ

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## ขั้นตอนที่ 2: การโหลดงานนำเสนอ

ในขั้นตอนนี้เราจะโหลดงานนำเสนอ PowerPoint ที่มีสไลด์ที่เราต้องการใช้แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## ขั้นตอนที่ 3: การเข้าถึงส่วนข้อความและพิกัด

ตอนนี้เราจะเข้าถึงส่วนข้อความภายในสไลด์และค้นหาพิกัด X และ Y ของข้อความเหล่านั้น เราจะวนซ้ำผ่านย่อหน้าและส่วนต่างๆ เพื่อให้บรรลุสิ่งนี้ นี่คือตัวอย่างโค้ด:

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

โค้ดนี้จะดึงค่าพิกัด X และ Y ของข้อความแต่ละส่วนในสไลด์ที่ระบุ คุณสามารถปรับเปลี่ยนให้เหมาะกับความต้องการเฉพาะของคุณได้

## โค้ดต้นฉบับที่สมบูรณ์สำหรับรับพิกัดตำแหน่งของส่วนต่างๆ ใน Java Slides

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

ในบทช่วยสอนนี้ เราได้กล่าวถึงวิธีการรับพิกัดตำแหน่งของส่วนข้อความในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API ความรู้ดังกล่าวอาจมีประโยชน์อย่างยิ่งเมื่อคุณต้องการควบคุมตำแหน่งขององค์ประกอบข้อความในงานนำเสนอ PowerPoint ของคุณอย่างแม่นยำ

## คำถามที่พบบ่อย

### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ Java ได้จากเว็บไซต์โดยใช้ลิงก์ต่อไปนี้: [ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/)

### ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

เอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java มีอยู่ได้ที่: [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/)

### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์ของฉันได้หรือไม่

ใช่ สามารถใช้ Aspose.Slides สำหรับ Java ในโปรเจ็กต์เชิงพาณิชย์ได้ อย่างไรก็ตาม โปรดตรวจสอบเงื่อนไขการอนุญาตสิทธิ์ที่ Aspose ให้ไว้

### Aspose.Slides สำหรับ Java เข้ากันได้กับรูปแบบไฟล์ PowerPoint ที่แตกต่างกันหรือไม่

ใช่ Aspose.Slides สำหรับ Java รองรับรูปแบบไฟล์ PowerPoint ต่างๆ รวมถึง PPTX, PPT และอื่นๆ อีกมากมาย

### ฉันจะได้รับการสนับสนุนหรือความช่วยเหลือเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

คุณสามารถเข้าถึงการสนับสนุนและทรัพยากรเพิ่มเติมได้บนเว็บไซต์ Aspose ซึ่งมีฟอรัม เอกสารประกอบ และตัวเลือกการสนับสนุนระดับพรีเมียมสำหรับผู้ใช้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}