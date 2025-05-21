---
"description": "تعلم كيفية إضافة تعليقات توضيحية على شكل حلقات في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لتحسين العروض التقديمية."
"linktitle": "إضافة تعليق توضيحي على شكل كعكة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة تعليق توضيحي على شكل كعكة في شرائح Java"
"url": "/ar/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة تعليق توضيحي على شكل كعكة في شرائح Java


## مقدمة لإضافة تعليق توضيحي على شكل كعكة في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنشرح لك عملية إضافة تعليق دائري إلى شريحة في جافا باستخدام Aspose.Slides. تعليق الدائري هو عنصر مخطط يُستخدم لتسليط الضوء على نقاط بيانات محددة في مخطط دائري. سنزودك بإرشادات خطوة بخطوة وشيفرة مصدرية كاملة لتسهيل الأمر عليك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. بيئة تطوير جافا
2. مكتبة Aspose.Slides لـ Java
3. بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA
4. عرض تقديمي على PowerPoint حيث تريد إضافة تعليق توضيحي على شكل كعكة

## الخطوة 1: إعداد مشروع Java الخاص بك

1. قم بإنشاء مشروع Java جديد في IDE الذي اخترته.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك كاعتمادية.

## الخطوة 2: تهيئة العرض التقديمي

للبدء، ستحتاج إلى تهيئة عرض تقديمي في PowerPoint وإنشاء شريحة لإضافة شرح الدونات. إليك الكود اللازم:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

تأكد من الاستبدال `"Your Document Directory"` مع المسار الفعلي لملف عرض PowerPoint الخاص بك.

## الخطوة 3: إنشاء مخطط دائري

بعد ذلك، ستُنشئ مخططًا دائريًا على الشريحة. يمكنك تخصيص موضع المخطط وحجمه حسب احتياجاتك. إليك الكود لإضافة مخطط دائري:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## الخطوة 4: تخصيص مخطط الدونات

الآن، حان وقت تخصيص مخطط الدونات. سنضبط خصائص مختلفة، مثل إزالة التسمية التوضيحية، وضبط حجم الفتحة، وضبط زاوية الشريحة الأولى. إليك الكود:

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

يُحدد هذا المقطع الشفري خصائص مخطط الدونات. يمكنك تعديل القيم لتلبية احتياجاتك الخاصة.

## الخطوة 5: إضافة البيانات إلى مخطط الدونات

الآن، لنُضِف البيانات إلى مخطط الدونات. سنُخصِّص أيضًا مظهر نقاط البيانات. إليك الكود اللازم:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // تخصيص مظهر نقطة البيانات هنا
        i++;
    }
    categoryIndex++;
}
```

في هذا الكود، نضيف فئات ونقاط بيانات إلى مخطط الدونات. يمكنك تخصيص مظهر نقاط البيانات حسب الحاجة.

## الخطوة 6: حفظ العرض التقديمي

أخيرًا، لا تنسَ حفظ عرضك التقديمي بعد إضافة شرح الدونات. إليك الكود لحفظ العرض التقديمي:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

تأكد من الاستبدال `"chart.pptx"` مع اسم الملف المطلوب.

تهانينا! لقد نجحت في إضافة مخطط دائري وشرح توضيحي إلى شريحة جافا باستخدام Aspose.Slides لجافا. يمكنك الآن تشغيل تطبيق جافا لإنشاء عرض تقديمي على PowerPoint باستخدام مخطط دائري وشرح توضيحي.

## كود المصدر الكامل لإضافة استدعاء الكعكة في شرائح Java

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا عملية إضافة مخطط دائري إلى شريحة جافا باستخدام Aspose.Slides لجافا. لقد تعلمت كيفية إنشاء مخطط دائري، وتخصيص مظهره، وإضافة نقاط بيانات. لا تتردد في تحسين عروضك التقديمية باستخدام هذه المكتبة القوية، واستكشف المزيد من خيارات المخططات البيانية.

## الأسئلة الشائعة

### كيف يمكنني تغيير مظهر Doughnut Callout؟

يمكنك تخصيص مظهر "التعليق الدائري" بتعديل خصائص نقاط البيانات في الرسم البياني. يوضح الكود المرفق كيفية ضبط لون التعبئة، ولون الخط، ونمط الخط، وغيرها من خصائص نقاط البيانات.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى مخطط الدونات؟

نعم، يمكنك إضافة أي عدد من نقاط البيانات إلى مخطط الدونات. ما عليك سوى توسيع نطاق الحلقات في الكود حيث تُضاف الفئات ونقاط البيانات، ثم توفير البيانات والتنسيق المناسبين.

### كيف يمكنني تعديل موضع وحجم مخطط الدونات على الشريحة؟

يمكنك تغيير موضع وحجم مخطط الدونات عن طريق تعديل المعلمات في `addChart` الطريقة. الأرقام الأربعة في هذه الطريقة تتوافق مع إحداثيات X وY للزاوية العلوية اليسرى من الرسم البياني وعرضه وارتفاعه، على التوالي.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}