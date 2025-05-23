---
"description": "เรียนรู้วิธีการเข้าถึงและจัดการรูปแบบเค้าโครงใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับแต่งรูปแบบรูปร่างและเส้นได้อย่างง่ายดายในงานนำเสนอ PowerPoint"
"linktitle": "เข้าถึงรูปแบบเค้าโครงใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เข้าถึงรูปแบบเค้าโครงใน Java Slides"
"url": "/th/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เข้าถึงรูปแบบเค้าโครงใน Java Slides


## บทนำเกี่ยวกับรูปแบบเค้าโครง Access ใน Java Slides

ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการเข้าถึงและทำงานกับรูปแบบเค้าโครงใน Java Slides โดยใช้ Aspose.Slides for Java API รูปแบบเค้าโครงช่วยให้คุณสามารถควบคุมลักษณะของรูปร่างและเส้นในสไลด์เค้าโครงของงานนำเสนอได้ เราจะกล่าวถึงวิธีเรียกค้นรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างในสไลด์เค้าโครง

## ข้อกำหนดเบื้องต้น

1. Aspose.Slides สำหรับไลบรารี Java
2. การนำเสนอ PowerPoint (รูปแบบ PPTX) พร้อมสไลด์เค้าโครง

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

ขั้นแรก เราต้องโหลดงานนำเสนอ PowerPoint ที่มีสไลด์เค้าโครง แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## ขั้นตอนที่ 2: เข้าถึงรูปแบบเค้าโครง

ตอนนี้ มาดูสไลด์เค้าโครงในงานนำเสนอและเข้าถึงรูปแบบการเติมและรูปแบบเส้นของรูปร่างบนสไลด์เค้าโครงแต่ละสไลด์กัน

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // เข้าถึงรูปแบบการกรอกของรูปร่าง
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // รูปแบบเส้นการเข้าถึงของรูปทรง
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

- เราทำซ้ำผ่านแต่ละสไลด์เค้าโครงโดยใช้ `for` ลูป
- สำหรับสไลด์เค้าโครงแต่ละสไลด์ เราสร้างอาร์เรย์เพื่อจัดเก็บรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างบนสไลด์นั้น
- เราใช้แบบซ้อนกัน `for` ลูปเพื่อวนซ้ำผ่านรูปร่างต่างๆ บนสไลด์เค้าโครงและดึงรูปแบบการเติมและเส้นของรูปร่างเหล่านั้น

## ขั้นตอนที่ 3: ทำงานกับรูปแบบเค้าโครง

ตอนนี้เราได้เข้าถึงรูปแบบการเติมและรูปแบบเส้นสำหรับรูปร่างบนสไลด์เค้าโครงแล้ว คุณสามารถดำเนินการต่างๆ กับรูปแบบเหล่านี้ได้ตามต้องการ ตัวอย่างเช่น คุณสามารถเปลี่ยนสีการเติม สไตล์เส้น หรือคุณสมบัติอื่นๆ ของรูปร่างได้

## โค้ดต้นฉบับที่สมบูรณ์สำหรับรูปแบบเค้าโครง Access ใน Java Slides

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

ในบทช่วยสอนนี้ เราจะอธิบายวิธีการเข้าถึงและจัดการรูปแบบเค้าโครงใน Java Slides โดยใช้ Aspose.Slides for Java API รูปแบบเค้าโครงมีความจำเป็นสำหรับการควบคุมลักษณะของรูปร่างและเส้นภายในสไลด์เค้าโครงในงานนำเสนอ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีเติมของรูปร่างได้อย่างไร?

หากต้องการเปลี่ยนสีเติมของรูปร่าง คุณสามารถใช้ `IFillFormat` วิธีการของวัตถุ นี่คือตัวอย่าง:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // ตั้งค่าประเภทการเติมเป็นสีทึบ
fillFormat.getSolidFillColor().setColor(Color.RED); // ตั้งค่าสีเติมเป็นสีแดง
```

### ฉันจะเปลี่ยนรูปแบบเส้นของรูปร่างได้อย่างไร?

หากต้องการเปลี่ยนรูปแบบเส้นของรูปร่าง คุณสามารถใช้ `ILineFormat` วิธีการของวัตถุ นี่คือตัวอย่าง:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // ตั้งค่ารูปแบบเส้นเป็นแบบเส้นเดียว
lineFormat.setWidth(2.0); // ตั้งค่าความกว้างเส้นเป็น 2.0 จุด
lineFormat.getSolidFillColor().setColor(Color.BLUE); // ตั้งค่าสีเส้นเป็นสีน้ำเงิน
```

### ฉันจะนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับรูปร่างบนสไลด์เค้าโครงได้อย่างไร

หากต้องการนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับรูปร่างเฉพาะบนสไลด์เค้าโครง คุณสามารถเข้าถึงรูปร่างนั้นได้โดยใช้ดัชนีในคอลเล็กชันรูปร่างของสไลด์เค้าโครง ตัวอย่างเช่น:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // เข้าถึงรูปร่างแรกบนสไลด์เค้าโครง
```

แล้วคุณก็สามารถใช้ `IFillFormat` และ `ILineFormat` วิธีการตามที่แสดงในคำตอบก่อนหน้าเพื่อปรับเปลี่ยนรูปแบบการเติมและเส้นของรูปร่าง

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}