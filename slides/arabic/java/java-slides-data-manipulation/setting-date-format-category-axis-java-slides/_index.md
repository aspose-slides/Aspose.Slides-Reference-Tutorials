---
title: ضبط تنسيق التاريخ لمحور الفئة في شرائح Java
linktitle: ضبط تنسيق التاريخ لمحور الفئة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين تنسيق تاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع كود المصدر.
weight: 26
url: /ar/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لإعداد تنسيق التاريخ لمحور الفئة في شرائح جافا

في هذا البرنامج التعليمي، سوف نتعلم كيفية تعيين تنسيق تاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides for Java. Aspose.Slides for Java هي مكتبة قوية تتيح لك إنشاء عروض PowerPoint التقديمية ومعالجتها وإدارتها برمجيًا.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. Aspose.Slides لمكتبة Java (يمكنك تنزيلها من[هنا](https://releases.aspose.com/slides/java/).
2. إعداد بيئة تطوير جافا.

## الخطوة 1: إنشاء عرض تقديمي لـ PowerPoint

أولاً، نحتاج إلى إنشاء عرض تقديمي لبرنامج PowerPoint حيث سنضيف مخططًا. تأكد من أنك قمت باستيراد فئات Aspose.Slides الضرورية.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

الآن، دعونا نضيف مخططًا إلى شريحة PowerPoint. سنستخدم مخططًا مساحيًا في هذا المثال.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## الخطوة 3: إعداد بيانات الرسم البياني

سنقوم بإعداد بيانات الرسم البياني والفئات. في هذا المثال، سوف نستخدم فئات التاريخ.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// إضافة فئات التاريخ
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// إضافة سلسلة البيانات
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## الخطوة 4: تخصيص محور الفئة
الآن، لنقم بتخصيص محور الفئة لعرض التواريخ بتنسيق معين (على سبيل المثال، yyyy).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## الخطوة 5: احفظ العرض التقديمي
وأخيرا، احفظ عرض PowerPoint التقديمي.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في تعيين تنسيق تاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لتحديد تنسيق التاريخ لمحور الفئة في شرائح جافا

```java
	// المسار إلى دليل المستندات.
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

##خاتمة

لقد نجحت في تخصيص تنسيق التاريخ لمحور الفئة في مخطط Java Slides باستخدام Aspose.Slides for Java. يتيح لك ذلك عرض قيم التاريخ بالتنسيق المطلوب على مخططاتك. لا تتردد في استكشاف المزيد من خيارات التخصيص بناءً على متطلباتك المحددة.

## الأسئلة الشائعة

### كيف أقوم بتغيير تنسيق التاريخ لمحور الفئة؟

 لتغيير تنسيق التاريخ لمحور الفئة، استخدم الزر`setNumberFormat` على محور الفئة وقم بتوفير نمط تنسيق التاريخ المطلوب، مثل "yyyy-MM-dd" أو "MM/yyyy". تأكد من ضبط`setNumberFormatLinkedToSource(false)` لتجاوز التنسيق الافتراضي.

### هل يمكنني استخدام تنسيقات تاريخ مختلفة لمخططات مختلفة في نفس العرض التقديمي؟

نعم، يمكنك تعيين تنسيقات تاريخ مختلفة لمحاور الفئات في مخططات مختلفة داخل نفس العرض التقديمي. ما عليك سوى تخصيص محور الفئة لكل مخطط حسب الحاجة.

### كيف يمكنني إضافة المزيد من نقاط البيانات إلى المخطط؟

 لإضافة المزيد من نقاط البيانات إلى المخطط، استخدم`getDataPoints().addDataPointForLineSeries`طريقة على سلسلة البيانات وتوفير قيم البيانات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
