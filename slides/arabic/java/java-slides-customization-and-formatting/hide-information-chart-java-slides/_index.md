---
"description": "تعلّم كيفية إخفاء عناصر المخططات في شرائح جافا باستخدام Aspose.Slides لجافا. خصّص العروض التقديمية لزيادة الوضوح والجمال من خلال إرشادات خطوة بخطوة وشيفرة المصدر."
"linktitle": "إخفاء المعلومات من الرسم البياني في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إخفاء المعلومات من الرسم البياني في شرائح Java"
"url": "/ar/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إخفاء المعلومات من الرسم البياني في شرائح Java


## مقدمة لإخفاء المعلومات من الرسم البياني في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إخفاء عناصر مختلفة من مخطط في شرائح جافا باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. يمكنك استخدام هذا الكود لتخصيص مخططاتك حسب الحاجة لعروضك التقديمية.

## الخطوة 1: إعداد البيئة

قبل أن نبدأ، تأكد من إضافة مكتبة Aspose.Slides لجافا إلى مشروعك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 2: إنشاء عرض تقديمي جديد

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 3: إضافة مخطط إلى الشريحة

سنضيف مخططًا خطيًا يحتوي على علامات إلى الشريحة ثم ننتقل إلى إخفاء عناصر مختلفة من المخطط.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## الخطوة 4: إخفاء عنوان الرسم البياني

يمكنك إخفاء عنوان الرسم البياني على النحو التالي:

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

## الخطوة 7: إخفاء الأسطورة

يمكنك إخفاء أسطورة الرسم البياني على النحو التالي:

```java
chart.setLegend(false);
```

## الخطوة 8: إخفاء خطوط الشبكة الرئيسية

لإخفاء خطوط الشبكة الرئيسية للمحور الأفقي، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## الخطوة 9: إزالة السلسلة

إذا كنت تريد إزالة جميع السلاسل من الرسم البياني، يمكنك استخدام حلقة مثل هذه:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## الخطوة 10: تخصيص سلسلة المخططات

يمكنك تخصيص سلسلة المخططات حسب الحاجة. في هذا المثال، نغير نمط العلامة، وموضع تسمية البيانات، وحجم العلامة، ولون الخط، ونمط الشرطة.

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

## الخطوة 11: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إخفاء عناصر مختلفة من مخطط في شرائح جافا باستخدام Aspose.Slides لجافا. يمكنك تخصيص مخططاتك وعروضك التقديمية بشكل أكبر لتلبية احتياجاتك الخاصة.

## كود المصدر الكامل لإخفاء المعلومات من الرسم البياني في شرائح Java

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
	//إخفاء خطوط الشبكة الرئيسية
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
	//ضبط لون خط السلسلة
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

في هذا الدليل التفصيلي، استكشفنا كيفية إخفاء عناصر مختلفة من مخطط في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. يُعد هذا مفيدًا للغاية عند الحاجة إلى تخصيص مخططاتك للعروض التقديمية وجعلها أكثر جاذبية بصريًا أو مصممة خصيصًا لتلبية احتياجاتك الخاصة.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر عناصر الرسم البياني بشكل أكبر؟

يمكنك تخصيص خصائص مختلفة لعناصر الرسم البياني مثل لون الخط ولون التعبئة ونمط العلامة والمزيد من خلال الوصول إلى الخصائص المقابلة لسلسلة الرسم البياني والعلامات والعلامات والتنسيق.

### هل يمكنني إخفاء نقاط بيانات محددة في الرسم البياني؟

نعم، يمكنك إخفاء نقاط بيانات محددة عن طريق تعديل بيانات سلسلة المخططات. يمكنك إزالة نقاط البيانات أو ضبط قيمها على قيمة فارغة لإخفائها.

### كيف يمكنني إضافة سلسلة إضافية إلى الرسم البياني؟

يمكنك إضافة المزيد من السلاسل إلى الرسم البياني باستخدام `IChartData.getSeries().add` الطريقة وتحديد نقاط البيانات للسلسلة الجديدة.

### هل من الممكن تغيير نوع الرسم البياني ديناميكيًا؟

نعم، يمكنك تغيير نوع الرسم البياني بشكل ديناميكي عن طريق إنشاء رسم بياني جديد من النوع المطلوب ونسخ البيانات من الرسم البياني القديم إلى الرسم البياني الجديد.

### كيف يمكنني تغيير عنوان الرسم البياني وعلامات المحور برمجيًا؟

بإمكانك تعيين عنوان وتسميات الرسم البياني والمحاور من خلال الوصول إلى خصائصها الخاصة وتعيين النص والتنسيق المطلوب.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}