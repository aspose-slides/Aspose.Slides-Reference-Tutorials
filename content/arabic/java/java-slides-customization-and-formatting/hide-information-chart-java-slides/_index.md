---
title: إخفاء المعلومات من الرسم البياني في شرائح جافا
linktitle: إخفاء المعلومات من الرسم البياني في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إخفاء عناصر المخطط في Java Slides باستخدام Aspose.Slides لـ Java. قم بتخصيص العروض التقديمية لتحقيق الوضوح والجمال من خلال إرشادات خطوة بخطوة وكود المصدر.
type: docs
weight: 13
url: /ar/java/customization-and-formatting/hide-information-chart-java-slides/
---

## مقدمة لإخفاء المعلومات من الرسم البياني في شرائح جافا

في هذا البرنامج التعليمي، سوف نستكشف كيفية إخفاء العناصر المختلفة من المخطط في Java Slides باستخدام Aspose.Slides for Java API. يمكنك استخدام هذا الرمز لتخصيص مخططاتك حسب الحاجة لعروضك التقديمية.

## الخطوة 1: إعداد البيئة

 قبل أن نبدأ، تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 2: إنشاء عرض تقديمي جديد

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 3: إضافة مخطط إلى الشريحة

سنضيف مخططًا خطيًا يحتوي على علامات إلى الشريحة ثم ننتقل إلى إخفاء العناصر المختلفة للمخطط.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## الخطوة 4: إخفاء عنوان المخطط

يمكنك إخفاء عنوان المخطط كما يلي:

```java
chart.setTitle(false);
```

## الخطوة 5: إخفاء محور القيم

لإخفاء محور القيم (المحور الرأسي)، استخدم الكود التالي:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## الخطوة 6: إخفاء محور الفئة

لإخفاء محور الفئة (المحور الأفقي)، استخدم هذا الكود:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## الخطوة 7: إخفاء وسيلة الإيضاح

يمكنك إخفاء وسيلة إيضاح المخطط مثل هذا:

```java
chart.setLegend(false);
```

## الخطوة 8: إخفاء خطوط الشبكة الرئيسية

لإخفاء خطوط الشبكة الرئيسية للمحور الأفقي، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## الخطوة 9: إزالة السلسلة

إذا كنت تريد إزالة كافة السلاسل من المخطط، يمكنك استخدام حلقة مثل هذه:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## الخطوة 10: تخصيص سلسلة المخططات

يمكنك تخصيص سلسلة المخططات حسب الحاجة. في هذا المثال، نقوم بتغيير نمط العلامة وموضع تسمية البيانات وحجم العلامة ولون الخط ونمط الشرطة:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## الخطوة 11: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إخفاء عناصر مختلفة من مخطط في Java Slides باستخدام Aspose.Slides for Java. يمكنك أيضًا تخصيص المخططات والعروض التقديمية الخاصة بك حسب الحاجة لمتطلباتك المحددة.

## أكمل كود المصدر لإخفاء المعلومات من المخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//إخفاء عنوان الرسم البياني
	chart.setTitle(false);
	///إخفاء محور القيم
	chart.getAxes().getVerticalAxis().setVisible(false);
	//رؤية محور الفئة
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//إخفاء الأسطورة
	chart.setLegend(false);
	//إخفاء خطوط MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//تحديد لون خط السلسلة
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## خاتمة

في هذا الدليل المفصّل خطوة بخطوة، اكتشفنا كيفية إخفاء عناصر مختلفة من مخطط في Java Slides باستخدام Aspose.Slides for Java API. يمكن أن يكون هذا مفيدًا بشكل لا يصدق عندما تحتاج إلى تخصيص مخططاتك للعروض التقديمية وجعلها أكثر جاذبية من الناحية المرئية أو مصممة خصيصًا لتلبية احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر عناصر المخطط بشكل أكبر؟

يمكنك تخصيص خصائص متنوعة لعناصر المخطط مثل لون الخط ولون التعبئة ونمط العلامة والمزيد عن طريق الوصول إلى الخصائص المقابلة لسلسلة المخطط والعلامات والتسميات والتنسيق.

### هل يمكنني إخفاء نقاط بيانات محددة في المخطط؟

نعم، يمكنك إخفاء نقاط بيانات محددة عن طريق معالجة البيانات الموجودة في سلسلة المخططات. يمكنك إزالة نقاط البيانات أو تعيين قيمها على قيمة خالية لإخفائها.

### كيف يمكنني إضافة سلسلة إضافية إلى المخطط؟

 يمكنك إضافة المزيد من السلاسل إلى المخطط باستخدام`IChartData.getSeries().add` طريقة وتحديد نقاط البيانات للسلسلة الجديدة.

### هل من الممكن تغيير نوع المخطط ديناميكيًا؟

نعم، يمكنك تغيير نوع المخطط ديناميكيًا عن طريق إنشاء مخطط جديد من النوع المطلوب ونسخ البيانات من المخطط القديم إلى المخطط الجديد.

### كيف يمكنني تغيير عنوان المخطط وتسميات المحاور برمجياً؟

يمكنك تعيين عنوان وتسميات المخطط والمحاور عن طريق الوصول إلى خصائصها وتعيين النص والتنسيق المطلوبين.