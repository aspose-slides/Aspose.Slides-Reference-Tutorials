---
title: مخطط القمع في شرائح جافا
linktitle: مخطط القمع في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: استكشف Aspose.Slides لـ Java من خلال البرامج التعليمية خطوة بخطوة. قم بإنشاء مخططات تحويلية مذهلة والمزيد.
weight: 14
url: /ar/java/chart-elements/funnel-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى مخطط القمع في شرائح جافا

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط قمعى باستخدام Aspose.Slides لـ Java. تُعد المخططات القمعية مفيدة لتصور عملية تسلسلية بمراحل يتم تضييق نطاقها تدريجيًا، مثل تحويلات المبيعات أو اكتساب العملاء.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إضافة مكتبة Aspose.Slides إلى مشروع Java الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

أولاً، لنبدأ عرضًا تقديميًا ونضيف إليه شريحة حيث سنضع المخطط القمعي الخاص بنا.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 تأكد من استبدال`"Your Document Directory"` مع المسار الفعلي إلى دليل المشروع الخاص بك.

## الخطوة 2: إنشاء مخطط التحويل

الآن، لنقم بإنشاء المخطط القمعي ونضع أبعاده على الشريحة.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

في الكود أعلاه، نضيف مخططًا قمعيًا إلى الشريحة الأولى عند الإحداثيات (50، 50) بعرض 500 وارتفاع 400 بكسل.

## الخطوة 3: تحديد بيانات الرسم البياني

بعد ذلك، سنقوم بتحديد البيانات الخاصة بالمخطط القمعي الخاص بنا. سنقوم بتعيين الفئات والسلاسل للمخطط.

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

هنا، نقوم بمسح أي بيانات موجودة، وإضافة فئات (في هذه الحالة، مراحل مسار التحويل)، وتعيين تسمياتها.

## الخطوة 4: إضافة نقاط البيانات

الآن، دعونا نضيف نقاط البيانات إلى سلسلة المخططات القمعية الخاصة بنا.

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

في هذه الخطوة، نقوم بإنشاء سلسلة للمخطط القمعي الخاص بنا ونضيف نقاط بيانات تمثل القيم في كل مرحلة من مراحل القمع.

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، نقوم بحفظ العرض التقديمي مع المخطط القمعي في ملف PowerPoint.

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 تأكد من استبدال`"Your Document Directory"` مع موقع الحفظ المطلوب.

## أكمل كود المصدر للمخطط القمعي في شرائح Java

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

في هذا البرنامج التعليمي، أوضحنا لك كيفية إنشاء مخطط قمع في Java Slides باستخدام Aspose.Slides لـ Java. يمكنك تخصيص المخطط بشكل أكبر عن طريق ضبط الألوان والتسميات والخصائص الأخرى لتناسب احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر المخطط القمعي؟

يمكنك تخصيص مظهر المخطط القمعي عن طريق تعديل خصائص المخطط والسلاسل ونقاط البيانات. راجع وثائق Aspose.Slides للحصول على خيارات التخصيص التفصيلية.

### هل يمكنني إضافة المزيد من الفئات أو نقاط البيانات إلى المخطط القمعي؟

نعم، يمكنك إضافة المزيد من الفئات ونقاط البيانات إلى المخطط القمعي عن طريق توسيع الكود في الخطوة 3 والخطوة 4 وفقًا لذلك.

### هل من الممكن تغيير نوع المخطط إلى شيء آخر غير مسار التحويل؟

 نعم، يدعم Aspose.Slides أنواعًا مختلفة من المخططات. يمكنك تغيير نوع المخطط عن طريق الاستبدال`ChartType.Funnel` مع نوع المخطط المطلوب في الخطوة 2.

### كيف أتعامل مع الأخطاء أو الاستثناءات أثناء العمل مع Aspose.Slides؟

يمكنك التعامل مع الأخطاء والاستثناءات باستخدام آليات معالجة استثناءات Java القياسية. تأكد من أن لديك معالجة صحيحة للأخطاء في التعليمات البرمجية الخاصة بك للتعامل مع المواقف غير المتوقعة بأمان.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟

 يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية حول استخدام Aspose.Slides لـ Java في[توثيق](https://docs.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
