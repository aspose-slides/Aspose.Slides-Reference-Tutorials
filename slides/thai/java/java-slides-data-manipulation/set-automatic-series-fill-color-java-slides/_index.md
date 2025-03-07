---
title: ตั้งค่าสีเติมซีรี่ส์อัตโนมัติใน Java Slides
linktitle: ตั้งค่าสีเติมซีรี่ส์อัตโนมัติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าสีเติมซีรีส์อัตโนมัติใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการนำเสนอแบบไดนามิก
weight: 14
url: /th/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าสีเติมซีรี่ส์อัตโนมัติใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าสีเติมซีรี่ส์อัตโนมัติใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่าสีเติมชุดข้อมูลอัตโนมัติใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพซึ่งช่วยให้คุณสามารถสร้าง จัดการ และจัดการงานนำเสนอ PowerPoint โดยทางโปรแกรม ในตอนท้ายของคู่มือนี้ คุณจะสามารถสร้างแผนภูมิและตั้งค่าสีเติมชุดอัตโนมัติได้อย่างง่ายดาย

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
-  เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

ตอนนี้เรามีโครงร่างเรียบร้อยแล้ว เรามาเริ่มด้วยคำแนะนำทีละขั้นตอนกัน

## ขั้นตอนที่ 1: ข้อมูลเบื้องต้นเกี่ยวกับ Aspose.Slides สำหรับ Java

Aspose.Slides สำหรับ Java คือ Java API ที่ช่วยให้นักพัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint โดยมีคุณสมบัติที่หลากหลาย รวมถึงการสร้าง การแก้ไข และการจัดการสไลด์ แผนภูมิ รูปร่าง และอื่นๆ

## ขั้นตอนที่ 2: การตั้งค่าโครงการ Java ของคุณ

ก่อนที่เราจะเริ่มเขียนโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java ใน Integrated Development Environment (IDE) ที่คุณต้องการ ตรวจสอบให้แน่ใจว่าได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 3: การสร้างงานนำเสนอ PowerPoint

ในการเริ่มต้น ให้สร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ข้อมูลโค้ดต่อไปนี้:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางที่คุณต้องการบันทึกงานนำเสนอ

## ขั้นตอนที่ 4: การเพิ่มแผนภูมิในการนำเสนอ

ต่อไป ให้เพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในงานนำเสนอ เราจะใช้รหัสต่อไปนี้เพื่อทำสิ่งนี้ให้สำเร็จ:

```java
// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

รหัสนี้สร้างแผนภูมิคอลัมน์แบบกลุ่มบนสไลด์แรกของงานนำเสนอ

## ขั้นตอนที่ 5: การตั้งค่าสีเติมซีรี่ส์อัตโนมัติ

มาถึงส่วนสำคัญแล้ว—การตั้งค่าสีเติมชุดข้อมูลอัตโนมัติ เราจะวนซ้ำชุดข้อมูลของแผนภูมิและตั้งค่ารูปแบบการเติมเป็นอัตโนมัติ:

```java
// กำลังตั้งค่ารูปแบบการเติมซีรี่ส์เป็นอัตโนมัติ
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

รหัสนี้ช่วยให้แน่ใจว่าสีเติมของซีรี่ส์ถูกตั้งค่าเป็นอัตโนมัติ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

หากต้องการบันทึกการนำเสนอ ให้ใช้โค้ดต่อไปนี้:

```java
// เขียนไฟล์การนำเสนอลงดิสก์
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 แทนที่`"AutoFillSeries_out.pptx"` พร้อมชื่อไฟล์ที่ต้องการ

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับตั้งค่าสีเติมซีรี่ส์อัตโนมัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// การสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// กำลังตั้งค่ารูปแบบการเติมซีรี่ส์เป็นอัตโนมัติ
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// เขียนไฟล์การนำเสนอลงดิสก์
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ยินดีด้วย! คุณได้ตั้งค่าสีเติมชุดข้อมูลอัตโนมัติใน Java Slide โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างงานนำเสนอ PowerPoint แบบไดนามิกและน่าดึงดูดสายตาในแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิเป็นสไตล์อื่นได้อย่างไร

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่`ChartType.ClusteredColumn` ด้วยประเภทกราฟที่ต้องการ เช่น`ChartType.Line` หรือ`ChartType.Pie`.

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิเพิ่มเติมได้หรือไม่

ได้ คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการปรับเปลี่ยนคุณสมบัติต่างๆ ของแผนภูมิ เช่น สี แบบอักษร และป้ายกำกับ

### Aspose.Slides สำหรับ Java เหมาะสำหรับใช้ในเชิงพาณิชย์หรือไม่

ใช่ Aspose.Slides สำหรับ Java สามารถใช้กับทั้งโปรเจ็กต์ส่วนตัวและเชิงพาณิชย์ คุณสามารถดูข้อกำหนดสิทธิ์การใช้งานเพื่อดูรายละเอียดเพิ่มเติมได้

### มีคุณสมบัติอื่นใดอีกที่ Aspose.Slides สำหรับ Java มีให้หรือไม่

ใช่ Aspose.Slides สำหรับ Java นำเสนอคุณสมบัติที่หลากหลาย รวมถึงการจัดการสไลด์ การจัดรูปแบบข้อความ และการรองรับภาพเคลื่อนไหว

### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและเอกสารประกอบได้จากที่ไหน?

 คุณสามารถเข้าถึงเอกสารที่ครอบคลุมสำหรับ Aspose.Slides สำหรับ Java ได้ที่[ที่นี่](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
