---
"description": "تعلّم كيفية إنشاء مخططات التشتت في جافا باستخدام Aspose.Slides. دليل خطوة بخطوة مع شفرة المصدر بلغة جافا لعرض البيانات في العروض التقديمية."
"linktitle": "مخطط مبعثر في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط مبعثر في شرائح جافا"
"url": "/ar/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط مبعثر في شرائح جافا


## مقدمة إلى المخططات المتناثرة في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط تشتت باستخدام Aspose.Slides في جافا. تُعدّ مخططات التشتت مفيدة لعرض نقاط البيانات على مستوى ثنائي الأبعاد. سنقدم تعليمات خطوة بخطوة، وسنضيف شفرة مصدر جافا لتسهيل الأمر عليك.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. [Aspose.Slides لـ Java](https://products.aspose.com/slides/java) تم تثبيته.
2. تم إعداد بيئة تطوير Java.

## الخطوة 1: تهيئة العرض التقديمي

أولاً، قم باستيراد المكتبات الضرورية وإنشاء عرض تقديمي جديد.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// إنشاء عرض تقديمي جديد
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة شريحة وإنشاء مخطط التشتت

بعد ذلك، أضف شريحة وأنشئ مخطط التشتت عليها. سنستخدم `ScatterWithSmoothLines` نوع الرسم البياني في هذا المثال.

```java
// احصل على الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);

// إنشاء مخطط التشتت
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## الخطوة 3: تحضير بيانات الرسم البياني

الآن، لنُعِدّ بيانات مخطط التشتت. سنضيف سلسلتين، تحتوي كل منهما على نقاط بيانات متعددة.

```java
// الحصول على فهرس ورقة عمل بيانات الرسم البياني الافتراضية
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// حذف سلسلة العروض التوضيحية
chart.getChartData().getSeries().clear();

// أضف السلسلة الأولى
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// إضافة نقاط البيانات إلى السلسلة الأولى
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// تعديل نوع السلسلة
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // تغيير حجم العلامة
series.getMarker().setSymbol(MarkerStyleType.Star); // تغيير رمز العلامة

// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);

// إضافة نقاط البيانات إلى السلسلة الثانية
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// تغيير نمط العلامة للسلسلة الثانية
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## الخطوة 4: حفظ العرض التقديمي

أخيرًا، احفظ العرض التقديمي مع مخطط التشتت في ملف PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد أنشأتَ بنجاح مخططًا تشتتًا باستخدام Aspose.Slides لجافا. يمكنك الآن تخصيص هذا المثال بشكل أكبر ليناسب بياناتك ومتطلبات تصميمك.

## كود المصدر الكامل للمخططات المتناثرة في شرائح Java
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// إنشاء الرسم البياني الافتراضي
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// الحصول على فهرس ورقة عمل بيانات الرسم البياني الافتراضية
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف سلسلة العروض التوضيحية
chart.getChartData().getSeries().clear();
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// خذ أول سلسلة مخططات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// أضف نقطة جديدة (1:3) هناك.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// إضافة نقطة جديدة (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// تعديل نوع السلسلة
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// تغيير علامة سلسلة الرسم البياني
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// أضف نقطة جديدة (5:2) هناك.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// إضافة نقطة جديدة (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// إضافة نقطة جديدة (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// إضافة نقطة جديدة (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// تغيير علامة سلسلة الرسم البياني
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، شرحنا لك عملية إنشاء مخطط تشتت باستخدام Aspose.Slides لجافا. تُعد مخططات التشتت أدوات فعّالة لعرض نقاط البيانات في مساحة ثنائية الأبعاد، مما يُسهّل تحليل وفهم علاقات البيانات المعقدة.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

لتغيير نوع الرسم البياني، استخدم `setType` استخدم طريقةً لسلسلة المخططات البيانية، وحدد نوع المخطط المطلوب. على سبيل المثال، `series.setType(ChartType.Line)` سيتم تغيير السلسلة إلى مخطط خطي.

### كيف يمكنني تخصيص حجم ونمط العلامة؟

يمكنك تغيير حجم العلامة ونمطها باستخدام `getMarker` على السلسلة، ثم اضبط خصائص الحجم والرمز. على سبيل المثال:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

لا تتردد في استكشاف المزيد من خيارات التخصيص في وثائق Aspose.Slides لـ Java.

تذكر أن تستبدل `"Your Document Directory"` مع المسار الفعلي الذي تريد حفظ العرض التقديمي فيه.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}