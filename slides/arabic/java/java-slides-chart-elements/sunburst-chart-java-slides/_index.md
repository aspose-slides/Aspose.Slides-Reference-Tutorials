---
"description": "أنشئ مخططات Sunburst مذهلة في شرائح Java باستخدام Aspose.Slides. تعلم خطوة بخطوة إنشاء المخططات ومعالجة البيانات."
"linktitle": "مخطط Sunburst في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط Sunburst في شرائح Java"
"url": "/ar/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط Sunburst في شرائح Java


## مقدمة إلى مخطط Sunburst في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، ستتعلم كيفية إنشاء مخطط Sunburst في عرض تقديمي لبرنامج PowerPoint باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. مخطط Sunburst هو مخطط شعاعي يُستخدم لتمثيل البيانات الهرمية. سنقدم تعليمات خطوة بخطوة مع الكود المصدري.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا وتهيئتها في مشروع جافا. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: استيراد المكتبات المطلوبة

أولاً، قم باستيراد المكتبات اللازمة للعمل مع Aspose.Slides وإنشاء مخطط Sunburst في تطبيق Java الخاص بك.

```java
import com.aspose.slides.*;
```

## الخطوة 2: تهيئة العرض التقديمي

قم بتشغيل عرض تقديمي في PowerPoint وحدد الدليل الذي سيتم حفظ ملف العرض التقديمي فيه.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 3: إنشاء مخطط Sunburst

أنشئ مخططًا لـ Sunburst على شريحة. حدد موضع المخطط (X، Y) وأبعاده (العرض، الارتفاع).

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## الخطوة 4: تحضير بيانات الرسم البياني

قم بمسح أي فئات وبيانات سلاسل موجودة من الرسم البياني، ثم قم بإنشاء مصنف بيانات للرسم البياني.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## الخطوة 5: تحديد التسلسل الهرمي للمخطط

حدّد الهيكل الهرمي لمخطط Sunburst. يمكنك إضافة فروع وسيقان وأوراق كفئات.

```java
// الفرع 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// الفرع الثاني
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## الخطوة 6: إضافة البيانات إلى الرسم البياني

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

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي باستخدام مخطط Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## كود المصدر الكامل لمخطط Sunburst في شرائح Java

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
	//الفرع 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//الفرع الثاني
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

في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط Sunburst في عرض تقديمي على PowerPoint باستخدام واجهة برمجة تطبيقات Aspose.Slides لجافا. وشاهدت كيفية تهيئة العرض التقديمي، وإنشائه، وتحديد تسلسله الهرمي، وإضافة نقاط بيانات، وحفظه. يمكنك الآن استخدام هذه المعرفة لإنشاء مخططات Sunburst تفاعلية وغنية بالمعلومات في تطبيقات جافا.

## الأسئلة الشائعة

### كيف يمكنني تخصيص مظهر مخطط Sunburst؟

يمكنك تخصيص مظهر مخطط Sunburst بتعديل خصائص مثل الألوان والتسميات والأنماط. راجع وثائق Aspose.Slides للاطلاع على خيارات التخصيص المفصلة.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى الرسم البياني؟

نعم، يمكنك إضافة المزيد من نقاط البيانات إلى الرسم البياني باستخدام `series.getDataPoints().addDataPointForSunburstSeries()` طريقة لكل نقطة بيانات تريد تضمينها.

### كيف يمكنني إضافة تلميحات الأدوات إلى مخطط Sunburst؟

لإضافة تلميحات الأدوات إلى مخطط Sunburst، يمكنك تعيين تنسيق تسمية البيانات لعرض معلومات إضافية، مثل القيم أو الأوصاف، عند التمرير فوق أجزاء المخطط.

### هل من الممكن إنشاء مخططات Sunburst تفاعلية مع الارتباطات التشعبية؟

نعم، يمكنك إنشاء مخططات Sunburst تفاعلية مع روابط تشعبية بإضافة روابط تشعبية إلى عناصر أو أجزاء محددة من المخطط. راجع وثائق Aspose.Slides لمزيد من التفاصيل حول إضافة الروابط التشعبية.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}