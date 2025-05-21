---
"description": "تعرّف على كيفية إعداد مصنفات خارجية في شرائح جافا باستخدام Aspose.Slides لجافا. أنشئ عروضًا تقديمية ديناميكية مع تكامل بيانات Excel."
"linktitle": "تعيين مصنف خارجي في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين مصنف خارجي في شرائح Java"
"url": "/ar/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين مصنف خارجي في شرائح Java


## مقدمة لتعيين المصنف الخارجي في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية إعداد مصنف خارجي في Java Slides باستخدام Aspose.Slides. ستتعلم كيفية إنشاء عرض تقديمي في PowerPoint باستخدام مخطط يشير إلى بيانات من مصنف Excel خارجي. بنهاية هذا الدليل، ستفهم بوضوح كيفية دمج البيانات الخارجية في عروض Java Slides التقديمية.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تمت إضافة مكتبة Aspose.Slides for Java إلى مشروعك.
- مصنف Excel يحتوي على البيانات التي تريد الإشارة إليها في العرض التقديمي الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي جديد

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

نبدأ بإنشاء عرض تقديمي جديد في PowerPoint باستخدام Aspose.Slides.

## الخطوة 2: إضافة مخطط

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

بعد ذلك، نُدرج مخططًا دائريًا في العرض التقديمي. يُمكنك تخصيص نوع المخطط وموقعه حسب الحاجة.

## الخطوة 3: الوصول إلى المصنف الخارجي

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

للوصول إلى المصنف الخارجي، نستخدم `setExternalWorkbook` الطريقة وتوفير المسار إلى مصنف Excel الذي يحتوي على البيانات.

## الخطوة 4: ربط بيانات الرسم البياني

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

نقوم بربط الرسم البياني بالبيانات من المصنف الخارجي من خلال تحديد مراجع الخلايا للسلسلة والفئات.

## الخطوة 5: حفظ العرض التقديمي

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

وأخيرًا، نحفظ العرض التقديمي مع مرجع المصنف الخارجي كملف PowerPoint.

## كود المصدر الكامل لمجموعة المصنفات الخارجية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إعداد مصنف خارجي في شرائح جافا باستخدام Aspose.Slides. يمكنك الآن إنشاء عروض تقديمية تشير ديناميكيًا إلى بيانات من مصنفات Excel، مما يعزز مرونة وتفاعلية شرائحك.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

يمكن تثبيت Aspose.Slides لجافا بإضافة المكتبة إلى مشروع جافا. يمكنك تنزيل المكتبة من موقع Aspose الإلكتروني واتباع تعليمات التثبيت الموضحة في الوثائق.

### هل يمكنني استخدام أنواع مختلفة من المخططات مع المصنفات الخارجية؟

نعم، يمكنك استخدام أنواع مختلفة من المخططات التي يدعمها Aspose.Slides وربطها ببيانات من مصنفات خارجية. قد تختلف العملية قليلاً حسب نوع المخطط الذي تختاره.

### ماذا لو تغير هيكل البيانات الخاص بالمصنف الخارجي الخاص بي؟

إذا تغير هيكل بيانات المصنف الخارجي لديك، فقد تحتاج إلى تحديث مراجع الخلايا في كود Java الخاص بك لضمان بقاء بيانات الرسم البياني دقيقة.

### هل Aspose.Slides متوافق مع أحدث إصدارات Java؟

يتم تحديث Aspose.Slides لجافا بانتظام لضمان توافقه مع أحدث إصدارات جافا. تأكد من التحقق من التحديثات واستخدام أحدث إصدار من المكتبة للحصول على أفضل أداء وتوافق.

### هل يمكنني إضافة مخططات متعددة تشير إلى نفس المصنف الخارجي؟

نعم، يمكنك إضافة عدة مخططات بيانية إلى عرضك التقديمي، بحيث تشير جميعها إلى نفس المصنف الخارجي. ما عليك سوى تكرار الخطوات الموضحة في هذا البرنامج التعليمي لكل مخطط بياني ترغب في إنشائه.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}