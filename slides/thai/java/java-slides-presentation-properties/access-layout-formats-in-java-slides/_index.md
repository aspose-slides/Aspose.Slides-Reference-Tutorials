---
title: เข้าถึงรูปแบบเค้าโครงใน Java Slides
linktitle: เข้าถึงรูปแบบเค้าโครงใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเข้าถึงและจัดการรูปแบบเค้าโครงใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับแต่งรูปร่างและสไตล์เส้นได้อย่างง่ายดายในงานนำเสนอ PowerPoint
weight: 10
url: /th/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เข้าถึงรูปแบบเค้าโครงใน Java Slides


## รู้เบื้องต้นเกี่ยวกับรูปแบบเค้าโครงการเข้าถึงใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีเข้าถึงและทำงานกับรูปแบบเค้าโครงใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API รูปแบบเค้าโครงช่วยให้คุณสามารถควบคุมลักษณะที่ปรากฏของรูปร่างและเส้นภายในสไลด์เค้าโครงของงานนำเสนอได้ เราจะกล่าวถึงวิธีการดึงข้อมูลรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างบนสไลด์เค้าโครง

## ข้อกำหนดเบื้องต้น

1. Aspose.Slides สำหรับไลบรารี Java
2. งานนำเสนอ PowerPoint (รูปแบบ PPTX) พร้อมสไลด์เค้าโครง

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

 ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีสไลด์เค้าโครง แทนที่`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงรูปแบบเค้าโครง

ตอนนี้ มาดูสไลด์เค้าโครงในงานนำเสนอและเข้าถึงรูปแบบการเติมและรูปแบบเส้นของรูปร่างบนสไลด์เค้าโครงแต่ละสไลด์

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // เข้าถึงรูปแบบการเติมของรูปร่าง
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // เข้าถึงรูปแบบเส้นของรูปร่าง
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

ในโค้ดด้านบน:

- เราวนซ้ำแต่ละสไลด์เค้าโครงโดยใช้`for` วนซ้ำ
- สำหรับแต่ละสไลด์เค้าโครง เราจะสร้างอาร์เรย์เพื่อจัดเก็บรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างบนสไลด์นั้น
-  เราใช้ซ้อนกัน`for` วนซ้ำเพื่อวนซ้ำรูปร่างบนสไลด์เค้าโครงและเรียกข้อมูลรูปแบบการเติมและเส้น

## ขั้นตอนที่ 3: ทำงานกับรูปแบบเค้าโครง

ตอนนี้เราได้เข้าถึงรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างบนสไลด์เค้าโครงแล้ว คุณสามารถดำเนินการต่างๆ กับรูปแบบเหล่านั้นได้ตามต้องการ ตัวอย่างเช่น คุณสามารถเปลี่ยนสีเติม ลักษณะเส้น หรือคุณสมบัติอื่นๆ ของรูปร่างได้

## กรอกซอร์สโค้ดสำหรับรูปแบบเค้าโครงการเข้าถึงใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีเข้าถึงและจัดการรูปแบบเค้าโครงใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API รูปแบบเค้าโครงเป็นสิ่งจำเป็นสำหรับการควบคุมลักษณะที่ปรากฏของรูปร่างและเส้นภายในเค้าโครงสไลด์ในงานนำเสนอ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีเติมของรูปร่างได้อย่างไร

 หากต้องการเปลี่ยนสีเติมของรูปร่าง คุณสามารถใช้`IFillFormat`วิธีการของวัตถุ นี่คือตัวอย่าง:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // ตั้งค่าประเภทการเติมเป็นสีทึบ
fillFormat.getSolidFillColor().setColor(Color.RED); // ตั้งค่าสีเติมเป็นสีแดง
```

### ฉันจะเปลี่ยนสไตล์เส้นของรูปร่างได้อย่างไร

 หากต้องการเปลี่ยนสไตล์เส้นของรูปร่าง คุณสามารถใช้`ILineFormat`วิธีการของวัตถุ นี่คือตัวอย่าง:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // ตั้งค่ารูปแบบเส้นเป็นเดี่ยว
lineFormat.setWidth(2.0); // ตั้งค่าความกว้างของเส้นเป็น 2.0 พอยต์
lineFormat.getSolidFillColor().setColor(Color.BLUE); // กำหนดสีของเส้นเป็นสีน้ำเงิน
```

### ฉันจะนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับรูปร่างบนสไลด์เค้าโครงได้อย่างไร

หากต้องการใช้การเปลี่ยนแปลงเหล่านี้กับรูปร่างเฉพาะบนสไลด์เลย์เอาต์ คุณสามารถเข้าถึงรูปร่างได้โดยใช้ดัชนีของรูปร่างนั้นในคอลเลกชั่นรูปร่างของสไลด์เลย์เอาต์ ตัวอย่างเช่น:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // เข้าถึงรูปร่างแรกบนสไลด์เค้าโครง
```

 จากนั้นคุณสามารถใช้`IFillFormat` และ`ILineFormat` วิธีการดังที่แสดงในคำตอบก่อนหน้าเพื่อปรับเปลี่ยนรูปแบบการเติมและเส้นของรูปร่าง
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
