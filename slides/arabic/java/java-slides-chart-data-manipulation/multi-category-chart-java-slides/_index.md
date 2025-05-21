---
"description": "أنشئ مخططات متعددة الفئات في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لعرض بيانات مُبهر في العروض التقديمية."
"linktitle": "مخطط متعدد الفئات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط متعدد الفئات في شرائح Java"
"url": "/ar/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط متعدد الفئات في شرائح Java


## مقدمة إلى مخططات الفئات المتعددة في Java Slides باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سنتعلم كيفية إنشاء مخطط بياني متعدد الفئات في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. سيقدم هذا الدليل تعليمات خطوة بخطوة، بالإضافة إلى شيفرة المصدر، لمساعدتك في إنشاء مخطط بياني عمودي مجمع بفئات وسلاسل بيانات متعددة.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في بيئة تطوير Java الخاصة بك.

## الخطوة 1: إعداد البيئة
أولاً، قم باستيراد الفئات الضرورية وإنشاء كائن عرض تقديمي جديد للعمل مع الشرائح.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة شريحة ومخطط
بعد ذلك، قم بإنشاء شريحة وأضف إليها مخططًا عموديًا مجمعًا.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## الخطوة 3: مسح البيانات الموجودة
مسح أي بيانات موجودة من الرسم البياني.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## الخطوة 4: إعداد فئات البيانات
الآن، لنُنشئ فئات بيانات للرسم البياني. سنُنشئ فئات متعددة ونُجمّعها.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// إضافة الفئات وتجميعها
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
الآن، دعنا نضيف سلسلة إلى الرسم البياني مع نقاط البيانات.

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
وأخيرًا، احفظ العرض التقديمي مع الرسم البياني.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط متعدد الفئات في شريحة جافا باستخدام Aspose.Slides. يمكنك تخصيص هذا المخطط بشكل أكبر ليناسب احتياجاتك الخاصة.

## الكود المصدر الكامل للمخطط متعدد الفئات في شرائح Java

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
//            إضافة سلسلة
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

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخطط متعدد الفئات في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. اتبعنا دليلاً خطوة بخطوة مع الكود المصدري لإنشاء مخطط عمودي مجمع بفئات وسلاسل متعددة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر الرسم البياني؟

يمكنك تخصيص مظهر المخطط بتعديل خصائص مثل الألوان والخطوط والأنماط. راجع وثائق Aspose.Slides للاطلاع على خيارات التخصيص المفصلة.

### هل يمكنني إضافة المزيد من السلاسل إلى الرسم البياني؟

نعم، يمكنك إضافة سلسلة إضافية إلى الرسم البياني باتباع عملية مماثلة كما هو موضح في الخطوة 5.

### كيف يمكنني تغيير نوع الرسم البياني؟

لتغيير نوع الرسم البياني، استبدل `ChartType.ClusteredColumn` مع نوع الرسم البياني المطلوب عند إضافة الرسم البياني في الخطوة 2.

### كيف يمكنني إضافة عنوان إلى الرسم البياني؟

يمكنك إضافة عنوان إلى الرسم البياني باستخدام `ch.getChartTitle().getTextFrame().setText("Chart Title");` طريقة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}