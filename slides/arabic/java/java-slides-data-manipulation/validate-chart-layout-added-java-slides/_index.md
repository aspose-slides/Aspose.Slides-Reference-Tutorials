---
title: التحقق من صحة تخطيط المخطط المُضاف في شرائح Java
linktitle: التحقق من صحة تخطيط المخطط المُضاف في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: التحقق من صحة تخطيط المخطط الرئيسي في PowerPoint باستخدام Aspose.Slides لـ Java. تعلم كيفية التعامل مع المخططات برمجيًا للحصول على عروض تقديمية مذهلة.
weight: 10
url: /ar/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة للتحقق من صحة تخطيط المخطط في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية التحقق من صحة تخطيط المخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تتيح لك هذه المكتبة العمل مع عروض PowerPoint التقديمية برمجياً، مما يجعل من السهل التعامل مع العناصر المختلفة والتحقق من صحتها، بما في ذلك المخططات.

## الخطوة 1: تهيئة العرض التقديمي

 أولاً، نحتاج إلى تهيئة كائن عرض تقديمي وتحميل عرض تقديمي موجود في PowerPoint. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف العرض التقديمي الخاص بك (`test.pptx` في هذا المثال).

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 2: إضافة مخطط

 بعد ذلك، سنقوم بإضافة مخطط إلى العرض التقديمي. في هذا المثال، نقوم بإضافة مخطط عمودي متفاوت المسافات، ولكن يمكنك تغيير`ChartType` كما هو مطلوب.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## الخطوة 3: التحقق من صحة تخطيط المخطط

 الآن، سوف نقوم بالتحقق من صحة تخطيط المخطط باستخدام`validateChartLayout()` طريقة. وهذا يضمن أن المخطط تم وضعه بشكل صحيح داخل الشريحة.

```java
chart.validateChartLayout();
```

## الخطوة 4: استرداد موضع المخطط وحجمه

بعد التحقق من صحة تخطيط المخطط، قد ترغب في استرداد معلومات حول موضعه وحجمه. يمكننا الحصول على إحداثيات X وY الفعلية، بالإضافة إلى عرض وارتفاع منطقة رسم المخطط.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## الخطوة 5: حفظ العرض التقديمي

 وأخيرًا، لا تنس حفظ العرض التقديمي المعدل. في هذا المثال، نقوم بحفظه باسم`Result.pptx`، ولكن يمكنك تحديد اسم ملف مختلف إذا لزم الأمر.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر للتحقق من صحة تخطيط المخطط المُضاف في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// حفظ العرض التقديمي
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعمقنا في عالم العمل مع المخططات في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. لقد قمنا بتغطية الخطوات الأساسية للتحقق من صحة تخطيط المخطط واسترداد موضعه وحجمه وحفظ العرض التقديمي المعدل. وهنا خلاصة سريعة:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع المخطط؟

 لتغيير نوع المخطط، ما عليك سوى استبداله`ChartType.ClusteredColumn`مع نوع المخطط المطلوب في`addChart()` طريقة.

### هل يمكنني تخصيص بيانات الرسم البياني؟

نعم، يمكنك تخصيص بيانات المخطط عن طريق إضافة وتعديل سلاسل البيانات والفئات والقيم. راجع وثائق Aspose.Slides لمزيد من التفاصيل.

### ماذا لو كنت أرغب في تعديل خصائص المخطط الأخرى؟

يمكنك الوصول إلى خصائص المخطط المختلفة وتخصيصها وفقًا لمتطلباتك. استكشف وثائق Aspose.Slides للحصول على معلومات شاملة حول معالجة المخططات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
