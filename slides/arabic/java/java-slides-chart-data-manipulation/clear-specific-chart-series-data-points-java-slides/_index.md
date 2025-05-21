---
"description": "تعرّف على كيفية مسح نقاط بيانات محددة من سلسلة مخططات في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري لإدارة فعّالة لتصور البيانات."
"linktitle": "مسح نقاط بيانات سلسلة مخططات محددة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مسح نقاط بيانات سلسلة مخططات محددة في شرائح Java"
"url": "/ar/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مسح نقاط بيانات سلسلة مخططات محددة في شرائح Java


## مقدمة لبيانات نقاط سلسلة مخططات واضحة محددة في شرائح Java

في هذا البرنامج التعليمي، سنشرح لك عملية مسح نقاط بيانات محددة من سلسلة مخططات في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لـ Java. قد يكون هذا مفيدًا عند الرغبة في إزالة نقاط بيانات معينة من مخطط لتحديث أو تعديل تصور البيانات.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من دمج مكتبة Aspose.Slides لجافا في مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تحميل العرض التقديمي

أولاً، نحتاج إلى تحميل عرض PowerPoint الذي يحتوي على المخطط الذي تريد تعديله. استبدل `"Your Document Directory"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## الخطوة 2: الوصول إلى الرسم البياني

بعد ذلك، سنصل إلى الرسم البياني من الشريحة. في هذا المثال، نفترض أن الرسم البياني موجود في الشريحة الأولى (الشريحة عند الفهرس 0). يمكنك تعديل فهرس الشريحة حسب الحاجة.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## الخطوة 3: مسح نقاط البيانات المحددة

الآن، سوف نقوم بتكرار نقاط البيانات الخاصة بالسلسلة الأولى من الرسم البياني ومسح قيم X وY الخاصة بها.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

يقوم هذا الكود بالتنقل عبر كل نقطة بيانات في السلسلة الأولى (المؤشر 0) ويضبط قيمتي X وY على `null`، مسح نقاط البيانات بشكل فعال.

## الخطوة 4: إزالة نقاط البيانات الممسوحة

للتأكد من إزالة نقاط البيانات الممسوحة من السلسلة، سنقوم بمسح السلسلة بأكملها.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

يقوم هذا الكود بمسح جميع نقاط البيانات من السلسلة الأولى.

## الخطوة 5: حفظ العرض التقديمي المعدّل

وأخيرًا، سنقوم بحفظ العرض التقديمي المعدّل في ملف جديد.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لبيانات نقاط بيانات سلسلة مخططات واضحة ومحددة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا الدليل، تعلمت كيفية مسح نقاط بيانات محددة من سلسلة مخططات في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. قد يكون هذا مفيدًا عند الحاجة إلى تحديث بيانات المخططات أو تعديلها ديناميكيًا في تطبيقات جافا. إذا كانت لديك أي أسئلة أخرى أو كنت بحاجة إلى مساعدة إضافية، يُرجى الرجوع إلى [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

## الأسئلة الشائعة

### كيف يمكنني إزالة نقاط بيانات محددة من سلسلة مخطط في Aspose.Slides لـ Java؟

لإزالة نقاط بيانات محددة من سلسلة مخططات في Aspose.Slides لـ Java، اتبع الخطوات التالية:

1. تحميل العرض التقديمي.
2. الوصول إلى الرسم البياني على الشريحة.
3. قم بالتكرار خلال نقاط البيانات الخاصة بالسلسلة المطلوبة وقم بمسح قيم X وY الخاصة بها.
4. قم بمسح السلسلة بأكملها لإزالة نقاط البيانات التي تم مسحها.
5. احفظ العرض التقديمي المعدّل.

### هل يمكنني مسح نقاط البيانات من سلاسل متعددة في نفس الرسم البياني؟

نعم، يمكنك مسح نقاط البيانات من سلاسل متعددة في نفس الرسم البياني عن طريق تكرار نقاط البيانات لكل سلسلة ومسحها بشكل فردي.

### هل هناك طريقة لمسح نقاط البيانات بناءً على شرط أو معيار؟

نعم، يمكنك مسح نقاط البيانات بناءً على شرط بإضافة منطق شرطي داخل الحلقة التي تتكرر عبر نقاط البيانات. يمكنك التحقق من قيم نقاط البيانات وتحديد ما إذا كنت تريد مسحها أم لا بناءً على معاييرك.

### كيف يمكنني إضافة نقاط بيانات جديدة إلى سلسلة مخطط باستخدام Aspose.Slides لـ Java؟

لإضافة نقاط بيانات جديدة إلى سلسلة مخطط، يمكنك استخدام `addDataPoint` طريقة السلسلة. ببساطة، أنشئ نقاط بيانات جديدة وأضفها إلى السلسلة باستخدام هذه الطريقة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

يمكنك العثور على وثائق وأمثلة شاملة في [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}