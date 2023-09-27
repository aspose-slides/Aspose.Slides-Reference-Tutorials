---
title: خيارات المؤامرة الثانية للمخططات في شرائح جافا
linktitle: خيارات المؤامرة الثانية للمخططات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تخصيص المخططات في Java Slides باستخدام Aspose.Slides لـ Java. استكشف خيارات الحبكة الثانية وحسّن عروضك التقديمية.
type: docs
weight: 12
url: /ar/java/chart-creation/second-plot-options-charts-java-slides/
---

## مقدمة إلى خيارات الرسم الثاني للمخططات في شرائح جافا

في هذا البرنامج التعليمي، سوف نستكشف كيفية إضافة خيارات الرسم الثاني إلى المخططات باستخدام Aspose.Slides لـ Java. تسمح لك خيارات الرسم الثاني بتخصيص مظهر المخططات وسلوكها، خاصة في سيناريوهات مثل المخططات الدائرية الدائرية. سنقدم تعليمات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر لتحقيق ذلك. 

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من تثبيت Aspose.Slides for Java وإعداده في مشروع Java الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي
لنبدأ بإنشاء عرض تقديمي جديد:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة
بعد ذلك، سنضيف مخططًا إلى الشريحة. في هذا المثال، سنقوم بإنشاء مخطط دائري دائري:

```java
// إضافة مخطط على الشريحة
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## الخطوة 3: تخصيص خصائص المخطط
الآن، لنقم بتعيين خصائص مختلفة للمخطط، بما في ذلك خيارات الرسم الثاني:

```java
// إظهار تسميات البيانات للسلسلة الأولى
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// ضبط حجم الفطيرة الثانية (بالنسبة المئوية)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// قم بتقسيم الفطيرة بنسبة مئوية
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// اضبط موضع الانقسام
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## الخطوة 4: احفظ العرض التقديمي
أخيرًا، احفظ العرض التقديمي مع المخطط وخيارات الرسم الثاني:

```java
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لخيارات قطعة الأرض الثانية

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// إضافة مخطط على الشريحة
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// تعيين خصائص مختلفة
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة خيارات الرسم الثاني إلى المخططات في Java Slides باستخدام Aspose.Slides for Java. يمكنك تخصيص خصائص متنوعة لتحسين مظهر مخططاتك ووظائفها، مما يجعل عروضك التقديمية أكثر إفادة وجاذبية من الناحية المرئية.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم الفطيرة الثانية في مخطط الفطيرة الدائرية؟

 لتغيير حجم الفطيرة الثانية في المخطط الدائري الدائري، استخدم`setSecondPieSize` الطريقة كما هو موضح في مثال الكود أعلاه. اضبط القيمة لتحديد الحجم بالنسبة المئوية.

###  ماذا فعلت`PieSplitBy` control in a Pie of Pie chart?

 ال`PieSplitBy`تتحكم الخاصية في كيفية تقسيم المخطط الدائري. يمكنك ضبطه على أي منهما`PieSplitType.ByPercentage` أو`PieSplitType.ByValue` لتقسيم المخطط حسب النسبة المئوية أو بقيمة محددة، على التوالي.

### كيف أقوم بتعيين موضع الانقسام في مخطط دائري؟

 يمكنك ضبط موضع الانقسام في المخطط الدائري الدائري باستخدام`setPieSplitPosition` طريقة. اضبط القيمة لتحديد الموضع المطلوب.