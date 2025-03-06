---
title: إضافة خطأ مخصص في شرائح جافا
linktitle: إضافة خطأ مخصص في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة أشرطة خطأ مخصصة إلى مخططات PowerPoint في Java Slides باستخدام Aspose.Slides. دليل خطوة بخطوة مع الكود المصدري لتصور البيانات بدقة.
weight: 11
url: /ar/java/chart-data-manipulation/add-custom-error-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لإضافة أشرطة خطأ مخصصة في شرائح Java باستخدام Aspose.Slides

ستتعلم في هذا البرنامج التعليمي كيفية إضافة أشرطة خطأ مخصصة إلى مخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. تعتبر أشرطة الخطأ مفيدة لعرض التباين أو عدم اليقين في نقاط البيانات على المخطط.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت Aspose.Slides لمكتبة Java وتكوينها في مشروعك.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: إنشاء عرض تقديمي فارغ

أولاً، قم بإنشاء عرض PowerPoint تقديمي فارغ.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
```

## الخطوة 2: إضافة مخطط فقاعي

بعد ذلك، سنقوم بإضافة مخطط فقاعي إلى العرض التقديمي.

```java
// إنشاء مخطط فقاعي
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## الخطوة 3: إضافة أشرطة خطأ مخصصة

الآن، دعونا نضيف أشرطة الخطأ المخصصة إلى سلسلة المخططات.

```java
// إضافة أشرطة خطأ مخصصة وتحديد تنسيقها
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## الخطوة 4: تعيين بيانات أشرطة الخطأ

في هذه الخطوة، سنصل إلى نقاط بيانات سلسلة المخططات ونقوم بتعيين قيم أشرطة الخطأ المخصصة لكل نقطة.

```java
// الوصول إلى نقاط بيانات سلسلة المخططات وتعيين قيم أشرطة الخطأ للنقاط الفردية
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// تحديد أشرطة الخطأ لنقاط سلسلة الرسم البياني
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## الخطوة 5: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام أشرطة الأخطاء المخصصة.

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة أشرطة خطأ مخصصة إلى مخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java.

## أكمل كود المصدر لإضافة خطأ مخصص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
try
{
	// إنشاء مخطط فقاعي
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// إضافة أشرطة خطأ مخصصة وتحديد تنسيقها
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// الوصول إلى نقطة بيانات سلسلة المخططات وتعيين قيم أشرطة الخطأ للنقطة الفردية
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// تحديد أشرطة الخطأ لنقاط سلسلة الرسم البياني
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

في هذا البرنامج التعليمي الشامل، تعلمت كيفية تحسين عروض PowerPoint التقديمية الخاصة بك عن طريق إضافة أشرطة خطأ مخصصة إلى المخططات باستخدام Aspose.Slides for Java. توفر أشرطة الخطأ رؤى قيمة حول تقلب البيانات وعدم اليقين، مما يجعل مخططاتك أكثر إفادة وجاذبية من الناحية المرئية.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر أشرطة الخطأ؟

 يمكنك تخصيص مظهر أشرطة الخطأ عن طريق تعديل خصائص الملف`IErrorBarsFormat` كائن، مثل نمط الخط ولون الخط وعرض شريط الخطأ.

### هل يمكنني إضافة أشرطة خطأ إلى أنواع المخططات الأخرى؟

نعم، يمكنك إضافة أشرطة خطأ إلى أنواع المخططات المتنوعة التي يدعمها Aspose.Slides لـ Java، بما في ذلك المخططات الشريطية، والمخططات الخطية، والمخططات المبعثرة.

### كيف أقوم بتعيين قيم مختلفة لشريط الخطأ لكل نقطة بيانات؟

يمكنك التكرار خلال نقاط البيانات وتعيين قيم شريط الأخطاء المخصصة لكل نقطة، كما هو موضح في الكود أعلاه.

### هل من الممكن إخفاء أشرطة الخطأ لنقاط بيانات محددة؟

 نعم، يمكنك التحكم في رؤية أشرطة الخطأ لنقاط البيانات الفردية عن طريق تعيين`setVisible` ملكية`IErrorBarsFormat` هدف.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
