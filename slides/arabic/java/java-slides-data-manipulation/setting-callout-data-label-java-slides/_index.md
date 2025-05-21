---
"description": "تعرّف على كيفية إعداد تسميات البيانات في Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "إعداد استدعاء تسمية البيانات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إعداد استدعاء تسمية البيانات في شرائح Java"
"url": "/ar/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إعداد استدعاء تسمية البيانات في شرائح Java


## مقدمة لتعيين تسمية البيانات في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنشرح كيفية إعداد التعليقات التوضيحية لعلامات البيانات في مخطط بياني باستخدام Aspose.Slides لجافا. يمكن أن تكون التعليقات التوضيحية مفيدة لتسليط الضوء على نقاط بيانات محددة في مخططك البياني. سنشرح الكود خطوة بخطوة ونوفر الكود المصدري اللازم.

## المتطلبات الأساسية

- يجب أن يكون لديك Aspose.Slides for Java مثبتًا.
- قم بإنشاء مشروع Java وأضف مكتبة Aspose.Slides إلى مشروعك.

## الخطوة 1: إنشاء عرض تقديمي وإضافة مخطط

أولاً، نحتاج إلى إنشاء عرض تقديمي وإضافة مخطط إلى الشريحة. تأكد من استبدال `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## الخطوة 2: تكوين الرسم البياني

بعد ذلك، سنقوم بتكوين الرسم البياني عن طريق تعيين خصائص مثل الأسطورة والسلسلة والفئات.

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

الآن، سنقوم بتخصيص تسميات البيانات، بما في ذلك إعداد التعليقات التوضيحية للسلسلة الأخيرة.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // تخصيص تنسيق نقاط البيانات (التعبئة، الخط، وما إلى ذلك)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // تخصيص تنسيق الملصق (الخط، التعبئة، وما إلى ذلك)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // تمكين التعليقات التوضيحية
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام الرسم البياني الذي قمت بتكوينه.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

لقد نجحت الآن في إعداد تسميات البيانات في مخطط باستخدام Aspose.Slides لجافا. خصّص الكود وفقًا لمتطلبات مخططك وبياناتك.

## كود المصدر الكامل لإعداد استدعاء تسمية البيانات في شرائح Java

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
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(صحيح)؛
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

في هذا البرنامج التعليمي، استكشفنا كيفية إعداد تعليقات توضيحية لعلامات البيانات في مخطط بياني باستخدام Aspose.Slides لجافا. تُعد التعليقات التوضيحية أدوات قيّمة لإبراز نقاط بيانات محددة في مخططاتك وعروضك التقديمية. لقد قدمنا دليلاً تفصيليًا مع شفرة المصدر لمساعدتك في تحقيق هذا التخصيص.

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

### كيف يمكنني تمكين أو تعطيل التعليقات التوضيحية لملصقات البيانات؟

لتمكين أو تعطيل التعليقات التوضيحية لملصقات البيانات، استخدم `setShowLabelAsDataCallout` الطريقة. اضبطها على `true` لتمكين النداءات و `false` لتعطيلهم.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // تمكين التعليقات التوضيحية
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // تعطيل التعليقات التوضيحية
```

### هل يمكنني تخصيص خطوط القائد لملصقات البيانات؟

نعم، يمكنك تخصيص خطوط البيانات الرئيسية باستخدام خصائص مثل نمط الخط ولونه وعرضه. على سبيل المثال:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // تمكين خطوط القائد
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

هذه بعض خيارات التخصيص الشائعة لعلامات البيانات وعلامات الاستدعاء في Aspose.Slides لـ Java. يمكنك تخصيص المظهر بشكل أكبر ليناسب احتياجاتك الخاصة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}