---
"description": "تعلّم كيفية إنشاء شرائح جافا مع علامات افتراضية في الرسوم البيانية باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدر."
"linktitle": "العلامات الافتراضية في الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "العلامات الافتراضية في الرسم البياني في شرائح Java"
"url": "/ar/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# العلامات الافتراضية في الرسم البياني في شرائح Java


## مقدمة عن العلامات الافتراضية في المخططات في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء مخطط بياني بعلامات افتراضية باستخدام Aspose.Slides لجافا. العلامات الافتراضية هي رموز أو أشكال تُضاف إلى نقاط البيانات في المخطط لتمييزها. سننشئ مخططًا خطيًا بعلامات لعرض البيانات.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، لنُنشئ عرضًا تقديميًا ونُضيف شريحةً إليه. ثم سنُضيف مخططًا إلى الشريحة.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## الخطوة 2: إضافة مخطط خطي مع علامات

الآن، لنُضِف مخططًا خطيًا مع علامات إلى الشريحة. سنمسح أيضًا أي بيانات افتراضية من المخطط.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## الخطوة 3: ملء بيانات الرسم البياني

سنملأ الرسم البياني ببيانات نموذجية. في هذا المثال، سننشئ سلسلتين تحتويان على نقاط بيانات وفئات.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// السلسلة 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// السلسلة 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// ملء بيانات السلسلة
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## الخطوة 4: تخصيص الرسم البياني

يمكنك تخصيص الرسم البياني بشكل أكبر، مثل إضافة أسطورة وتعديل مظهره.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع الرسم البياني في الموقع المطلوب.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد أنشأتَ مخططًا خطيًا بعلامات افتراضية باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل للعلامات الافتراضية في الرسم البياني في شرائح Java

```java
        // المسار إلى دليل المستندات.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //خذ سلسلة الرسم البياني الثانية
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //يتم الآن ملء بيانات السلسلة
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## خاتمة

في هذا البرنامج التعليمي الشامل، تعلمت كيفية إنشاء شرائح جافا مع علامات افتراضية في المخططات باستخدام Aspose.Slides لجافا. غطينا العملية بأكملها، من إعداد عرض تقديمي إلى تخصيص مظهر المخطط وحفظ النتيجة.

## الأسئلة الشائعة

### كيف يمكنني تغيير رموز العلامة؟

يمكنك تخصيص رموز العلامات عن طريق ضبط نمط العلامة لكل نقطة بيانات. استخدم `IDataPoint.setMarkerStyle()` لتغيير رمز العلامة.

### كيف يمكنني تعديل ألوان الرسم البياني؟

لتعديل ألوان الرسم البياني، يمكنك استخدام `IChartSeriesFormat` و `IShapeFillFormat` واجهات لتعيين خصائص التعبئة والخط.

### هل يمكنني إضافة تسميات إلى نقاط البيانات؟

نعم، يمكنك إضافة تسميات إلى نقاط البيانات باستخدام `IDataPoint.getLabel()` الطريقة وتخصيصها حسب الحاجة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}