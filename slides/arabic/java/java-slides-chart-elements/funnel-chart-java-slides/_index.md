---
"description": "استكشف Aspose.Slides لجافا مع دروس تعليمية خطوة بخطوة. أنشئ مخططات قمعية رائعة، وغير ذلك الكثير."
"linktitle": "مخطط القمع في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط القمع في شرائح Java"
"url": "/ar/java/chart-elements/funnel-chart-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط القمع في شرائح Java


## مقدمة إلى مخطط القمع في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط قمعي باستخدام Aspose.Slides لجافا. تُعدّ المخططات القمعية مفيدة لتصوير عملية متسلسلة بمراحل تتضاءل تدريجيًا، مثل تحويلات المبيعات أو اكتساب العملاء.

## المتطلبات الأساسية

قبل البدء، تأكد من إضافة مكتبة Aspose.Slides إلى مشروع جافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

أولاً، دعنا ننشئ عرضًا تقديميًا ونضيف إليه شريحة حيث سنضع مخططنا البياني.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

تأكد من الاستبدال `"Your Document Directory"` مع المسار الفعلي إلى دليل المشروع الخاص بك.

## الخطوة 2: إنشاء مخطط القمع

الآن، دعنا ننشئ مخطط القمع ونضع أبعاده على الشريحة.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

في الكود أعلاه، نضيف مخططًا قمعيًا إلى الشريحة الأولى عند الإحداثيات (50، 50) بعرض 500 وارتفاع 400 بكسل.

## الخطوة 3: تحديد بيانات الرسم البياني

بعد ذلك، سنُعرّف بيانات مخططنا القمعي. سنُحدّد الفئات والسلاسل للمخطط.

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

هنا، نقوم بمسح أي بيانات موجودة، وإضافة فئات (في هذه الحالة، مراحل القمع)، وتعيين تسمياتها.

## الخطوة 4: إضافة نقاط البيانات

الآن، دعنا نضيف نقاط البيانات إلى سلسلة مخططاتنا البيانية.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

في هذه الخطوة، نقوم بإنشاء سلسلة لمخطط القمع الخاص بنا ونضيف نقاط البيانات التي تمثل القيم في كل مرحلة من مراحل القمع.

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، نحفظ العرض التقديمي مع مخطط القمع في ملف PowerPoint.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

تأكد من الاستبدال `"Your Document Directory"` مع موقع الحفظ المطلوب.

## كود المصدر الكامل لمخطط القمع في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا لك كيفية إنشاء مخطط قمعي في Java Slides باستخدام Aspose.Slides لـ Java. يمكنك تخصيص المخطط بشكل أكبر عن طريق ضبط الألوان والتسميات والخصائص الأخرى لتناسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر مخطط القمع؟

يمكنك تخصيص مظهر مخطط القمع عن طريق تعديل خصائصه، والسلسلة، ونقاط البيانات. راجع وثائق Aspose.Slides للاطلاع على خيارات التخصيص المفصلة.

### هل يمكنني إضافة المزيد من الفئات أو نقاط البيانات إلى مخطط المبيعات؟

نعم، يمكنك إضافة المزيد من الفئات ونقاط البيانات إلى مخطط المبيعات عن طريق توسيع الكود في الخطوة 3 والخطوة 4 وفقًا لذلك.

### هل من الممكن تغيير نوع الرسم البياني إلى شيء آخر غير القمع؟

نعم، يدعم Aspose.Slides أنواعًا مختلفة من المخططات. يمكنك تغيير نوع المخطط باستبدال `ChartType.Funnel` مع نوع الرسم البياني المطلوب في الخطوة 2.

### كيف أتعامل مع الأخطاء أو الاستثناءات أثناء العمل مع Aspose.Slides؟

يمكنك معالجة الأخطاء والاستثناءات باستخدام آليات معالجة استثناءات جافا القياسية. تأكد من استخدام معالجة أخطاء سليمة في شفرتك للتعامل مع المواقف غير المتوقعة بسلاسة.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟

يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية حول استخدام Aspose.Slides لـ Java في [التوثيق](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}