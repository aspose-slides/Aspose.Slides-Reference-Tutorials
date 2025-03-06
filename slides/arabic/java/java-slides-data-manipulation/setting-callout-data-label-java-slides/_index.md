---
title: إعداد وسائل الشرح لتسمية البيانات في شرائح Java
linktitle: إعداد وسائل الشرح لتسمية البيانات في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إعداد وسائل الشرح لتسميات البيانات في Aspose.Slides لـ Java. دليل خطوة بخطوة مع كود المصدر.
weight: 25
url: /ar/java/data-manipulation/setting-callout-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إعداد وسائل الشرح لتسمية البيانات في شرائح Java


## مقدمة لإعداد وسائل الشرح لتسمية البيانات في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنوضح كيفية إعداد وسائل الشرح لتسميات البيانات في مخطط باستخدام Aspose.Slides لـ Java. يمكن أن تكون وسائل الشرح مفيدة لتسليط الضوء على نقاط بيانات محددة في المخطط الخاص بك. سنتعرف على الكود خطوة بخطوة ونوفر كود المصدر اللازم.

## المتطلبات الأساسية

- يجب أن يكون Aspose.Slides الخاص بـ Java مثبتًا لديك.
- أنشئ مشروع Java وأضف مكتبة Aspose.Slides إلى مشروعك.

## الخطوة 1: إنشاء عرض تقديمي وإضافة مخطط

 أولاً، نحتاج إلى إنشاء عرض تقديمي وإضافة مخطط إلى الشريحة. تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## الخطوة 2: تكوين المخطط

بعد ذلك، سنقوم بتكوين المخطط عن طريق تعيين خصائص مثل وسيلة الإيضاح والسلسلة والفئات.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// تكوين السلسلة والفئات (يمكنك ضبط عدد السلسلة والفئات)
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
        // أضف نقاط البيانات هنا
        // ...
        i++;
    }
    categoryIndex++;
}
```

## الخطوة 3: تخصيص تسميات البيانات

الآن، سنقوم بتخصيص تسميات البيانات، بما في ذلك إعداد وسائل الشرح للسلسلة الأخيرة.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // تخصيص تنسيق نقطة البيانات (تعبئة، خط، إلخ.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //تخصيص تنسيق التسمية (الخط، التعبئة، وما إلى ذلك)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // تمكين وسائل الشرح
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي بالمخطط الذي تم تكوينه.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

لقد نجحت الآن في إعداد وسائل الشرح لتسميات البيانات في مخطط باستخدام Aspose.Slides for Java. قم بتخصيص الكود وفقًا لمتطلبات الرسم البياني والبيانات المحددة الخاصة بك.

## كود المصدر الكامل لإعداد وسائل الشرح لتسمية البيانات في شرائح Java

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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
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

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إعداد وسائل الشرح لتسميات البيانات في مخطط باستخدام Aspose.Slides لـ Java. تعد وسائل الشرح أدوات قيمة للتأكيد على نقاط بيانات محددة في المخططات والعروض التقديمية الخاصة بك. لقد قدمنا دليلًا خطوة بخطوة بالإضافة إلى التعليمات البرمجية المصدر لمساعدتك في تحقيق هذا التخصيص.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر تسميات البيانات؟

لتخصيص مظهر تسميات البيانات، يمكنك تعديل خصائص مثل الخط والتعبئة وأنماط الخطوط. على سبيل المثال:

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

### كيف يمكنني تمكين وسائل الشرح أو تعطيلها لتسميات البيانات؟

 لتمكين وسائل الشرح أو تعطيلها لتسميات البيانات، استخدم`setShowLabelAsDataCallout` طريقة. اضبطه على`true` لتمكين وسائل الشرح و`false`لتعطيلهم.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // تمكين وسائل الشرح
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // تعطيل وسائل الشرح
```

### هل يمكنني تخصيص الخطوط الرئيسية لتسميات البيانات؟

نعم، يمكنك تخصيص الخطوط الرئيسية لتسميات البيانات باستخدام خصائص مثل نمط الخط واللون والعرض. على سبيل المثال:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // تمكين خطوط الزعيم
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

هذه بعض خيارات التخصيص الشائعة لتسميات البيانات ووسائل الشرح في Aspose.Slides لـ Java. يمكنك أيضًا تخصيص المظهر وفقًا لاحتياجاتك المحددة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
