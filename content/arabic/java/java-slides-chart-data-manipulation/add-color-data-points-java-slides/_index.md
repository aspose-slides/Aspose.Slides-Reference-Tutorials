---
title: إضافة اللون إلى نقاط البيانات في شرائح جافا
linktitle: إضافة اللون إلى نقاط البيانات في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة لون إلى نقاط البيانات في شرائح Java باستخدام Aspose.Slides for Java.
type: docs
weight: 10
url: /ar/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## مقدمة لإضافة اللون إلى نقاط البيانات في شرائح جافا

في هذا البرنامج التعليمي، سنوضح كيفية إضافة اللون إلى نقاط البيانات في شرائح Java باستخدام Aspose.Slides for Java. يتضمن هذا الدليل التفصيلي أمثلة على التعليمات البرمجية المصدر لمساعدتك في تحقيق هذه المهمة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- Aspose.Slides لمكتبة جافا

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، سنقوم بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides لـ Java. سيكون هذا العرض التقديمي بمثابة حاوية لمخططنا.

```java
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط Sunburst

الآن، دعونا نضيف مخطط Sunburst إلى العرض التقديمي. نحدد نوع المخطط وموضعه وحجمه.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## الخطوة 3: الوصول إلى نقاط البيانات

 لتعديل نقاط البيانات في المخطط، نحتاج إلى الوصول إلى`IChartDataPointCollection` هدف.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## الخطوة 4: تخصيص نقاط البيانات

في هذه الخطوة، سنقوم بتخصيص نقاط بيانات محددة. نقوم هنا بتغيير لون نقاط البيانات وتكوين إعدادات التسمية.

```java
// تخصيص نقطة البيانات 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// تخصيص نقطة البيانات 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام المخطط المخصص.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة اللون إلى نقاط بيانات محددة في شريحة Java باستخدام Aspose.Slides for Java.

## أكمل كود المصدر لإضافة اللون إلى نقاط البيانات في شرائح Java

```java
Presentation pres = new Presentation();
try
{
	// المسار إلى دليل المستندات.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//لكى يفعل
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إضافة لون إلى نقاط البيانات في شرائح Java باستخدام Aspose.Slides for Java. يمكنك أيضًا تخصيص المخططات والعروض التقديمية الخاصة بك بناءً على متطلباتك المحددة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون نقاط البيانات الأخرى؟

لتغيير لون نقاط البيانات الأخرى، يمكنك اتباع أسلوب مشابه كما هو موضح في الخطوة 4. قم بالوصول إلى نقطة البيانات التي تريد تخصيصها وتعديل إعدادات اللون والتسمية الخاصة بها.

### هل يمكنني تخصيص جوانب أخرى من المخطط؟

نعم، يمكنك تخصيص جوانب مختلفة من المخطط، بما في ذلك الخطوط والتسميات والعناوين والمزيد. الرجوع إلى[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على خيارات التخصيص التفصيلية.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟

 يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية حول استخدام Aspose.Slides لـ Java على الموقع[Aspose.Slides الوثائق](https://reference.aspose.com/slides/java/) موقع إلكتروني.