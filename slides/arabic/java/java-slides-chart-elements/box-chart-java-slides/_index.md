---
title: مخطط مربع في شرائح جافا
linktitle: مخطط مربع في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء مخططات مربعة في عروض Java التقديمية باستخدام Aspose.Slides. تم تضمين دليل خطوة بخطوة وكود المصدر لتصور البيانات بشكل فعال.
type: docs
weight: 10
url: /ar/java/chart-elements/box-chart-java-slides/
---

## مقدمة إلى المخطط الصندوقي في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخطط مربع باستخدام Aspose.Slides لـ Java. تعتبر المخططات المربعة مفيدة لتصور البيانات الإحصائية ذات الأرباع والقيم المتطرفة المختلفة. سنقدم لك تعليمات خطوة بخطوة بالإضافة إلى التعليمات البرمجية المصدر لمساعدتك على البدء.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Aspose.Slides لمكتبة Java.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: تهيئة العرض التقديمي

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

في هذه الخطوة، نقوم بتهيئة كائن عرض تقديمي باستخدام المسار إلى ملف PowerPoint موجود ("test.pptx" في هذا المثال).

## الخطوة 2: إنشاء مخطط الصندوق

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

في هذه الخطوة، نقوم بإنشاء شكل مخطط مربع على الشريحة الأولى من العرض التقديمي. نقوم أيضًا بمسح أي فئات وسلاسل موجودة من المخطط.

## الخطوة 3: تحديد الفئات

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 في هذه الخطوة، نقوم بتحديد فئات المخطط الصندوقي. نحن نستخدم ال`IChartDataWorkbook` لإضافة فئات وتصنيفها وفقًا لذلك.

## الخطوة 4: إنشاء السلسلة

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

هنا، نقوم بإنشاء سلسلة BoxAndWhisker للمخطط وتكوين خيارات متنوعة مثل الطريقة الربعية والخط المتوسط والعلامات المتوسطة والنقاط الداخلية والنقاط الخارجية.

## الخطوة 5: إضافة نقاط البيانات

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

في هذه الخطوة، نضيف نقاط البيانات إلى سلسلة BoxAndWhisker. تمثل نقاط البيانات هذه البيانات الإحصائية للمخطط.

## الخطوة 6: احفظ العرض التقديمي

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

وأخيرًا، نقوم بحفظ العرض التقديمي مع Box Chart في ملف PowerPoint جديد يسمى "BoxAndWhisker.pptx."

تهانينا! لقد نجحت في إنشاء مخطط مربع باستخدام Aspose.Slides لـ Java. يمكنك تخصيص المخطط بشكل أكبر عن طريق ضبط الخصائص المتنوعة وإضافة المزيد من نقاط البيانات حسب الحاجة.

## أكمل كود المصدر للمخطط الصندوقي في شرائح جافا

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخطط مربع باستخدام Aspose.Slides لـ Java. تعد المخططات المربعة أدوات قيمة لتصور البيانات الإحصائية، بما في ذلك الربعيات والقيم المتطرفة. لقد قدمنا دليلاً خطوة بخطوة بالإضافة إلى التعليمات البرمجية المصدر لمساعدتك على البدء في إنشاء مخططات مربعة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني تغيير مظهر المخطط الصندوقي؟

يمكنك تخصيص مظهر المخطط المربع عن طريق تعديل خصائص مثل أنماط الخطوط والألوان والخطوط. راجع وثائق Aspose.Slides for Java للحصول على تفاصيل حول تخصيص المخطط.

### هل يمكنني إضافة سلسلة بيانات إضافية إلى المخطط المربع؟

 نعم، يمكنك إضافة سلاسل بيانات متعددة إلى المخطط المربع عن طريق إنشاء المزيد`IChartSeries` الكائنات وإضافة نقاط البيانات إليها.

### ماذا يعني QuartileMethodType.Exclusive؟

 ال`QuartileMethodType.Exclusive` يحدد الإعداد أنه يجب إجراء الحسابات الربعية باستخدام الطريقة الحصرية. يمكنك اختيار طرق حساب ربعية مختلفة وفقًا لبياناتك ومتطلباتك.