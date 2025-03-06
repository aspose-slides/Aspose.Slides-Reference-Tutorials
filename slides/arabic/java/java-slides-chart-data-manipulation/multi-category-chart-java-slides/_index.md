---
title: مخطط متعدد الفئات في شرائح جافا
linktitle: مخطط متعدد الفئات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بإنشاء مخططات متعددة الفئات في شرائح Java باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع التعليمات البرمجية المصدر لتصور البيانات بشكل مثير للإعجاب في العروض التقديمية.
weight: 20
url: /ar/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة إلى المخطط متعدد الفئات في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سوف نتعلم كيفية إنشاء مخطط متعدد الفئات في شرائح Java باستخدام Aspose.Slides for Java API. سيوفر هذا الدليل إرشادات خطوة بخطوة بالإضافة إلى التعليمات البرمجية المصدر لمساعدتك في إنشاء مخطط عمودي متفاوت المسافات مع فئات وسلاسل متعددة.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في بيئة تطوير Java لديك.

## الخطوة 1: إعداد البيئة
أولاً، قم باستيراد الفئات الضرورية وإنشاء كائن عرض تقديمي جديد للعمل مع الشرائح.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط
بعد ذلك، قم بإنشاء شريحة وأضف إليها مخططًا عموديًا متفاوت المسافات.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## الخطوة 3: مسح البيانات الموجودة
امسح أي بيانات موجودة من المخطط.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## الخطوة 4: إعداد فئات البيانات
الآن، لنقم بإعداد فئات البيانات للمخطط. سنقوم بإنشاء فئات متعددة ونجمعها.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// إضافة فئات وتجميعها
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## الخطوة 5: إضافة السلسلة
الآن، دعونا نضيف سلسلة إلى المخطط مع نقاط البيانات.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## الخطوة 6: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي مع المخطط.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط متعدد الفئات في شريحة Java باستخدام Aspose.Slides. يمكنك تخصيص هذا المخطط بشكل أكبر ليناسب متطلباتك المحددة.

## أكمل كود المصدر للمخطط متعدد الفئات في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// إضافة سلسلة
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// حفظ العرض التقديمي مع الرسم البياني
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخطط متعدد الفئات في شرائح Java باستخدام Aspose.Slides for Java API. لقد مررنا بدليل خطوة بخطوة مع التعليمات البرمجية المصدر لإنشاء مخطط عمودي متفاوت المسافات مع فئات وسلاسل متعددة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر الرسم البياني؟

يمكنك تخصيص مظهر المخطط عن طريق تعديل الخصائص مثل الألوان والخطوط والأنماط. راجع وثائق Aspose.Slides للحصول على خيارات التخصيص التفصيلية.

### هل يمكنني إضافة المزيد من السلاسل إلى المخطط؟

نعم، يمكنك إضافة سلسلة إضافية إلى المخطط باتباع عملية مشابهة كما هو موضح في الخطوة 5.

### كيف يمكنني تغيير نوع المخطط؟

 لتغيير نوع المخطط، استبدل`ChartType.ClusteredColumn` بنوع المخطط المطلوب عند إضافة المخطط في الخطوة 2.

### كيف يمكنني إضافة عنوان إلى الرسم البياني؟

 يمكنك إضافة عنوان إلى المخطط باستخدام`ch.getChartTitle().getTextFrame().setText("Chart Title");` طريقة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
