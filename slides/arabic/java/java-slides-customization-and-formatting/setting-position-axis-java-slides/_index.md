---
"description": "حسّن مخططاتك البيانية مع Aspose.Slides لجافا. تعلّم كيفية ضبط محور الموضع في شرائح جافا، وإنشاء عروض تقديمية رائعة، وتخصيص تخطيطات المخططات البيانية بسهولة."
"linktitle": "ضبط محور الموضع في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "ضبط محور الموضع في شرائح Java"
"url": "/ar/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ضبط محور الموضع في شرائح Java


## مقدمة لضبط محور الموضع في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنتعلم كيفية تحديد موضع المحور في مخطط بياني باستخدام Aspose.Slides لجافا. يُعد تحديد موضع المحور مفيدًا عند الرغبة في تخصيص مظهر وتخطيط مخططك البياني. سننشئ مخططًا بيانيًا عموديًا مجمعًا ونضبط موضع المحور الأفقي بين الفئات.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا وإعدادها في مشروع جافا. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، دعنا ننشئ عرضًا تقديميًا جديدًا للعمل عليه:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

تأكد من الاستبدال `"Your Document Directory"` مع المسار الفعلي إلى دليل المستند الخاص بك.

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا عموديًا مجمعًا إلى الشريحة. نحدد نوع المخطط، وموقعه (إحداثيات x وy)، وأبعاده (العرض والارتفاع):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

هنا، أضفنا مخططًا عموديًا مجمعًا في الموضع (50، 50) بعرض 450 وارتفاع 300. يمكنك تعديل هذه القيم حسب الحاجة.

## الخطوة 3: ضبط محور الموضع

لتعيين محور الموضع بين الفئات، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

يقوم هذا الكود بتعيين المحور الأفقي الذي سيتم عرضه بين الفئات، والذي قد يكون مفيدًا لتخطيطات مخططات معينة.

## الخطوة 4: حفظ العرض التقديمي

وأخيرًا، دعنا نحفظ العرض التقديمي باستخدام الرسم البياني:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

يستبدل `"AsposeClusteredColumnChart.pptx"` مع اسم الملف المطلوب.

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي مجمع وتعيين محور الموضع بين الفئات باستخدام Aspose.Slides لـ Java.

## الكود المصدر الكامل
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، استكشفنا كيفية تحديد محور الموضع في مخطط بياني باستخدام Aspose.Slides لجافا. باتباع الخطوات الموضحة في هذا الدليل، تعلمت كيفية إنشاء مخطط بياني عمودي مجمع وتخصيص مظهره من خلال تحديد موضع المحور الأفقي بين الفئات. يوفر Aspose.Slides لجافا ميزات فعّالة للعمل مع المخططات البيانية والعروض التقديمية، مما يجعله أداة قيّمة لمطوري جافا.

## الأسئلة الشائعة

### كيف يمكنني تخصيص الرسم البياني بشكل أكبر؟

يمكنك تخصيص جوانب مختلفة من الرسم البياني، بما في ذلك سلسلة البيانات، وعنوان الرسم البياني، والرموز التوضيحية، والمزيد. راجع [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) للحصول على تعليمات مفصلة وأمثلة.

### هل يمكنني تغيير نوع الرسم البياني؟

نعم، يمكنك تغيير نوع الرسم البياني عن طريق تعديل `ChartType` عند إضافة الرسم البياني، يدعم Aspose.Slides لـ Java أنواعًا مختلفة من الرسوم البيانية، مثل الرسوم البيانية الشريطية والخطية وغيرها.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟

يمكنك العثور على وثائق شاملة ومزيد من الأمثلة على [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) صفحة.

تذكر التخلص من كائن العرض التقديمي عند الانتهاء منه لتحرير موارد النظام:

```java
if (pres != null) pres.dispose();
```

هذا كل ما في هذا البرنامج التعليمي. لقد تعلمت كيفية تعيين محور الموضع في مخطط باستخدام Aspose.Slides لجافا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}