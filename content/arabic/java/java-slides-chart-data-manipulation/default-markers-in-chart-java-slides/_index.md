---
title: العلامات الافتراضية في المخطط في شرائح Java
linktitle: العلامات الافتراضية في المخطط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء شرائح Java باستخدام العلامات الافتراضية في المخططات باستخدام Aspose.Slides for Java. دليل خطوة بخطوة مع كود المصدر.
type: docs
weight: 16
url: /ar/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## مقدمة إلى العلامات الافتراضية في المخطط في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء مخطط باستخدام العلامات الافتراضية باستخدام Aspose.Slides لـ Java. العلامات الافتراضية هي رموز أو أشكال تتم إضافتها إلى نقاط البيانات في المخطط لتمييزها. سنقوم بإنشاء مخطط خطي بعلامات لتصور البيانات.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، لنقم بإنشاء عرض تقديمي وإضافة شريحة إليه. سنقوم بعد ذلك بإضافة مخطط إلى الشريحة.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## الخطوة 2: إضافة مخطط خطي مع علامات

الآن، دعونا نضيف مخططًا خطيًا بعلامات إلى الشريحة. سنقوم أيضًا بمسح أي بيانات افتراضية من المخطط.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## الخطوة 3: تعبئة بيانات المخطط

سنقوم بملء المخطط ببيانات نموذجية. في هذا المثال، سنقوم بإنشاء سلسلتين بنقاط البيانات والفئات.

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

// تعبئة بيانات السلسلة
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## الخطوة 4: تخصيص المخطط

يمكنك تخصيص المخطط بشكل أكبر، مثل إضافة وسيلة إيضاح وضبط مظهره.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع المخطط في الموقع الذي تريده.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد قمت بإنشاء مخطط خطي بعلامات افتراضية باستخدام Aspose.Slides لـ Java.

## أكمل كود المصدر للعلامات الافتراضية في المخطط في شرائح Java

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
            //الآن ملء بيانات السلسلة
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

في هذا البرنامج التعليمي الشامل، تعلمت كيفية إنشاء شرائح Java باستخدام العلامات الافتراضية في المخططات باستخدام Aspose.Slides for Java. لقد قمنا بتغطية العملية بأكملها، بدءًا من إعداد العرض التقديمي ووصولاً إلى تخصيص مظهر المخطط وحفظ النتيجة.

## الأسئلة الشائعة

### كيف يمكنني تغيير رموز العلامة؟

يمكنك تخصيص رموز العلامة عن طريق تعيين نمط العلامة لكل نقطة بيانات. يستخدم`IDataPoint.setMarkerStyle()` لتغيير رمز العلامة.

### كيف يمكنني ضبط ألوان المخطط؟

 لتعديل ألوان المخطط، يمكنك استخدام`IChartSeriesFormat` و`IShapeFillFormat` واجهات لتعيين خصائص التعبئة والخط.

### هل يمكنني إضافة تسميات إلى نقاط البيانات؟

 نعم، يمكنك إضافة تسميات إلى نقاط البيانات باستخدام`IDataPoint.getLabel()` الطريقة وتخصيصها حسب الحاجة.