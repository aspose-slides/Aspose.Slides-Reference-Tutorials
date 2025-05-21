---
"description": "تعرّف على كيفية تخصيص المخططات البيانية في Java Slides باستخدام Aspose.Slides لـ Java. استكشف خيارات المخططات البيانية الإضافية وحسّن عروضك التقديمية."
"linktitle": "خيارات الرسم البياني الثانية للمخططات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خيارات الرسم البياني الثانية للمخططات في شرائح Java"
"url": "/ar/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خيارات الرسم البياني الثانية للمخططات في شرائح Java


## مقدمة لخيارات الرسم البياني الثاني للمخططات في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إضافة خيارات رسم بياني ثانوية إلى المخططات البيانية باستخدام Aspose.Slides في جافا. تتيح لك هذه الخيارات تخصيص مظهر وسلوك المخططات البيانية، خاصةً في سيناريوهات مثل المخططات الدائرية. سنقدم تعليمات خطوة بخطوة وأمثلة من الكود المصدري لتحقيق ذلك. 

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

## الخطوة 2: إضافة مخطط إلى شريحة
بعد ذلك، سنضيف مخططًا إلى شريحة. في هذا المثال، سننشئ مخططًا دائريًا:

```java
// إضافة مخطط على الشريحة
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## الخطوة 3: تخصيص خصائص الرسم البياني
الآن، دعنا نحدد خصائص مختلفة للرسم البياني، بما في ذلك خيارات الرسم البياني الثانية:

```java
// إظهار تسميات البيانات للسلسلة الأولى
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// ضبط حجم الفطيرة الثانية (بالنسبة المئوية)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// تقسيم الفطيرة حسب النسبة المئوية
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// تعيين موضع الانقسام
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## الخطوة 4: حفظ العرض التقديمي
أخيرًا، احفظ العرض التقديمي باستخدام المخطط وخيارات الرسم البياني الثاني:

```java
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لخيارات الرسم البياني الثاني

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

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة خيارات رسم ثانوية إلى المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك تخصيص خصائص متنوعة لتحسين مظهر ووظائف مخططاتك، مما يجعل عروضك التقديمية أكثر إفادة وجاذبية بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تغيير حجم الفطيرة الثانية في مخطط فطيرة؟

لتغيير حجم الفطيرة الثانية في مخطط فطيرة، استخدم `setSecondPieSize` الطريقة كما هو موضح في مثال الكود أعلاه. اضبط القيمة لتحديد الحجم كنسبة مئوية.

### ماذا يفعل `PieSplitBy` التحكم في مخطط دائري؟

ال `PieSplitBy` تتحكم الخاصية في كيفية تقسيم المخطط الدائري. يمكنك ضبطها على `PieSplitType.ByPercentage` أو `PieSplitType.ByValue` لتقسيم الرسم البياني حسب النسبة المئوية أو حسب قيمة محددة، على التوالي.

### كيف أقوم بتعيين موضع التقسيم في مخطط فطيرة؟

يمكنك تعيين موضع التقسيم في مخطط دائري باستخدام `setPieSplitPosition` الطريقة. اضبط القيمة لتحديد الموضع المطلوب.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}