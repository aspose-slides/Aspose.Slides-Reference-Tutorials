---
title: เพิ่มคำบรรยายภาพโดนัทใน Java Slides
linktitle: เพิ่มคำบรรยายภาพโดนัทใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มคำบรรยายภาพโดนัทใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการนำเสนอที่ได้รับการปรับปรุง
weight: 12
url: /th/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มคำบรรยายภาพโดนัทใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มคำบรรยายภาพโดนัทใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการเพิ่ม Donut Callout ลงในสไลด์ใน Java โดยใช้ Aspose.Slides สำหรับ Java คำบรรยายภาพโดนัทเป็นองค์ประกอบแผนภูมิที่สามารถใช้เพื่อเน้นจุดข้อมูลเฉพาะในแผนภูมิโดนัท เราจะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ดที่สมบูรณ์เพื่อความสะดวกของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. สภาพแวดล้อมการพัฒนาจาวา
2. Aspose.Slides สำหรับไลบรารี Java
3. สภาพแวดล้อมการพัฒนาแบบรวม (IDE) เช่น Eclipse หรือ IntelliJ IDEA
4. งานนำเสนอ PowerPoint ที่คุณต้องการเพิ่มคำบรรยายภาพโดนัท

## ขั้นตอนที่ 1: ตั้งค่าโครงการ Java ของคุณ

1. สร้างโปรเจ็กต์ Java ใหม่ใน IDE ที่คุณเลือก
2. เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับโปรเจ็กต์ของคุณเป็นการพึ่งพา

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

ในการเริ่มต้น คุณจะต้องเริ่มต้นงานนำเสนอ PowerPoint และสร้างสไลด์ที่คุณต้องการเพิ่มคำบรรยายภาพโดนัท นี่คือรหัสเพื่อให้บรรลุเป้าหมายนี้:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์งานนำเสนอ PowerPoint ของคุณ

## ขั้นตอนที่ 3: สร้างแผนภูมิโดนัท

ต่อไป คุณจะสร้างแผนภูมิโดนัทบนสไลด์ คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิได้ตามความต้องการของคุณ นี่คือโค้ดสำหรับเพิ่มแผนภูมิโดนัท:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## ขั้นตอนที่ 4: ปรับแต่งแผนภูมิโดนัท

ตอนนี้ก็ถึงเวลาปรับแต่งแผนภูมิโดนัทแล้ว เราจะตั้งค่าคุณสมบัติต่างๆ เช่น การลบคำอธิบาย การกำหนดค่าขนาดรู และการปรับมุมชิ้นแรก นี่คือรหัส:

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

ข้อมูลโค้ดนี้ตั้งค่าคุณสมบัติสำหรับแผนภูมิโดนัท คุณสามารถปรับค่าให้ตรงตามความต้องการเฉพาะของคุณได้

## ขั้นตอนที่ 5: เพิ่มข้อมูลลงในแผนภูมิโดนัท

ตอนนี้ มาเพิ่มข้อมูลลงในแผนภูมิโดนัทกันดีกว่า นอกจากนี้เรายังจะปรับแต่งรูปลักษณ์ของจุดข้อมูลด้วย นี่คือรหัสเพื่อทำสิ่งนี้ให้สำเร็จ:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // ปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลได้ที่นี่
        i++;
    }
    categoryIndex++;
}
```

ในโค้ดนี้ เรากำลังเพิ่มหมวดหมู่และจุดข้อมูลลงในแผนภูมิโดนัท คุณสามารถปรับแต่งลักษณะที่ปรากฏของจุดข้อมูลเพิ่มเติมได้ตามต้องการ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายนี้ อย่าลืมบันทึกงานนำเสนอของคุณหลังจากเพิ่มคำบรรยายภาพโดนัทแล้ว นี่คือโค้ดสำหรับบันทึกการนำเสนอ:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"chart.pptx"` ด้วยชื่อไฟล์ที่คุณต้องการ

ยินดีด้วย! คุณได้เพิ่ม Donut Callout ลงในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถเรียกใช้แอปพลิเคชัน Java ของคุณเพื่อสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิโดนัทและคำบรรยายภาพได้

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการเพิ่มคำบรรยายภาพโดนัทใน Java Slides

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

ในบทช่วยสอนนี้ เราได้กล่าวถึงกระบวนการเพิ่ม Donut Callout ลงในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณได้เรียนรู้วิธีสร้างแผนภูมิโดนัท ปรับแต่งรูปลักษณ์ และเพิ่มจุดข้อมูลแล้ว อย่าลังเลที่จะปรับปรุงการนำเสนอของคุณเพิ่มเติมด้วยไลบรารีอันทรงพลังนี้ และสำรวจตัวเลือกการสร้างแผนภูมิเพิ่มเติม

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนรูปลักษณ์ของคำบรรยายภาพโดนัทได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของคำบรรยายภาพโดนัทได้โดยการแก้ไขคุณสมบัติของจุดข้อมูลในแผนภูมิ ในโค้ดที่ให้มา คุณสามารถดูวิธีตั้งค่าสีเติม สีเส้น ลักษณะแบบอักษร และคุณลักษณะอื่นๆ ของจุดข้อมูลได้

### ฉันสามารถเพิ่มจุดข้อมูลลงในแผนภูมิโดนัทได้หรือไม่

ได้ คุณสามารถเพิ่มจุดข้อมูลลงในแผนภูมิโดนัทได้มากเท่าที่ต้องการ เพียงขยายลูปในโค้ดที่มีการเพิ่มหมวดหมู่และจุดข้อมูล และจัดเตรียมข้อมูลและการจัดรูปแบบที่เหมาะสม

### ฉันจะปรับตำแหน่งและขนาดของแผนภูมิโดนัทบนสไลด์ได้อย่างไร

 คุณสามารถเปลี่ยนตำแหน่งและขนาดของแผนภูมิโดนัทได้โดยการแก้ไขพารามิเตอร์ใน`addChart` วิธี. ตัวเลขสี่ตัวในวิธีนั้นสอดคล้องกับพิกัด X และ Y ของมุมซ้ายบนของแผนภูมิ รวมถึงความกว้างและความสูง ตามลำดับ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
