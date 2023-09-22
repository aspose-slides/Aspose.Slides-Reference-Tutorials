---
title: رسم خطوط الاتجاه في شرائح جافا
linktitle: رسم خطوط الاتجاه في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة خطوط اتجاه متنوعة إلى Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية لتصور البيانات بشكل فعال.
type: docs
weight: 15
url: /ar/java/data-manipulation/chart-trend-lines-java-slides/
---

## مقدمة لخطوط اتجاه الرسم البياني في شرائح جافا: دليل خطوة بخطوة

في هذا الدليل الشامل، سوف نستكشف كيفية إنشاء خطوط اتجاه الرسم البياني في Java Slides باستخدام Aspose.Slides for Java. يمكن أن تكون خطوط اتجاه المخطط إضافة قيمة إلى عروضك التقديمية، مما يساعد على تصور اتجاهات البيانات وتحليلها بشكل فعال. سنرشدك خلال العملية بتفسيرات واضحة وأمثلة على التعليمات البرمجية.

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء خطوط اتجاه الرسم البياني، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة جافا
- محرر كود من اختيارك

## الخطوة 1: البدء

لنبدأ بإعداد البيئة اللازمة وإنشاء عرض تقديمي جديد:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
```

لقد قمنا بتهيئة العرض التقديمي الخاص بنا، ونحن الآن جاهزون لإضافة مخطط عمودي متفاوت المسافات:

```java
// إنشاء مخطط عمود متفاوت المسافات
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## الخطوة 2: إضافة خط الاتجاه الأسي

لنبدأ بإضافة خط الاتجاه الأسي إلى سلسلة الرسوم البيانية لدينا:

```java
// إضافة خط الاتجاه الأسي لسلسلة الرسم البياني 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## الخطوة 3: إضافة خط الاتجاه الخطي

بعد ذلك، سنقوم بإضافة خط اتجاه خطي إلى سلسلة الرسوم البيانية لدينا:

```java
//إضافة خط اتجاه خطي لسلسلة الرسم البياني 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 4: إضافة خط الاتجاه اللوغاريتمي

الآن، دعونا نضيف خط اتجاه لوغاريتمي إلى سلسلة مخططات مختلفة:

```java
// إضافة خط الاتجاه اللوغاريتمي لسلسلة المخططات 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## الخطوة 5: إضافة خط اتجاه المتوسط المتحرك

يمكننا أيضًا إضافة خط اتجاه متوسط متحرك:

```java
// إضافة خط اتجاه المتوسط المتحرك لسلسلة الرسم البياني 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## الخطوة 6: إضافة خط اتجاه كثير الحدود

إضافة خط اتجاه متعدد الحدود:

```java
// إضافة خط اتجاه متعدد الحدود لسلسلة المخططات 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## الخطوة 7: إضافة خط اتجاه الطاقة

وأخيرا، دعونا نضيف خط اتجاه القوة:

```java
// إضافة خط اتجاه الطاقة لسلسلة الرسم البياني 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## الخطوة 8: حفظ العرض التقديمي

الآن بعد أن أضفنا خطوط اتجاه مختلفة إلى مخططنا، فلنحفظ العرض التقديمي:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إنشاء عرض تقديمي بأنواع مختلفة من خطوط الاتجاه في Java Slides باستخدام Aspose.Slides for Java.

## كود المصدر الكامل لخطوط اتجاه الرسم البياني في شرائح جافا

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
// إنشاء مخطط عمود متفاوت المسافات
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
//إضافة خط اتجاه عوني لسلسلة الرسم البياني 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// إضافة خط الاتجاه الخطي لسلسلة المخططات 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// إضافة خط الاتجاه اللوغاريتمي لسلسلة المخططات 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// إضافة خط اتجاه المتوسط المتحرك لسلسلة الرسم البياني 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// إضافة خط اتجاه متعدد الحدود لسلسلة المخططات 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// إضافة خط اتجاه الطاقة لسلسلة الرسم البياني 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// حفظ العرض التقديمي
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة أنواع مختلفة من خطوط الاتجاه إلى المخططات في Java Slides باستخدام مكتبة Aspose.Slides for Java. سواء كنت تعمل على تحليل البيانات أو إنشاء عروض تقديمية غنية بالمعلومات، فإن القدرة على تصور الاتجاهات يمكن أن تكون أداة قوية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون خط الاتجاه في Aspose.Slides لـ Java؟

 لتغيير لون خط الاتجاه، يمكنك استخدام`getSolidFillColor().setColor(Color)` الطريقة، كما هو موضح في المثال لإضافة خط اتجاه خطي.

### هل يمكنني إضافة خطوط اتجاه متعددة إلى سلسلة مخططات واحدة؟

 نعم، يمكنك إضافة خطوط اتجاه متعددة إلى سلسلة مخططات واحدة. ما عليك سوى الاتصال بـ`getTrendLines().add()` طريقة لكل خط اتجاه تريد إضافته.

### كيف يمكنني إزالة خط الاتجاه من المخطط في Aspose.Slides لـ Java؟

 لإزالة خط الاتجاه من الرسم البياني، يمكنك استخدام`removeAt(int index)` الطريقة، مع تحديد مؤشر خط الاتجاه الذي تريد إزالته.

### هل من الممكن تخصيص عرض معادلة خط الاتجاه؟

 نعم، يمكنك تخصيص عرض معادلة خط الاتجاه باستخدام`setDisplayEquation(boolean)` الطريقة كما هو موضح في المثال

### كيف يمكنني الوصول إلى المزيد من الموارد والأمثلة لـ Aspose.Slides لـ Java؟

 يمكنك الوصول إلى موارد ووثائق وأمثلة إضافية لـ Aspose.Slides for Java على الموقع[موقع أسبوز](https://reference.aspose.com/slides/java/).