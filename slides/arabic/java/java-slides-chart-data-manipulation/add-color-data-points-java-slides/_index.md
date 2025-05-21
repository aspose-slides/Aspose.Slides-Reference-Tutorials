---
"description": "تعرف على كيفية إضافة اللون إلى نقاط البيانات في شرائح Java باستخدام Aspose.Slides for Java."
"linktitle": "إضافة اللون إلى نقاط البيانات في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة اللون إلى نقاط البيانات في شرائح Java"
"url": "/ar/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة اللون إلى نقاط البيانات في شرائح Java


## مقدمة لإضافة اللون إلى نقاط البيانات في شرائح Java

في هذا البرنامج التعليمي، سنوضح كيفية إضافة ألوان إلى نقاط البيانات في شرائح جافا باستخدام Aspose.Slides for Java. يتضمن هذا الدليل خطوة بخطوة أمثلة على الكود المصدري لمساعدتك في إنجاز هذه المهمة.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- بيئة تطوير جافا
- مكتبة Aspose.Slides لـ Java

## الخطوة 1: إنشاء عرض تقديمي جديد

أولاً، سننشئ عرضًا تقديميًا جديدًا باستخدام Aspose.Slides لجافا. سيُستخدم هذا العرض التقديمي كحاوية لمخططنا.

```java
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط Sunburst

الآن، لنُضِف مخطط Sunburst إلى العرض التقديمي. نُحدِّد نوع المخطط وموقعه وحجمه.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## الخطوة 3: الوصول إلى نقاط البيانات

لتعديل نقاط البيانات في الرسم البياني، نحتاج إلى الوصول إلى `IChartDataPointCollection` هدف.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## الخطوة 4: تخصيص نقاط البيانات

في هذه الخطوة، سنُخصّص نقاط بيانات مُحدّدة. هنا، سنُغيّر لون نقاط البيانات ونُهيئ إعدادات التسميات.

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

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام الرسم البياني المخصص.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة لون إلى نقاط بيانات محددة في شريحة جافا باستخدام Aspose.Slides لجافا.

## الكود المصدر الكامل لإضافة اللون إلى نقاط البيانات في شرائح Java

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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//المهام
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إضافة ألوان إلى نقاط البيانات في شرائح جافا باستخدام Aspose.Slides for Java. يمكنك تخصيص مخططاتك وعروضك التقديمية بشكل أكبر بناءً على احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون نقاط البيانات الأخرى؟

لتغيير لون نقاط البيانات الأخرى، يمكنك اتباع نهج مماثل كما هو موضح في الخطوة 4. قم بالوصول إلى نقطة البيانات التي تريد تخصيصها وتعديل إعدادات اللون والتسمية الخاصة بها.

### هل يمكنني تخصيص جوانب أخرى من الرسم البياني؟

نعم، يمكنك تخصيص جوانب مختلفة من المخطط، بما في ذلك الخطوط، والتسميات، والعناوين، والمزيد. راجع [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/) للحصول على خيارات التخصيص التفصيلية.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟

يمكنك العثور على المزيد من الأمثلة والوثائق التفصيلية حول استخدام Aspose.Slides لـ Java على [توثيق Aspose.Slides](https://reference.aspose.com/slides/java/) موقع إلكتروني.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}