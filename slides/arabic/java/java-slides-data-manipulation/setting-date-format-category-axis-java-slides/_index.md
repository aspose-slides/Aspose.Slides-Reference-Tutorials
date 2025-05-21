---
"description": "تعرّف على كيفية تعيين تنسيق التاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "ضبط تنسيق التاريخ لمحور الفئة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ضبط تنسيق التاريخ لمحور الفئة في شرائح Java"
"url": "/ar/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط تنسيق التاريخ لمحور الفئة في شرائح Java


## مقدمة لضبط تنسيق التاريخ لمحور الفئة في شرائح Java

في هذا البرنامج التعليمي، سنتعلم كيفية تعيين تنسيق التاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides for Java. Aspose.Slides for Java هي مكتبة فعّالة تتيح لك إنشاء عروض PowerPoint التقديمية وتعديلها وإدارتها برمجيًا.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. Aspose.Slides لمكتبة Java (يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
2. تم إعداد بيئة تطوير Java.

## الخطوة 1: إنشاء عرض تقديمي في PowerPoint

أولاً، نحتاج إلى إنشاء عرض تقديمي ببرنامج PowerPoint لإضافة مخطط بياني. تأكد من استيراد فئات Aspose.Slides اللازمة.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

الآن، لنُضِف مخططًا إلى شريحة PowerPoint. سنستخدم مخططًا مساحيًا في هذا المثال.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## الخطوة 3: تحضير بيانات الرسم البياني

سنقوم بإعداد بيانات المخطط وفئاته. في هذا المثال، سنستخدم فئات التاريخ.

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
الآن، دعنا نقوم بتخصيص محور الفئة لعرض التواريخ بتنسيق محدد (على سبيل المثال، yyyy).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ عرض PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في ضبط تنسيق التاريخ لمحور الفئة في مخطط PowerPoint باستخدام Aspose.Slides لـ Java.

## الكود المصدر الكامل لتعيين تنسيق التاريخ لمحور الفئة في شرائح Java

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

لقد نجحت في تخصيص تنسيق التاريخ لمحور الفئة في مخطط شرائح جافا باستخدام Aspose.Slides لجافا. يتيح لك هذا عرض قيم التاريخ بالتنسيق المطلوب على مخططاتك. لا تتردد في استكشاف خيارات التخصيص الإضافية بناءً على متطلباتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تغيير تنسيق التاريخ لمحور الفئة؟

لتغيير تنسيق التاريخ لمحور الفئة، استخدم `setNumberFormat` على محور الفئة، ووفر نمط تنسيق التاريخ المطلوب، مثل "yyyy-MM-dd" أو "MM/yyyy". تأكد من ضبط `setNumberFormatLinkedToSource(false)` لتجاوز التنسيق الافتراضي.

### هل يمكنني استخدام تنسيقات تاريخ مختلفة لمخططات مختلفة في نفس العرض التقديمي؟

نعم، يمكنك تعيين تنسيقات تاريخ مختلفة لمحاور الفئات في مخططات مختلفة ضمن العرض التقديمي نفسه. ما عليك سوى تخصيص محور الفئة لكل مخطط حسب الحاجة.

### كيف أضيف المزيد من نقاط البيانات إلى الرسم البياني؟

لإضافة المزيد من نقاط البيانات إلى الرسم البياني، استخدم `getDataPoints().addDataPointForLineSeries` الطريقة على سلسلة البيانات وتوفير قيم البيانات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}