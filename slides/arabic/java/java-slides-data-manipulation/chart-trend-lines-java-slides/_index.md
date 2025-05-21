---
"description": "تعلّم كيفية إضافة خطوط اتجاه متنوعة إلى شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة برمجية لتصور البيانات بفعالية."
"linktitle": "خطوط اتجاه الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خطوط اتجاه الرسم البياني في شرائح Java"
"url": "/ar/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خطوط اتجاه الرسم البياني في شرائح Java


## مقدمة إلى خطوط اتجاه الرسم البياني في شرائح Java: دليل خطوة بخطوة

في هذا الدليل الشامل، سنستكشف كيفية إنشاء خطوط اتجاهات الرسوم البيانية في عروض جافا التقديمية باستخدام Aspose.Slides لجافا. تُعدّ خطوط اتجاهات الرسوم البيانية إضافة قيّمة لعروضك التقديمية، إذ تُساعد على تصوّر اتجاهات البيانات وتحليلها بفعالية. سنشرح لك العملية بالتفصيل مع شرح واضح وأمثلة برمجية.

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء خطوط اتجاه الرسم البياني، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة Java
- محرر الكود حسب اختيارك

## الخطوة 1: البدء

لنبدأ بإعداد البيئة اللازمة وإنشاء عرض تقديمي جديد:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
```

لقد قمنا بتهيئة عرضنا التقديمي، ونحن الآن جاهزون لإضافة مخطط عمودي مجمع:

```java
// إنشاء مخطط عمودي مجمع
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## الخطوة 2: إضافة خط الاتجاه الأسي

لنبدأ بإضافة خط اتجاه أسي إلى سلسلة الرسوم البيانية الخاصة بنا:

```java
// إضافة خط الاتجاه الأسّي لسلسلة الرسم البياني 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## الخطوة 3: إضافة خط الاتجاه الخطي

بعد ذلك، سنضيف خط اتجاه خطي إلى سلسلة الرسوم البيانية الخاصة بنا:

```java
// إضافة خط اتجاه خطي لسلسلة الرسم البياني 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## الخطوة 4: إضافة خط الاتجاه اللوغاريتمي

الآن، دعنا نضيف خط اتجاه لوغاريتمي إلى سلسلة مخططات بيانية مختلفة:

```java
// إضافة خط الاتجاه اللوغاريتمي لسلسلة الرسم البياني 2
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

## الخطوة 6: إضافة خط اتجاه متعدد الحدود

إضافة خط اتجاه متعدد الحدود:

```java
// إضافة خط اتجاه متعدد الحدود لسلسلة الرسم البياني 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## الخطوة 7: إضافة خط اتجاه الطاقة

وأخيرًا، دعونا نضيف خط اتجاه القوة:

```java
// إضافة خط اتجاه القوة لسلسلة الرسم البياني 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## الخطوة 8: حفظ العرض التقديمي

الآن بعد أن أضفنا خطوط الاتجاه المختلفة إلى الرسم البياني الخاص بنا، فلنحفظ العرض التقديمي:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إنشاء عرض تقديمي بأنواع مختلفة من خطوط الاتجاه في Java Slides باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل لخطوط اتجاه الرسم البياني في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
// إنشاء مخطط عمودي مجمع
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// إضافة خط الاتجاه المتزايد لسلسلة الرسم البياني 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// إضافة خط الاتجاه الخطي لسلسلة الرسم البياني 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// إضافة خط الاتجاه اللوغاريتمي لسلسلة الرسم البياني 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// إضافة خط اتجاه MovingAverage لسلسلة الرسم البياني 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// إضافة خط اتجاه متعدد الحدود لسلسلة الرسم البياني 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// إضافة خط اتجاه القوة لسلسلة الرسم البياني 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// حفظ العرض التقديمي
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة أنواع مختلفة من خطوط الاتجاهات إلى المخططات البيانية في Java Slides باستخدام مكتبة Aspose.Slides لـ Java. سواء كنت تعمل على تحليل البيانات أو تُنشئ عروضًا تقديمية غنية بالمعلومات، فإن القدرة على تصور الاتجاهات تُعدّ أداة فعّالة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون خط الاتجاه في Aspose.Slides لـ Java؟

لتغيير لون خط الاتجاه، يمكنك استخدام `getSolidFillColor().setColor(Color)` الطريقة، كما هو موضح في المثال لإضافة خط اتجاه خطي.

### هل يمكنني إضافة خطوط اتجاه متعددة إلى سلسلة مخطط واحد؟

نعم، يمكنك إضافة خطوط اتجاه متعددة إلى سلسلة مخططات بيانية واحدة. ما عليك سوى الاتصال بـ `getTrendLines().add()` طريقة لكل خط اتجاه تريد إضافته.

### كيف يمكنني إزالة خط الاتجاه من الرسم البياني في Aspose.Slides لـ Java؟

لإزالة خط الاتجاه من الرسم البياني، يمكنك استخدام `removeAt(int index)` الطريقة، تحديد مؤشر خط الاتجاه الذي تريد إزالته.

### هل من الممكن تخصيص عرض معادلة خط الاتجاه؟

نعم، يمكنك تخصيص عرض معادلة خط الاتجاه باستخدام `setDisplayEquation(boolean)` الطريقة كما هو موضح في المثال.

### كيف يمكنني الوصول إلى المزيد من الموارد والأمثلة لـ Aspose.Slides لـ Java؟

يمكنك الوصول إلى الموارد الإضافية والوثائق والأمثلة لـ Aspose.Slides for Java على [موقع Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}