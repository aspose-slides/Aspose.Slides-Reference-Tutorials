---
"description": "تعرّف على كيفية إنشاء مخططات الهيستوغرام في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لتصور البيانات."
"linktitle": "مخطط الهيستوغرام في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط الهيستوغرام في شرائح جافا"
"url": "/ar/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط الهيستوغرام في شرائح جافا


## مقدمة إلى مخطط الهيستوغرام في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط هيستوغرام في عرض تقديمي على PowerPoint باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. يُستخدم مخطط الهيستوغرام لتمثيل توزيع البيانات على فترة زمنية متصلة.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [موقع Aspose](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة مشروعك

قم بإنشاء مشروع Java وقم بتضمين مكتبة Aspose.Slides في تبعيات مشروعك.

## الخطوة 2: استيراد المكتبات الضرورية

```java
import com.aspose.slides.*;
```

## الخطوة 3: تحميل عرض تقديمي موجود

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

تأكد من الاستبدال `"Your Document Directory"` مع المسار الفعلي إلى مستند PowerPoint الخاص بك.

## الخطوة 4: إنشاء مخطط الهيستوجرام

الآن، دعنا نقوم بإنشاء مخطط الهيستوجرام على شريحة في العرض التقديمي.

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
    
    // تعيين نوع تجميع المحور الأفقي إلى تلقائي
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // حفظ العرض التقديمي
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

في هذا الكود، نقوم أولًا بمسح أي فئات وسلاسل موجودة من الرسم البياني. ثم نضيف نقاط بيانات إلى السلسلة باستخدام `getDataPoints().addDataPointForHistogramSeries` أخيرًا، قمنا بتعيين نوع تجميع المحور الأفقي إلى "تلقائي" وحفظ العرض التقديمي.

## كود المصدر الكامل لمخطط الهيستوجرام في شرائح جافا

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

في هذا البرنامج التعليمي، استكشفنا كيفية إنشاء مخطط هيستوغرام في عرض تقديمي على PowerPoint باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. تُعد مخططات الهيستوغرام أدوات قيّمة لتصور توزيع البيانات على فترات زمنية متصلة، ويمكن أن تُشكل إضافة فعّالة لعروضك التقديمية، خاصةً عند التعامل مع محتوى إحصائي أو تحليلي.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

يمكنك تنزيل مكتبة Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المقدمة على موقعهم الإلكتروني.

### ما هو استخدام مخطط الهيستوجرام؟

يُستخدم مخطط الهيستوغرام لتصوير توزيع البيانات على فترة زمنية متصلة. ويُستخدم عادةً في الإحصاءات لتمثيل توزيعات التكرار.

### هل يمكنني تخصيص مظهر مخطط الهيستوجرام؟

نعم، يمكنك تخصيص مظهر الرسم البياني، بما في ذلك ألوانه وعلاماته ومحاوره، باستخدام واجهة برمجة التطبيقات Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}