---
title: การตั้งค่าคำบรรยายภาพสำหรับ Data Label ใน Java Slides
linktitle: การตั้งค่าคำบรรยายภาพสำหรับ Data Label ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าคำบรรยายภาพสำหรับป้ายกำกับข้อมูลใน Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
type: docs
weight: 25
url: /th/java/data-manipulation/setting-callout-data-label-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าคำบรรยายภาพสำหรับป้ายกำกับข้อมูลใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีตั้งค่าคำบรรยายสำหรับป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำบรรยายภาพมีประโยชน์ในการเน้นจุดข้อมูลเฉพาะในแผนภูมิของคุณ เราจะอธิบายโค้ดทีละขั้นตอนและระบุซอร์สโค้ดที่จำเป็น

## ข้อกำหนดเบื้องต้น

- คุณควรติดตั้ง Aspose.Slides สำหรับ Java แล้ว
- สร้างโปรเจ็กต์ Java และเพิ่มไลบรารี Aspose.Slides ให้กับโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 1: สร้างงานนำเสนอและเพิ่มแผนภูมิ

 ขั้นแรก เราต้องสร้างงานนำเสนอและเพิ่มแผนภูมิลงในสไลด์ ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ขั้นตอนที่ 2: กำหนดค่าแผนภูมิ

ต่อไป เราจะกำหนดค่าแผนภูมิโดยการตั้งค่าคุณสมบัติ เช่น คำอธิบาย ซีรีส์ และหมวดหมู่

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// กำหนดค่าซีรี่ส์และหมวดหมู่ (คุณสามารถปรับจำนวนซีรีส์และหมวดหมู่ได้)
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
        // ...
        i++;
    }
    categoryIndex++;
}
```

## ขั้นตอนที่ 3: ปรับแต่งป้ายกำกับข้อมูล

ตอนนี้ เราจะปรับแต่งป้ายกำกับข้อมูล รวมถึงการตั้งค่าไฮไลต์สำหรับชุดสุดท้าย

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // ปรับแต่งการจัดรูปแบบจุดข้อมูล (เติม เส้น ฯลฯ)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // ปรับแต่งการจัดรูปแบบฉลาก (แบบอักษร การเติม ฯลฯ)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // เปิดใช้งานคำบรรยายภาพ
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยแผนภูมิที่กำหนดค่าไว้

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

ตอนนี้ คุณได้ตั้งค่าคำบรรยายสำหรับป้ายกำกับข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว ปรับแต่งโค้ดตามแผนภูมิและข้อมูลที่คุณต้องการ

## กรอกซอร์สโค้ดสำหรับการตั้งค่าคำบรรยายภาพสำหรับป้ายกำกับข้อมูลใน Java Slides

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

ในบทช่วยสอนนี้ เราได้สำรวจวิธีตั้งค่าคำบรรยายสำหรับป้ายข้อมูลในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java คำบรรยายภาพเป็นเครื่องมืออันทรงคุณค่าในการเน้นจุดข้อมูลเฉพาะในแผนภูมิและงานนำเสนอของคุณ เราได้ให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อช่วยให้คุณบรรลุการปรับแต่งนี้

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของป้ายกำกับข้อมูลได้อย่างไร

หากต้องการปรับแต่งลักษณะที่ปรากฏของป้ายกำกับข้อมูล คุณสามารถแก้ไขคุณสมบัติ เช่น แบบอักษร การเติม และสไตล์เส้นได้ ตัวอย่างเช่น:

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

### ฉันจะเปิดหรือปิดใช้คำบรรยายสำหรับป้ายกำกับข้อมูลได้อย่างไร

 หากต้องการเปิดหรือปิดใช้คำบรรยายสำหรับป้ายกำกับข้อมูล ให้ใช้`setShowLabelAsDataCallout` วิธี. ตั้งเป็น`true` เพื่อเปิดใช้งานคำบรรยายภาพและ`false` เพื่อปิดการใช้งาน

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // เปิดใช้งานคำบรรยายภาพ
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // ปิดการใช้งานคำบรรยายภาพ
```

### ฉันสามารถปรับแต่งเส้นตัวนำสำหรับป้ายกำกับข้อมูลได้หรือไม่

ใช่ คุณสามารถปรับแต่งเส้นตัวนำสำหรับป้ายกำกับข้อมูลได้โดยใช้คุณสมบัติ เช่น ลักษณะของเส้น สี และความกว้าง ตัวอย่างเช่น:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // เปิดใช้งานเส้นผู้นำ
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

นี่คือตัวเลือกการปรับแต่งทั่วไปบางส่วนสำหรับป้ายกำกับข้อมูลและคำบรรยายใน Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งรูปลักษณ์ให้ตรงกับความต้องการเฉพาะของคุณเพิ่มเติมได้