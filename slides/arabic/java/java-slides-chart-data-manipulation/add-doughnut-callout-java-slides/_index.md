---
title: إضافة وسيلة شرح دونات في شرائح جافا
linktitle: إضافة وسيلة شرح دونات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة وسائل شرح الدونات في شرائح Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع التعليمات البرمجية المصدر للعروض التقديمية المحسنة.
weight: 12
url: /ar/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة وسيلة شرح دونات في شرائح جافا


## مقدمة لإضافة وسيلة شرح دونات في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة وسيلة شرح دونات إلى شريحة في Java باستخدام Aspose.Slides for Java. وسيلة الشرح الدائرية المجوفة هي عنصر مخطط يمكن استخدامه لتمييز نقاط بيانات محددة في المخطط الدائري المجوف. سنزودك بتعليمات خطوة بخطوة وكود المصدر الكامل لراحتك.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. بيئة تطوير جافا
2. Aspose.Slides لمكتبة جافا
3. بيئة التطوير المتكاملة (IDE) مثل Eclipse أو IntelliJ IDEA
4. عرض تقديمي لـ PowerPoint حيث تريد إضافة وسيلة شرح الدونات

## الخطوة 1: قم بإعداد مشروع Java الخاص بك

1. قم بإنشاء مشروع Java جديد في IDE الذي اخترته.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك باعتبارها تبعية.

## الخطوة 2: تهيئة العرض التقديمي

للبدء، ستحتاج إلى تهيئة عرض تقديمي لـ PowerPoint وإنشاء شريحة حيث تريد إضافة وسيلة شرح الدونات. إليك الكود لتحقيق ذلك:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي لملف عرض PowerPoint التقديمي.

## الخطوة 3: إنشاء مخطط دائري

بعد ذلك، ستقوم بإنشاء مخطط دائري على الشريحة. يمكنك تخصيص موضع المخطط وحجمه وفقًا لمتطلباتك. إليك الرمز لإضافة مخطط دائري:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## الخطوة 4: تخصيص مخطط الكعكة

حان الوقت الآن لتخصيص المخطط الدائري المجوف. سنقوم بتعيين خصائص مختلفة مثل إزالة وسيلة الإيضاح وتكوين حجم الثقب وضبط زاوية الشريحة الأولى. إليك الكود:

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

يقوم مقتطف الكود هذا بتعيين خصائص المخطط الدائري المجوف. يمكنك ضبط القيم لتلبية احتياجاتك الخاصة.

## الخطوة 5: إضافة البيانات إلى المخطط الدائري

الآن، دعونا نضيف البيانات إلى المخطط الدائري المجوف. سنقوم أيضًا بتخصيص مظهر نقاط البيانات. إليك الكود لإنجاز هذا:

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

في هذا الكود، نقوم بإضافة فئات ونقاط بيانات إلى المخطط الدائري المجوف. يمكنك أيضًا تخصيص مظهر نقاط البيانات حسب الحاجة.

## الخطوة 6: احفظ العرض التقديمي

وأخيرًا، لا تنس حفظ العرض التقديمي الخاص بك بعد إضافة وسيلة شرح الدونات. إليك الكود لحفظ العرض التقديمي:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 تأكد من استبدال`"chart.pptx"` مع اسم الملف المطلوب.

تهانينا! لقد نجحت في إضافة وسيلة شرح دونات إلى شريحة Java باستخدام Aspose.Slides for Java. يمكنك الآن تشغيل تطبيق Java الخاص بك لإنشاء عرض PowerPoint التقديمي باستخدام المخطط الدائري ووسيلة الشرح.

## أكمل كود المصدر لإضافة وسيلة شرح دونات في شرائح جافا

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية عملية إضافة وسيلة شرح دونات إلى شريحة Java باستخدام Aspose.Slides for Java. لقد تعلمت كيفية إنشاء مخطط دائري مجوف وتخصيص مظهره وإضافة نقاط البيانات. لا تتردد في تحسين عروضك التقديمية بشكل أكبر باستخدام هذه المكتبة القوية واستكشاف المزيد من خيارات الرسوم البيانية.

## الأسئلة الشائعة

### كيف يمكنني تغيير مظهر وسيلة شرح الدونات؟

يمكنك تخصيص مظهر وسيلة الشرح الدائرية المجوفة عن طريق تعديل خصائص نقاط البيانات في المخطط. في التعليمات البرمجية المتوفرة، يمكنك معرفة كيفية تعيين لون التعبئة ولون الخط ونمط الخط والسمات الأخرى لنقاط البيانات.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى المخطط الدائري المجوف؟

نعم، يمكنك إضافة أي عدد من نقاط البيانات حسب الحاجة إلى المخطط الدائري المجوف. ما عليك سوى توسيع الحلقات في التعليمات البرمجية حيث تتم إضافة الفئات ونقاط البيانات وتوفير البيانات والتنسيق المناسب.

### كيف يمكنني ضبط موضع وحجم المخطط الدائري المجوف على الشريحة؟

 يمكنك تغيير موضع المخطط الدائري المجوف وحجمه عن طريق تعديل المعلمات الموجودة في`addChart` طريقة. تتوافق الأرقام الأربعة في هذه الطريقة مع إحداثيات X وY للزاوية العلوية اليسرى للمخطط وعرضه وارتفاعه على التوالي.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
