---
title: مخطط متفرق في شرائح جافا
linktitle: مخطط متفرق في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات مبعثرة في Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع كود مصدر Java لتصور البيانات في العروض التقديمية.
weight: 11
url: /ar/java/chart-creation/scattered-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى المخططات المتفرقة في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط مبعثر باستخدام Aspose.Slides لـ Java. تعتبر المخططات المبعثرة مفيدة لتصور نقاط البيانات على مستوى ثنائي الأبعاد. سنقدم لك تعليمات خطوة بخطوة وسنقوم بتضمين كود مصدر Java لراحتك.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. [Aspose.Slides لجافا](https://products.aspose.com/slides/java) المثبتة.
2. تم إعداد بيئة تطوير Java.

## الخطوة 1: تهيئة العرض التقديمي

أولاً، قم باستيراد المكتبات الضرورية وإنشاء عرض تقديمي جديد.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// إنشاء عرض تقديمي جديد
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة شريحة وإنشاء المخطط المبعثر

 بعد ذلك، أضف شريحة وقم بإنشاء المخطط المبعثر عليها. سوف نستخدم`ScatterWithSmoothLines`نوع المخطط في هذا المثال.

```java
// احصل على الشريحة الأولى
ISlide slide = pres.getSlides().get_Item(0);

// إنشاء المخطط المبعثر
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## الخطوة 3: إعداد بيانات الرسم البياني

الآن، دعونا نجهز البيانات للمخطط المبعثر الخاص بنا. سنضيف سلسلتين، تحتوي كل منهما على نقاط بيانات متعددة.

```java
// الحصول على فهرس ورقة عمل بيانات المخطط الافتراضي
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// حذف السلسلة التجريبية
chart.getChartData().getSeries().clear();

// أضف السلسلة الأولى
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// إضافة نقاط البيانات إلى السلسلة الأولى
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// تحرير نوع السلسلة
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // تغيير حجم العلامة
series.getMarker().setSymbol(MarkerStyleType.Star); // تغيير رمز العلامة

// خذ سلسلة الرسم البياني الثاني
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

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع المخطط المبعثر في ملف PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط مبعثر باستخدام Aspose.Slides لـ Java. يمكنك الآن تخصيص هذا المثال بشكل أكبر ليناسب بياناتك المحددة ومتطلبات التصميم.

## أكمل كود المصدر للمخطط المتفرق في شرائح جافا
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//إنشاء المخطط الافتراضي
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// الحصول على فهرس ورقة عمل بيانات المخطط الافتراضي
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف السلسلة التجريبية
chart.getChartData().getSeries().clear();
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// أضف نقطة جديدة (1:3) هناك.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// إضافة نقطة جديدة (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// تحرير نوع السلسلة
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

في هذا البرنامج التعليمي، قمنا بإرشادك خلال عملية إنشاء مخطط مبعثر باستخدام Aspose.Slides لـ Java. تعد المخططات المبعثرة أدوات فعالة لتصور نقاط البيانات في مساحة ثنائية الأبعاد، مما يسهل تحليل علاقات البيانات المعقدة وفهمها.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

 لتغيير نوع المخطط، استخدم`setType` الطريقة على سلسلة المخططات وتوفير نوع المخطط المطلوب. على سبيل المثال،`series.setType(ChartType.Line)` سيغير السلسلة إلى مخطط خطي.

### كيف يمكنني تخصيص حجم العلامة ونمطها؟

 يمكنك تغيير حجم العلامة ونمطها باستخدام`getMarker` الطريقة على السلسلة ثم قم بتعيين الحجم وخصائص الرمز. على سبيل المثال:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

لا تتردد في استكشاف المزيد من خيارات التخصيص في وثائق Aspose.Slides لـ Java.

 تذكر أن تحل محل`"Your Document Directory"` بالمسار الفعلي الذي تريد حفظ العرض التقديمي فيه.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
