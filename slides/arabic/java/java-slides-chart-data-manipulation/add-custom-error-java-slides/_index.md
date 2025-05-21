---
"description": "تعرّف على كيفية إضافة أشرطة أخطاء مخصصة إلى مخططات PowerPoint في شرائح Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع الكود المصدري لتصور دقيق للبيانات."
"linktitle": "إضافة خطأ مخصص في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة خطأ مخصص في شرائح Java"
"url": "/ar/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خطأ مخصص في شرائح Java


## مقدمة حول إضافة أشرطة أخطاء مخصصة في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، ستتعلم كيفية إضافة أشرطة أخطاء مخصصة إلى مخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. تُفيد أشرطة الأخطاء في عرض التباين أو عدم اليقين في نقاط البيانات على مخطط.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين مكتبة Aspose.Slides لـ Java في مشروعك.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: إنشاء عرض تقديمي فارغ

أولاً، قم بإنشاء عرض تقديمي فارغ في PowerPoint.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط فقاعي

بعد ذلك، سنضيف مخططًا فقاعيًا إلى العرض التقديمي.

```java
// إنشاء مخطط فقاعي
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## الخطوة 3: إضافة أشرطة خطأ مخصصة

الآن، دعنا نضيف أشرطة الخطأ المخصصة إلى سلسلة الرسم البياني.

```java
// إضافة أشرطة الخطأ المخصصة وتعيين تنسيقها
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## الخطوة 4: تعيين بيانات أشرطة الخطأ

في هذه الخطوة، سنتمكن من الوصول إلى نقاط بيانات سلسلة الرسم البياني وتعيين قيم أشرطة الخطأ المخصصة لكل نقطة.

```java
// الوصول إلى نقاط بيانات سلسلة المخططات وتعيين قيم أشرطة الخطأ للنقاط الفردية
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// ضبط أشرطة الخطأ لنقاط سلسلة الرسم البياني
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## الخطوة 5: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام أشرطة الأخطاء المخصصة.

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة أشرطة أخطاء مخصصة إلى مخطط في عرض تقديمي باوربوينت باستخدام Aspose.Slides لجافا.

## كود المصدر الكامل لإضافة خطأ مخصص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط فقاعي
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// إضافة أشرطة الخطأ المخصصة وتعيين تنسيقها
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// الوصول إلى نقطة بيانات سلسلة المخططات وتعيين قيم أشرطة الخطأ لكل نقطة على حدة
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// ضبط أشرطة الخطأ لنقاط سلسلة الرسم البياني
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// حفظ العرض التقديمي
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي الشامل، تعلمت كيفية تحسين عروض PowerPoint التقديمية بإضافة أشرطة أخطاء مخصصة إلى المخططات البيانية باستخدام Aspose.Slides لجافا. توفر أشرطة الأخطاء رؤى قيّمة حول تباين البيانات وعدم اليقين فيها، مما يجعل مخططاتك البيانية أكثر إفادة وجاذبية بصريًا.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر أشرطة الخطأ؟

يمكنك تخصيص مظهر أشرطة الخطأ عن طريق تعديل خصائص `IErrorBarsFormat` الكائن، مثل نمط الخط، ولون الخط، وعرض شريط الخطأ.

### هل يمكنني إضافة أشرطة الخطأ إلى أنواع أخرى من المخططات؟

نعم، يمكنك إضافة أشرطة الخطأ إلى أنواع المخططات المختلفة التي يدعمها Aspose.Slides لـ Java، بما في ذلك المخططات الشريطية، والمخططات الخطية، والمخططات المتناثرة.

### كيف أقوم بتعيين قيم شريط الخطأ المختلفة لكل نقطة بيانات؟

يمكنك التنقل عبر نقاط البيانات وتعيين قيم شريط الخطأ المخصصة لكل نقطة، كما هو موضح في الكود أعلاه.

### هل من الممكن إخفاء أشرطة الخطأ لنقاط بيانات محددة؟

نعم، يمكنك التحكم في رؤية أشرطة الخطأ لنقاط البيانات الفردية عن طريق ضبط `setVisible` ممتلكات `IErrorBarsFormat` هدف.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}