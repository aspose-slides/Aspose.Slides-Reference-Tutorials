---
title: خصائص الخط للمخطط في شرائح جافا
linktitle: خصائص الخط للمخطط في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تحسين خصائص خط المخطط في شرائح Java باستخدام Aspose.Slides لـ Java. قم بتخصيص حجم الخط والنمط واللون لتقديم عروض تقديمية مؤثرة.
type: docs
weight: 11
url: /ar/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

## مقدمة إلى خصائص الخط للمخطط في شرائح Java

سيرشدك هذا الدليل خلال إعداد خصائص الخط للمخطط في Java Slides باستخدام Aspose.Slides. يمكنك تخصيص حجم الخط ومظهر نص المخطط لتحسين المظهر المرئي لعروضك التقديمية.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج Aspose.Slides for Java API في مشروعك. إذا لم تكن قد قمت بذلك بالفعل، يمكنك تنزيله من[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، قم بإنشاء عرض تقديمي جديد باستخدام الكود التالي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

الآن، دعنا نضيف مخططًا عموديًا متفاوت المسافات إلى العرض التقديمي الخاص بك:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

نقوم هنا بإضافة مخطط عمودي متفاوت المسافات إلى الشريحة الأولى عند الإحداثيات (100، 100) بعرض 500 وحدة وارتفاع 400 وحدة.

## الخطوة 3: تخصيص خصائص الخط

بعد ذلك، سنقوم بتخصيص خصائص الخط للمخطط. في هذا المثال، نقوم بتعيين حجم الخط إلى 20 لجميع نص المخطط:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

يقوم هذا الرمز بتعيين حجم الخط إلى 20 نقطة لكل النص داخل المخطط.

## الخطوة 4: إظهار تسميات البيانات

يمكنك أيضًا إظهار تسميات البيانات على المخطط باستخدام الكود التالي:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

يتيح سطر التعليمات البرمجية هذا تسميات البيانات للسلسلة الأولى في المخطط، ويعرض القيم في أعمدة المخطط.

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام خصائص خط المخطط المخصص:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

سيقوم هذا الرمز بحفظ العرض التقديمي في الدليل المحدد باسم الملف "FontPropertiesForChart.pptx".

## أكمل كود المصدر لخصائص الخط للمخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تخصيص خصائص الخط لمخطط في Java Slides باستخدام Aspose.Slides لـ Java. يمكنك تطبيق هذه التقنيات لتحسين مظهر المخططات والعروض التقديمية الخاصة بك. اكتشف المزيد من الخيارات في[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

 لتغيير لون الخط لنص المخطط، استخدم`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` ، استبدال`Color.RED` مع اللون المطلوب.

### هل يمكنني تغيير نمط الخط (غامق، مائل، الخ)؟

 نعم، يمكنك تغيير نمط الخط. يستخدم`chart.getTextFormat().getPortionFormat().setFontBold(true);` لجعل الخط عريضًا. وبالمثل، يمكنك استخدام`setFontItalic(true)` لجعلها مائلة.

### كيف أقوم بتخصيص خصائص الخط لعناصر مخطط محددة؟

لتخصيص خصائص الخط لعناصر مخطط محددة، مثل تسميات المحاور أو نص وسيلة الإيضاح، يمكنك الوصول إلى هذه العناصر وتعيين خصائص الخط الخاصة بها باستخدام طرق مشابهة كما هو موضح أعلاه.