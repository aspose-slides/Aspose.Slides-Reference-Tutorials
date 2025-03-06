---
title: الرسم البياني في شرائح جافا
linktitle: الرسم البياني في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات الرسم البياني في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري لتصور البيانات.
weight: 19
url: /ar/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة إلى الرسم البياني في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط مدرج تكراري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java API. يتم استخدام مخطط الرسم البياني لتمثيل توزيع البيانات على فترة زمنية مستمرة.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java. يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة مشروعك

قم بإنشاء مشروع Java وقم بتضمين مكتبة Aspose.Slides في تبعيات مشروعك.

## الخطوة 2: استيراد المكتبات الضرورية

```java
import com.aspose.slides.*;
```

## الخطوة 3: قم بتحميل عرض تقديمي موجود

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي لمستند PowerPoint الخاص بك.

## الخطوة 4: إنشاء مخطط الرسم البياني

الآن، لنقم بإنشاء مخطط مدرج تكراري على شريحة في العرض التقديمي.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // إضافة نقاط البيانات إلى السلسلة
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // قم بتعيين نوع تجميع المحور الأفقي على تلقائي
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // احفظ العرض التقديمي
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 في هذا الكود، نقوم أولاً بمسح أي فئات وسلاسل موجودة من المخطط. ثم نضيف نقاط البيانات إلى السلسلة باستخدام`getDataPoints().addDataPointForHistogramSeries` طريقة. أخيرًا، قمنا بتعيين نوع تجميع المحور الأفقي على "تلقائي" وحفظ العرض التقديمي.

## أكمل كود المصدر لمخطط الرسم البياني في شرائح جافا

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إنشاء مخطط مدرج تكراري في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java API. تعد مخططات المدرج التكراري أدوات قيمة لتصور توزيع البيانات على مدى فترة زمنية متواصلة، ويمكن أن تكون إضافة قوية لعروضك التقديمية، خاصة عند التعامل مع المحتوى الإحصائي أو التحليلي.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

 يمكنك تنزيل مكتبة Aspose.Slides for Java من[هنا](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المتوفرة على موقعه على الانترنت.

### ما هو مخطط الرسم البياني المستخدم؟

يتم استخدام مخطط الرسم البياني لتصور توزيع البيانات على مدى فترة زمنية مستمرة. يُستخدم بشكل شائع في الإحصائيات لتمثيل التوزيعات التكرارية.

### هل يمكنني تخصيص مظهر مخطط الرسم البياني؟

نعم، يمكنك تخصيص مظهر المخطط، بما في ذلك ألوانه وتسمياته ومحاوره، باستخدام Aspose.Slides API.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
