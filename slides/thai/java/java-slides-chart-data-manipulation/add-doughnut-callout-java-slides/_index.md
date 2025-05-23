---
"description": "เรียนรู้การเพิ่มคำอธิบายโดนัทในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการนำเสนอที่มีประสิทธิภาพยิ่งขึ้น"
"linktitle": "เพิ่มคำอธิบายโดนัทใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มคำอธิบายโดนัทใน Java Slides"
"url": "/th/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มคำอธิบายโดนัทใน Java Slides


## การแนะนำการเพิ่มคำอธิบายโดนัทใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการเพิ่ม Doughnut Callout ลงในสไลด์ใน Java โดยใช้ Aspose.Slides สำหรับ Java Doughnut Callout คือองค์ประกอบแผนภูมิที่ใช้เน้นจุดข้อมูลเฉพาะในแผนภูมิ Doughnut เราจะให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับฉบับสมบูรณ์เพื่อความสะดวกของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. สภาพแวดล้อมการพัฒนา Java
2. Aspose.Slides สำหรับไลบรารี Java
3. สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) เช่น Eclipse หรือ IntelliJ IDEA
4. การนำเสนอ PowerPoint ที่คุณต้องการเพิ่มคำอธิบายภาพโดนัท

## ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ

1. สร้างโครงการ Java ใหม่ใน IDE ที่คุณเลือก
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณโดยเป็นส่วนที่ต้องมี

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ในการเริ่มต้น คุณจะต้องเริ่มต้นการนำเสนอ PowerPoint และสร้างสไลด์ที่คุณต้องการเพิ่มคำอธิบายโดนัท นี่คือโค้ดสำหรับทำสิ่งนี้:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

อย่าลืมเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์งานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 3: สร้างแผนภูมิโดนัท

ขั้นต่อไป คุณจะสร้างแผนภูมิโดนัทบนสไลด์ คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิได้ตามความต้องการ นี่คือโค้ดสำหรับเพิ่มแผนภูมิโดนัท:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ขั้นตอนที่ 4: ปรับแต่งแผนภูมิโดนัท

ตอนนี้ถึงเวลาปรับแต่งแผนภูมิโดนัทแล้ว เราจะตั้งค่าคุณสมบัติต่างๆ เช่น การลบคำอธิบาย การกำหนดค่าขนาดรู และการปรับมุมของชิ้นแรก นี่คือโค้ด:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

โค้ดสั้นๆ นี้กำหนดคุณสมบัติของแผนภูมิโดนัท คุณสามารถปรับค่าต่างๆ ให้ตรงตามความต้องการเฉพาะของคุณได้

## ขั้นตอนที่ 5: เพิ่มข้อมูลลงในแผนภูมิโดนัท

ตอนนี้เรามาเพิ่มข้อมูลลงในแผนภูมิโดนัทกัน เราจะปรับแต่งลักษณะของจุดข้อมูลด้วย นี่คือโค้ดสำหรับทำสิ่งนี้:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // ปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลที่นี่
        i++;
    }
    categoryIndex++;
}
```

ในโค้ดนี้ เราจะเพิ่มหมวดหมู่และจุดข้อมูลลงในแผนภูมิโดนัท คุณสามารถปรับแต่งลักษณะของจุดข้อมูลเพิ่มเติมได้ตามต้องการ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายอย่าลืมบันทึกการนำเสนอของคุณหลังจากเพิ่ม Doughnut Callout นี่คือโค้ดสำหรับบันทึกการนำเสนอ:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

อย่าลืมเปลี่ยน `"chart.pptx"` ด้วยชื่อไฟล์ที่คุณต้องการ

ขอแสดงความยินดี! คุณได้เพิ่ม Doughnut Callout ลงในสไลด์ Java สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถรันแอปพลิเคชัน Java เพื่อสร้างการนำเสนอ PowerPoint ด้วยแผนภูมิ Doughnut และ Callout

## โค้ดต้นฉบับสมบูรณ์สำหรับการเพิ่มคำอธิบายโดนัทใน Java Slides

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนการเพิ่มคำอธิบายโดนัทลงในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณได้เรียนรู้วิธีการสร้างแผนภูมิโดนัท ปรับแต่งรูปลักษณ์ของแผนภูมิ และเพิ่มจุดข้อมูลแล้ว อย่าลังเลที่จะปรับปรุงการนำเสนอของคุณให้ดียิ่งขึ้นด้วยไลบรารีอันทรงพลังนี้ และสำรวจตัวเลือกการสร้างแผนภูมิเพิ่มเติม

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนลักษณะของ Doughnut Callout ได้อย่างไร?

คุณสามารถปรับแต่งรูปลักษณ์ของ Doughnut Callout ได้โดยแก้ไขคุณสมบัติของจุดข้อมูลในแผนภูมิ ในโค้ดที่ให้มา คุณจะเห็นวิธีการตั้งค่าสีเติม สีเส้น สไตล์แบบอักษร และแอตทริบิวต์อื่นๆ ของจุดข้อมูล

### ฉันสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในแผนภูมิโดนัทได้หรือไม่

ใช่ คุณสามารถเพิ่มจุดข้อมูลได้มากเท่าที่ต้องการในแผนภูมิโดนัท เพียงขยายลูปในโค้ดที่เพิ่มหมวดหมู่และจุดข้อมูล และระบุข้อมูลและการจัดรูปแบบที่เหมาะสม

### ฉันจะปรับตำแหน่งและขนาดของแผนภูมิโดนัทบนสไลด์ได้อย่างไร

คุณสามารถเปลี่ยนตำแหน่งและขนาดของแผนภูมิโดนัทได้โดยการแก้ไขพารามิเตอร์ใน `addChart` วิธีการ ตัวเลขทั้งสี่ตัวในวิธีนั้นสอดคล้องกับพิกัด X และ Y ของมุมบนซ้ายของแผนภูมิ และความกว้างและความสูงตามลำดับ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}