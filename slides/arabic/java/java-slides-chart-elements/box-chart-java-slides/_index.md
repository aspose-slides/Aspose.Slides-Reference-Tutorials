---
"description": "تعلّم كيفية إنشاء مخططات مربعات في عروض جافا التقديمية باستخدام Aspose.Slides. يتضمن دليلًا خطوة بخطوة وشيفرة مصدرية لعرض البيانات بفعالية."
"linktitle": "مخطط مربع في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط مربع في شرائح Java"
"url": "/ar/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط مربع في شرائح Java


## مقدمة إلى مخطط الصندوق في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنشرح لك عملية إنشاء مخطط بياني مربع باستخدام Aspose.Slides لجافا. تُعدّ المخططات البيانية المربعة مفيدة لعرض البيانات الإحصائية باستخدام أرباع وقيم متطرفة مختلفة. سنقدم لك تعليمات خطوة بخطوة مع شفرة المصدر لمساعدتك في البدء.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- تم تثبيت وتكوين Aspose.Slides لمكتبة Java.
- تم إعداد بيئة تطوير Java.

## الخطوة 1: تهيئة العرض التقديمي

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

في هذه الخطوة، نقوم بتهيئة كائن العرض التقديمي باستخدام المسار إلى ملف PowerPoint الموجود ("test.pptx" في هذا المثال).

## الخطوة 2: إنشاء مخطط الصندوق

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

في هذه الخطوة، نُنشئ شكل مخطط مربع على الشريحة الأولى من العرض التقديمي. كما نُزيل أي فئات أو سلاسل موجودة من المخطط.

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

في هذه الخطوة، نُعرّف فئات مخطط الصندوق. نستخدم `IChartDataWorkbook` لإضافة الفئات وتسميتها وفقًا لذلك.

## الخطوة 4: إنشاء السلسلة

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

هنا، نقوم بإنشاء سلسلة BoxAndWhisker للرسم البياني ونقوم بتكوين خيارات مختلفة مثل طريقة الربع، وخط المتوسط، وعلامات المتوسط، والنقط الداخلية، ونقاط القيم المتطرفة.

## الخطوة 5: إضافة نقاط البيانات

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

في هذه الخطوة، نضيف نقاط بيانات إلى سلسلة BoxAndWhisker. تُمثل هذه النقاط البيانات الإحصائية للرسم البياني.

## الخطوة 6: حفظ العرض التقديمي

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

وأخيرًا، نقوم بحفظ العرض التقديمي باستخدام مخطط الصندوق في ملف PowerPoint جديد يسمى "BoxAndWhisker.pptx".

تهانينا! لقد نجحت في إنشاء مخطط صندوقي باستخدام Aspose.Slides لجافا. يمكنك تخصيص المخطط بشكل أكبر بتعديل خصائصه المختلفة وإضافة نقاط بيانات إضافية حسب الحاجة.

## كود المصدر الكامل للمخطط الصندوقي في شرائح Java

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

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخطط صندوقي باستخدام Aspose.Slides في جافا. تُعد المخططات الصندوقية أدوات قيّمة لعرض البيانات الإحصائية، بما في ذلك الأرباع والقيم المتطرفة. قدّمنا دليلاً خطوة بخطوة مع الكود المصدري لمساعدتك على البدء في إنشاء المخططات الصندوقية في تطبيقات جافا.

## الأسئلة الشائعة

### كيف يمكنني تغيير مظهر مخطط الصندوق؟

يمكنك تخصيص مظهر مخطط الصندوق بتعديل خصائص مثل أنماط الخطوط والألوان والخطوط. راجع وثائق Aspose.Slides لجافا لمزيد من التفاصيل حول تخصيص المخطط.

### هل يمكنني إضافة سلسلة بيانات إضافية إلى مخطط الصندوق؟

نعم، يمكنك إضافة سلاسل بيانات متعددة إلى مخطط المربع عن طريق إنشاء سلاسل بيانات إضافية `IChartSeries` الكائنات وإضافة نقاط البيانات إليها.

### ماذا يعني QuartileMethodType.Exclusive؟

ال `QuartileMethodType.Exclusive` يُحدد الإعداد إجراء حسابات الربع باستخدام الطريقة الحصرية. يمكنك اختيار طرق مختلفة لحساب الربع حسب بياناتك ومتطلباتك.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}