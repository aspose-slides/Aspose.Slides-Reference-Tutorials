---
title: مسح بيانات نقاط بيانات سلسلة المخططات المحددة في شرائح Java
linktitle: مسح بيانات نقاط بيانات سلسلة المخططات المحددة في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية مسح نقاط بيانات محددة من سلسلة مخططات في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع الكود المصدري لإدارة فعالة لتصور البيانات.
type: docs
weight: 15
url: /ar/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

## مقدمة لمسح بيانات نقاط بيانات سلسلة المخططات المحددة في شرائح Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية مسح نقاط بيانات محددة من سلسلة مخططات في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. يمكن أن يكون ذلك مفيدًا عندما تريد إزالة نقاط بيانات معينة من مخطط لتحديث تمثيل بياناتك أو تعديله.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: قم بتحميل العرض التقديمي

 أولاً، نحتاج إلى تحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي تريد تعديله. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## الخطوة 2: الوصول إلى المخطط

بعد ذلك، سنصل إلى المخطط من الشريحة. في هذا المثال، نفترض أن المخطط موجود في الشريحة الأولى (الشريحة عند الفهرس 0). يمكنك ضبط فهرس الشريحة حسب الحاجة.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## الخطوة 3: مسح نقاط البيانات المحددة

الآن، سوف نكرر نقاط البيانات الخاصة بالسلسلة الأولى من المخطط ونمسح قيم X وY الخاصة بها.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

 يتكرر هذا الرمز عبر كل نقطة بيانات في السلسلة الأولى (الفهرس 0) ويعين قيمتي X وY على`null`، مسح نقاط البيانات بشكل فعال.

## الخطوة 4: إزالة نقاط البيانات التي تم مسحها

للتأكد من إزالة نقاط البيانات التي تم مسحها من السلسلة، سنقوم بمسح السلسلة بأكملها.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

يقوم هذا الرمز بمسح كافة نقاط البيانات من السلسلة الأولى.

## الخطوة 5: احفظ العرض التقديمي المعدل

وأخيرًا، سنقوم بحفظ العرض التقديمي المعدل في ملف جديد.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لمسح بيانات نقاط بيانات سلسلة المخططات المحددة في شرائح Java

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

 في هذا الدليل، تعلمت كيفية مسح نقاط بيانات محددة من سلسلة مخططات في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى تحديث بيانات المخطط أو تعديلها ديناميكيًا في تطبيقات Java الخاصة بك. إذا كان لديك أي أسئلة أخرى أو كنت بحاجة إلى مساعدة إضافية، يرجى الرجوع إلى[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

## الأسئلة الشائعة

### كيف يمكنني إزالة نقاط بيانات محددة من سلسلة مخططات في Aspose.Slides لـ Java؟

لإزالة نقاط بيانات معينة من سلسلة مخططات في Aspose.Slides لـ Java، اتبع الخطوات التالية:

1. قم بتحميل العرض التقديمي.
2. قم بالوصول إلى المخطط الموجود على الشريحة.
3. قم بالتكرار عبر نقاط البيانات الخاصة بالسلسلة المطلوبة وامسح قيم X وY الخاصة بها.
4. قم بمسح السلسلة بأكملها لإزالة نقاط البيانات التي تم مسحها.
5. احفظ العرض التقديمي المعدل.

### هل يمكنني مسح نقاط البيانات من سلاسل متعددة في نفس المخطط؟

نعم، يمكنك مسح نقاط البيانات من سلاسل متعددة في نفس المخطط عن طريق التكرار خلال نقاط البيانات لكل سلسلة ومسحها بشكل فردي.

### هل هناك طريقة لمسح نقاط البيانات بناءً على شرط أو معايير؟

نعم، يمكنك مسح نقاط البيانات بناءً على شرط ما عن طريق إضافة منطق شرطي داخل الحلقة التي تتكرر عبر نقاط البيانات. يمكنك التحقق من قيم نقاط البيانات وتحديد ما إذا كنت تريد مسحها أم لا بناءً على معاييرك.

### كيف يمكنني إضافة نقاط بيانات جديدة إلى سلسلة مخططات باستخدام Aspose.Slides لـ Java؟

 لإضافة نقاط بيانات جديدة إلى سلسلة مخططات، يمكنك استخدام`addDataPoint` طريقة السلسلة. ما عليك سوى إنشاء نقاط بيانات جديدة وإضافتها إلى السلسلة باستخدام هذه الطريقة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ Java؟

 يمكنك العثور على وثائق وأمثلة شاملة في[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).