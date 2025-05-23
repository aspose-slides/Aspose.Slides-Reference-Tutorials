---
"description": "เรียนรู้วิธีการตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ในแผนภูมิ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "การตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ใน Java Slides"
"url": "/th/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ใน Java Slides


## บทนำเกี่ยวกับการตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ใน Java Slides

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีการตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ในแผนภูมิ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้คุณสร้าง จัดการ และจัดการการนำเสนอ PowerPoint ได้ด้วยโปรแกรม

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

1. Aspose.Slides สำหรับไลบรารี Java (สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).
2. การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: สร้างการนำเสนอ PowerPoint

ขั้นแรก เราต้องสร้างการนำเสนอ PowerPoint โดยจะเพิ่มแผนภูมิเข้าไป ตรวจสอบให้แน่ใจว่าคุณได้นำเข้าคลาส Aspose.Slides ที่จำเป็นแล้ว

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ตอนนี้เรามาเพิ่มแผนภูมิลงในสไลด์ PowerPoint กัน เราจะใช้แผนภูมิพื้นที่ในตัวอย่างนี้

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## ขั้นตอนที่ 3: เตรียมข้อมูลแผนภูมิ

เราจะตั้งค่าข้อมูลแผนภูมิและหมวดหมู่ ในตัวอย่างนี้ เราจะใช้หมวดหมู่วันที่

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// การเพิ่มหมวดหมู่วันที่
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// การเพิ่มชุดข้อมูล
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## ขั้นตอนที่ 4: ปรับแต่งแกนหมวดหมู่
ตอนนี้ มาปรับแต่งแกนหมวดหมู่เพื่อแสดงวันที่ในรูปแบบเฉพาะ (เช่น yyyy) กัน

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอ PowerPoint

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้ตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ในแผนภูมิ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับการตั้งค่ารูปแบบวันที่สำหรับแกนหมวดหมู่ใน Java Slides

```java
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##บทสรุป

คุณได้ปรับแต่งรูปแบบวันที่สำหรับแกนหมวดหมู่ในแผนภูมิ Java Slides สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java วิธีนี้ช่วยให้คุณแสดงค่าวันที่ในรูปแบบที่ต้องการบนแผนภูมิของคุณได้ โปรดอย่าลังเลที่จะสำรวจตัวเลือกการปรับแต่งเพิ่มเติมตามความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนรูปแบบวันที่สำหรับแกนหมวดหมู่ได้อย่างไร

หากต้องการเปลี่ยนรูปแบบวันที่สำหรับแกนหมวดหมู่ ให้ใช้ `setNumberFormat` วิธีการบนแกนหมวดหมู่และระบุรูปแบบรูปแบบวันที่ที่ต้องการ เช่น "yyyy-MM-dd" หรือ "MM/yyyy" ตรวจสอบให้แน่ใจว่าได้ตั้งค่า `setNumberFormatLinkedToSource(false)` เพื่อแทนที่รูปแบบเริ่มต้น

### ฉันสามารถใช้รูปแบบวันที่ที่แตกต่างกันสำหรับแผนภูมิต่างๆ ในงานนำเสนอเดียวกันได้หรือไม่

ใช่ คุณสามารถตั้งค่ารูปแบบวันที่ที่แตกต่างกันสำหรับแกนหมวดหมู่ในแผนภูมิต่างๆ ภายในงานนำเสนอเดียวกันได้ เพียงปรับแต่งแกนหมวดหมู่สำหรับแต่ละแผนภูมิตามต้องการ

### ฉันจะเพิ่มจุดข้อมูลเพิ่มเติมลงในแผนภูมิได้อย่างไร

หากต้องการเพิ่มจุดข้อมูลเพิ่มเติมลงในแผนภูมิ ให้ใช้ `getDataPoints().addDataPointForLineSeries` วิธีการบนชุดข้อมูลและให้ค่าข้อมูล

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}