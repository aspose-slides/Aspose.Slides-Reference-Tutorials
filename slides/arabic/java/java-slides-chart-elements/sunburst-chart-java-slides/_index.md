---
title: مخطط Sunburst في شرائح Java
linktitle: مخطط Sunburst في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: أنشئ مخططات Sunburst مذهلة في شرائح Java باستخدام Aspose.Slides. تعلم كيفية إنشاء المخططات خطوة بخطوة ومعالجة البيانات.
weight: 16
url: /ar/java/chart-elements/sunburst-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى مخطط Sunburst في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، ستتعلم كيفية إنشاء مخطط Sunburst في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java API. مخطط Sunburst هو مخطط شعاعي يستخدم لتمثيل البيانات الهرمية. سنقدم تعليمات خطوة بخطوة مع كود المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وتكوينها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد المكتبات المطلوبة

أولاً، قم باستيراد المكتبات اللازمة للعمل مع Aspose.Slides وإنشاء مخطط Sunburst في تطبيق Java الخاص بك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تهيئة العرض التقديمي

قم بتهيئة عرض PowerPoint التقديمي وحدد الدليل الذي سيتم حفظ ملف العرض التقديمي فيه.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 3: إنشاء مخطط Sunburst

إنشاء مخطط Sunburst على شريحة. نحدد الموضع (X، Y) والأبعاد (العرض والارتفاع) للمخطط.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## الخطوة 4: إعداد بيانات الرسم البياني

قم بمسح أي فئات وبيانات متسلسلة موجودة من المخطط، وقم بإنشاء مصنف بيانات للمخطط.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## الخطوة 5: تحديد التسلسل الهرمي للمخطط

حدد الهيكل الهرمي لمخطط Sunburst. يمكنك إضافة الفروع والسيقان والأوراق كفئات.

```java
// فرع 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// فرع 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## الخطوة 6: إضافة البيانات إلى المخطط

أضف نقاط البيانات إلى سلسلة مخططات Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## الخطوة 7: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام مخطط Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لمخطط Sunburst في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//فرع 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//فرع 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط Sunburst في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java API. لقد رأيت كيفية تهيئة العرض التقديمي وإنشاء المخطط وتحديد التسلسل الهرمي للمخطط وإضافة نقاط البيانات وحفظ العرض التقديمي. يمكنك الآن استخدام هذه المعرفة لإنشاء مخططات Sunburst تفاعلية وغنية بالمعلومات في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر مخطط Sunburst؟

يمكنك تخصيص مظهر مخطط Sunburst عن طريق تعديل خصائص مثل الألوان والتسميات والأنماط. راجع وثائق Aspose.Slides للحصول على خيارات التخصيص التفصيلية.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى المخطط؟

 نعم، يمكنك إضافة المزيد من نقاط البيانات إلى المخطط باستخدام`series.getDataPoints().addDataPointForSunburstSeries()` طريقة لكل نقطة بيانات تريد تضمينها.

### كيف يمكنني إضافة تلميحات الأدوات إلى مخطط Sunburst؟

لإضافة تلميحات أدوات إلى مخطط Sunburst، يمكنك تعيين تنسيق تسمية البيانات لعرض معلومات إضافية، مثل القيم أو الأوصاف، عند المرور فوق مقاطع المخطط.

### هل من الممكن إنشاء مخططات Sunburst تفاعلية باستخدام الارتباطات التشعبية؟

نعم، يمكنك إنشاء مخططات Sunburst تفاعلية باستخدام ارتباطات تشعبية عن طريق إضافة ارتباطات تشعبية إلى عناصر أو مقاطع مخطط محددة. راجع وثائق Aspose.Slides للحصول على تفاصيل حول إضافة الارتباطات التشعبية.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
