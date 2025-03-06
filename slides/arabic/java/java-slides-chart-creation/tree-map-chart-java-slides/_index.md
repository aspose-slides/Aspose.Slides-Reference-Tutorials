---
title: مخطط خريطة الشجرة في شرائح جافا
linktitle: مخطط خريطة الشجرة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بإنشاء مخططات خريطة الشجرة في شرائح Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع التعليمات البرمجية المصدر لتصور البيانات الهرمية.
weight: 13
url: /ar/java/chart-creation/tree-map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة إلى مخطط خريطة الشجرة في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية إنشاء مخطط Tree Map في عرض تقديمي لـ PowerPoint باستخدام مكتبة Aspose.Slides for Java. تعد مخططات الخريطة الشجرية طريقة فعالة لتصور البيانات الهرمية.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من إعداد مكتبة Aspose.Slides for Java في مشروع Java الخاص بك.

## الخطوة 1: استيراد المكتبات المطلوبة

```java
import com.aspose.slides.*;
```

## الخطوة 2: قم بتحميل العرض التقديمي

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 3: إنشاء مخطط خريطة شجرة

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // إنشاء فرع 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // إنشاء فرع 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // إضافة نقاط البيانات
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // احفظ العرض التقديمي باستخدام مخطط الخريطة الشجرةية
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## أكمل كود المصدر لمخطط خريطة الشجرة في شرائح جافا
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//فرع 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//فرع 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط شجرة في عرض تقديمي لـ PowerPoint باستخدام مكتبة Aspose.Slides for Java. تعد مخططات الخريطة الشجرية أداة قيمة لتصور البيانات الهرمية، مما يجعل عروضك التقديمية أكثر إفادة وجاذبية.

## الأسئلة الشائعة

### كيف أقوم بإضافة بيانات إلى مخطط الخريطة الشجرةية؟

 لإضافة بيانات إلى مخطط الشجرة، استخدم`series.getDataPoints().addDataPointForTreemapSeries()` طريقة تمرير قيم البيانات كمعلمات.

### كيف يمكنني تخصيص مظهر مخطط الخريطة الشجرةية؟

 يمكنك تخصيص مظهر مخطط الخريطة الشجرةية عن طريق تعديل خصائص مختلفة للمخطط`chart` و`series`الكائنات، مثل الألوان والتسميات والتخطيطات.

### هل يمكنني إنشاء مخططات خريطة شجرة متعددة في عرض تقديمي واحد؟

نعم، يمكنك إنشاء مخططات متعددة للخريطة الشجرية في عرض تقديمي واحد عن طريق اتباع نفس الخطوات وتحديد مواضع شرائح مختلفة.

### كيف يمكنني حفظ العرض التقديمي باستخدام مخطط الخريطة الشجرةية؟

 استخدم ال`pres.save()` طريقة لحفظ العرض التقديمي باستخدام مخطط Tree Map بالتنسيق المطلوب (على سبيل المثال، PPTX).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
