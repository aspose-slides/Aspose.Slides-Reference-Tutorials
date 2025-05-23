---
"description": "เรียนรู้วิธีตั้งค่าคำอธิบายภาพสำหรับป้ายข้อมูลใน Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "การตั้งค่าคำอธิบายภาพสำหรับป้ายข้อมูลใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่าคำอธิบายภาพสำหรับป้ายข้อมูลใน Java Slides"
"url": "/th/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าคำอธิบายภาพสำหรับป้ายข้อมูลใน Java Slides


## บทนำสู่การตั้งค่าคำอธิบายภาพสำหรับป้ายข้อมูลใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีตั้งค่าคำอธิบายประกอบสำหรับป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำอธิบายประกอบอาจมีประโยชน์ในการเน้นจุดข้อมูลเฉพาะในแผนภูมิของคุณ เราจะอธิบายโค้ดทีละขั้นตอนและให้โค้ดต้นฉบับที่จำเป็น

## ข้อกำหนดเบื้องต้น

- คุณควรติดตั้ง Aspose.Slides สำหรับ Java
- สร้างโครงการ Java และเพิ่มไลบรารี Aspose.Slides ลงในโครงการของคุณ

## ขั้นตอนที่ 1: สร้างการนำเสนอและเพิ่มแผนภูมิ

ขั้นแรก เราต้องสร้างงานนำเสนอและเพิ่มแผนภูมิลงในสไลด์ อย่าลืมแทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ขั้นตอนที่ 2: กำหนดค่าแผนภูมิ

ต่อไปเราจะกำหนดค่าแผนภูมิโดยตั้งค่าคุณสมบัติ เช่น ตำนาน ชุด และหมวดหมู่

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// การกำหนดค่าซีรีย์และหมวดหมู่ (สามารถปรับเปลี่ยนจำนวนซีรีย์และหมวดหมู่ได้)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // เพิ่มจุดข้อมูลที่นี่
        // -
        i++;
    }
    categoryIndex++;
}
```

## ขั้นตอนที่ 3: ปรับแต่งป้ายข้อมูล

ขณะนี้ เราจะปรับแต่งป้ายข้อมูล รวมถึงการตั้งค่าคำอธิบายภาพสำหรับชุดสุดท้าย

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // ปรับแต่งการจัดรูปแบบจุดข้อมูล (เติม, เส้น ฯลฯ)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // ปรับแต่งการจัดรูปแบบฉลาก (แบบอักษร, เติม ฯลฯ)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // เปิดใช้งานคำอธิบายภาพ
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอโดยใช้แผนภูมิที่ได้กำหนดค่าไว้

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

ตอนนี้คุณได้ตั้งค่าคำอธิบายสำหรับป้ายข้อมูลในแผนภูมิสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java ปรับแต่งโค้ดตามแผนภูมิเฉพาะและข้อกำหนดข้อมูลของคุณ

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการตั้งค่าคำอธิบายสำหรับป้ายข้อมูลใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(จริง);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการตั้งค่าคำอธิบายประกอบสำหรับป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำอธิบายประกอบเป็นเครื่องมือที่มีประโยชน์สำหรับการเน้นจุดข้อมูลเฉพาะในแผนภูมิและการนำเสนอของคุณ เราได้จัดทำคู่มือทีละขั้นตอนพร้อมโค้ดต้นฉบับเพื่อช่วยให้คุณปรับแต่งได้สำเร็จ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของป้ายข้อมูลได้อย่างไร

หากต้องการปรับแต่งลักษณะของป้ายข้อมูล คุณสามารถแก้ไขคุณสมบัติต่างๆ เช่น แบบอักษร การเติม และสไตล์เส้น ตัวอย่างเช่น:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### ฉันจะเปิดใช้งานหรือปิดใช้งานคำอธิบายภาพสำหรับป้ายข้อมูลได้อย่างไร

หากต้องการเปิดใช้งานหรือปิดใช้งานคำอธิบายภาพสำหรับป้ายข้อมูล ให้ใช้ `setShowLabelAsDataCallout` วิธีการ ตั้งค่าเป็น `true` เพื่อเปิดใช้งานคำอธิบายประกอบและ `false` เพื่อปิดการใช้งานพวกเขา

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // เปิดใช้งานคำอธิบายภาพ
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // ปิดใช้งานคำอธิบายภาพ
```

### ฉันสามารถปรับแต่งเส้นผู้นำสำหรับป้ายข้อมูลได้หรือไม่

ใช่ คุณสามารถปรับแต่งเส้นผู้นำสำหรับป้ายข้อมูลได้โดยใช้คุณสมบัติเช่น สไตล์เส้น สี และความกว้าง ตัวอย่างเช่น:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // เปิดใช้งานเส้นผู้นำ
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

เหล่านี้คือตัวเลือกการปรับแต่งทั่วไปสำหรับป้ายข้อมูลและคำอธิบายประกอบใน Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งลักษณะที่ปรากฏให้เหมาะกับความต้องการเฉพาะของคุณได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}