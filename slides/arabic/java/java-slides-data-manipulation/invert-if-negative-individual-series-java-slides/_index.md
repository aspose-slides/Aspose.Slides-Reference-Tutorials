---
"description": "تعرف على كيفية استخدام ميزة \"عكس إذا كان سلبيًا\" في Aspose.Slides لـ Java لتحسين صور المخططات في عروض PowerPoint التقديمية."
"linktitle": "عكس إذا كان سلبيًا لسلسلة فردية في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "عكس إذا كان سلبيًا لسلسلة فردية في شرائح Java"
"url": "/ar/java/data-manipulation/invert-if-negative-individual-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# عكس إذا كان سلبيًا لسلسلة فردية في شرائح Java


## مقدمة لعكس إذا كانت سلبية لسلاسل فردية في شرائح Java

يوفر Aspose.Slides لجافا أدوات فعّالة للتعامل مع العروض التقديمية، ومن ميزاته المثيرة للاهتمام إمكانية التحكم في كيفية عرض سلاسل البيانات على المخططات. في هذه المقالة، سنستكشف كيفية استخدام ميزة "عكس البيانات السلبية" لكل سلسلة على حدة في شرائح جافا. تتيح لك هذه الميزة التمييز بصريًا بين نقاط البيانات السلبية في المخطط، مما يجعل عروضك التقديمية أكثر إفادة وتفاعلية.

## المتطلبات الأساسية

قبل أن نتعمق في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## إعداد مشروعك

للبدء، أنشئ مشروع جافا جديدًا في بيئة التطوير المتكاملة (IDE) المُفضّلة لديك. بعد إعداد مشروعك، اتبع هذه الخطوات لتطبيق ميزة "عكس القيم السلبية" لكل سلسلة على حدة في شرائح جافا.

## الخطوة 1: تضمين مكتبة Aspose.Slides

أولاً، عليك تضمين مكتبة Aspose.Slides في مشروعك. يمكنك القيام بذلك بإضافة ملف JAR الخاص بالمكتبة إلى مسار فئة مشروعك. تضمن هذه الخطوة إمكانية الوصول إلى جميع الفئات والأساليب اللازمة للعمل مع عروض PowerPoint التقديمية.

```java
import com.aspose.slides.*;
```

## الخطوة 2: إنشاء عرض تقديمي

الآن، لنُنشئ عرضًا تقديميًا جديدًا على PowerPoint باستخدام Aspose.Slides. يمكنك تحديد المجلد الذي تريد حفظ العرض التقديمي فيه باستخدام `dataDir` عامل.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 3: إضافة مخطط

في هذه الخطوة، سنضيف مخططًا بيانيًا إلى العرض التقديمي. سنستخدم مخططًا بيانيًا عموديًا مجمعًا كمثال. يمكنك اختيار أنواع مختلفة من المخططات البيانية حسب احتياجاتك.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## الخطوة 4: تكوين سلسلة بيانات الرسم البياني

بعد ذلك، سنقوم بتكوين سلسلة بيانات الرسم البياني. لتوضيح ميزة "عكس القيم السلبية"، سننشئ مجموعة بيانات نموذجية تحتوي على قيم موجبة وسالبة.

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

الآن، سنطبّق خاصية "عكس اللون إذا كان سلبيًا" على إحدى نقاط البيانات. سيؤدي هذا إلى عكس لون نقطة البيانات المحددة بصريًا عندما تكون سالبة.

```java
series.get_Item(0).setInvertIfNegative(false); // لا تنعكس بشكل افتراضي
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // عكس اللون لنقطة البيانات الثالثة
```

## الخطوة 6: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في الدليل المحدد.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لعكس إذا كان سلبيًا لسلسلة فردية في شرائح Java

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

في هذا البرنامج التعليمي، تعلمنا كيفية استخدام ميزة "عكس البيانات السلبية" لكل سلسلة على حدة في شرائح جافا باستخدام Aspose.Slides لجافا. تتيح لك هذه الميزة إبراز نقاط البيانات السلبية في مخططاتك، مما يجعل عروضك التقديمية أكثر جاذبية بصريًا وغنية بالمعلومات.

## الأسئلة الشائعة

### ما هو الغرض من ميزة "عكس إذا كان سلبيا" في Aspose.Slides لـ Java؟

تتيح لك ميزة "عكس البيانات السلبية" في Aspose.Slides لجافا التمييز بصريًا بين نقاط البيانات السلبية في المخططات البيانية. وتساعدك هذه الميزة على جعل عروضك التقديمية أكثر إفادة وتفاعلية من خلال إبراز نقاط بيانات محددة.

### كيف يمكنني تضمين مكتبة Aspose.Slides في مشروع Java الخاص بي؟

لتضمين مكتبة Aspose.Slides في مشروع جافا، عليك إضافة ملف JAR الخاص بالمكتبة إلى مسار فئة مشروعك. يتيح لك هذا الوصول إلى جميع الفئات والأساليب اللازمة للعمل مع عروض PowerPoint التقديمية.

### هل يمكنني استخدام أنواع مختلفة من المخططات مع ميزة "عكس إذا كانت سلبية"؟

نعم، يمكنك استخدام أنواع مختلفة من المخططات البيانية باستخدام ميزة "عكس البيانات السلبية". في هذا البرنامج التعليمي، استخدمنا مخططًا عموديًا مجمعًا كمثال، ولكن يمكنك تطبيق هذه الميزة على أنواع مختلفة من المخططات البيانية حسب احتياجاتك.

### هل من الممكن تخصيص مظهر نقاط البيانات المقلوبة؟

نعم، يمكنك تخصيص مظهر نقاط البيانات المقلوبة. يوفر Aspose.Slides لجافا خيارات للتحكم في لون ونمط نقاط البيانات عند عكسها باستخدام إعداد "عكس إذا كانت سلبية".

### أين يمكنني الوصول إلى وثائق Aspose.Slides لـ Java؟

يمكنك الوصول إلى وثائق Aspose.Slides لـ Java على [هنا](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}