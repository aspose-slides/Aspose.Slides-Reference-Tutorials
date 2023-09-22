---
title: عكس إذا كان سلبيا للسلسلة الفردية في شرائح جافا
linktitle: عكس إذا كان سلبيا للسلسلة الفردية في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية استخدام ميزة Invert If Negative في Aspose.Slides لـ Java لتحسين مرئيات المخطط في عروض PowerPoint التقديمية.
type: docs
weight: 11
url: /ar/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## مقدمة إلى عكس إذا كان سلبيًا للسلسلة الفردية في شرائح Java

يوفر Aspose.Slides for Java أدوات قوية للعمل مع العروض التقديمية، وإحدى الميزات المثيرة للاهتمام هي القدرة على التحكم في كيفية عرض سلاسل البيانات على المخططات. في هذه المقالة، سوف نستكشف كيفية استخدام ميزة "عكس إذا كان سلبيًا" للسلاسل الفردية في شرائح Java. تسمح لك هذه الميزة بالتمييز بصريًا بين نقاط البيانات السلبية في المخطط، مما يجعل عروضك التقديمية أكثر إفادة وجاذبية.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## إعداد مشروعك

للبدء، قم بإنشاء مشروع Java جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. بمجرد إعداد مشروعك، اتبع هذه الخطوات لتنفيذ ميزة "عكس إذا كان سلبيًا" للسلسلة الفردية في Java Slides.

## الخطوة 1: تضمين مكتبة Aspose.Slides

أولاً، تحتاج إلى تضمين مكتبة Aspose.Slides في مشروعك. يمكنك القيام بذلك عن طريق إضافة ملف JAR للمكتبة إلى مسار الفصل الخاص بمشروعك. تضمن هذه الخطوة أنه يمكنك الوصول إلى جميع الفئات والأساليب اللازمة للعمل مع عروض PowerPoint التقديمية.

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء عرض تقديمي

 الآن، لنقم بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides. يمكنك تحديد الدليل الذي تريد حفظ العرض التقديمي فيه باستخدام ملف`dataDir` عامل.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 3: إضافة مخطط

في هذه الخطوة، سنقوم بإضافة مخطط إلى العرض التقديمي. سنستخدم مخططًا عموديًا متفاوت المسافات كمثال. يمكنك اختيار أنواع مختلفة من المخططات بناءً على متطلباتك.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## الخطوة 4: تكوين سلسلة بيانات المخطط

بعد ذلك، سنقوم بتكوين سلسلة بيانات المخطط. لتوضيح ميزة "عكس حالة السلبية"، سنقوم بإنشاء مجموعة بيانات نموذجية تحتوي على قيم إيجابية وسلبية.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// إضافة نقاط البيانات إلى السلسلة
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## الخطوة 5: تطبيق "عكس إذا كان سلبيًا"

الآن، سنقوم بتطبيق ميزة "عكس حالة السلبية" على إحدى نقاط البيانات. سيؤدي هذا إلى عكس لون نقطة البيانات المحددة هذه بشكل مرئي عندما تكون سلبية.

```java
series.get_Item(0).setInvertIfNegative(false); // لا تقلب بشكل افتراضي
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // عكس اللون لنقطة البيانات الثالثة
```

## الخطوة 6: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في الدليل المحدد لديك.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل للعكس إذا كان سلبيًا للسلسلة الفردية في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام ميزة "Invert If Negative" للسلاسل الفردية في Java Slides باستخدام Aspose.Slides for Java. تسمح لك هذه الميزة بتسليط الضوء على نقاط البيانات السلبية في مخططاتك، مما يجعل عروضك التقديمية أكثر جاذبية وغنية بالمعلومات.

## الأسئلة الشائعة

### ما هو الغرض من ميزة "عكس حالة السلبية" في Aspose.Slides لـ Java؟

تتيح لك ميزة "عكس حالة السلبية" الموجودة في Aspose.Slides لـ Java التمييز بصريًا بين نقاط البيانات السلبية في المخططات. فهو يساعد في جعل عروضك التقديمية أكثر إفادة وجاذبية من خلال تسليط الضوء على نقاط بيانات محددة.

### كيف يمكنني تضمين مكتبة Aspose.Slides في مشروع Java الخاص بي؟

لتضمين مكتبة Aspose.Slides في مشروع Java الخاص بك، تحتاج إلى إضافة ملف JAR الخاص بالمكتبة إلى مسار الفصل الخاص بمشروعك. يمكّنك هذا من الوصول إلى جميع الفئات والأساليب اللازمة للعمل مع عروض PowerPoint التقديمية.

### هل يمكنني استخدام أنواع مختلفة من المخططات مع ميزة "عكس حالة السلبية"؟

نعم، يمكنك استخدام أنواع مختلفة من المخططات مع ميزة "عكس حالة السلبية". في هذا البرنامج التعليمي، استخدمنا مخططًا عموديًا متفاوت المسافات كمثال، ولكن يمكنك تطبيق الميزة على أنواع المخططات المختلفة بناءً على متطلباتك.

### هل من الممكن تخصيص مظهر نقاط البيانات المقلوبة؟

نعم، يمكنك تخصيص مظهر نقاط البيانات المقلوبة. يوفر Aspose.Slides for Java خيارات للتحكم في لون ونمط نقاط البيانات عندما تكون مقلوبة بسبب الإعداد "Invert If Negative".

### أين يمكنني الوصول إلى وثائق Aspose.Slides الخاصة بـ Java؟

 يمكنك الوصول إلى وثائق Aspose.Slides for Java على[هنا](https://reference.aspose.com/slides/java/).