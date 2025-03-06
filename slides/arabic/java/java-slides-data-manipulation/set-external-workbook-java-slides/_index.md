---
title: قم بتعيين المصنف الخارجي في شرائح Java
linktitle: قم بتعيين المصنف الخارجي في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين مصنفات خارجية في Java Slides باستخدام Aspose.Slides لـ Java. قم بإنشاء عروض تقديمية ديناميكية باستخدام تكامل بيانات Excel.
weight: 19
url: /ar/java/data-manipulation/set-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتعيين المصنف الخارجي في شرائح جافا

في هذا البرنامج التعليمي، سنستكشف كيفية تعيين مصنف خارجي في Java Slides باستخدام Aspose.Slides. سوف تتعلم كيفية إنشاء عرض تقديمي لـ PowerPoint باستخدام مخطط يشير إلى البيانات من مصنف Excel خارجي. بنهاية هذا الدليل، سيكون لديك فهم واضح لكيفية دمج البيانات الخارجية في عروض Java Slides التقديمية.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
- تمت إضافة مكتبة Aspose.Slides لـ Java إلى مشروعك.
- مصنف Excel يحتوي على البيانات التي تريد الرجوع إليها في العرض التقديمي الخاص بك.

## الخطوة 1: إنشاء عرض تقديمي جديد

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

نبدأ بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides.

## الخطوة 2: إضافة مخطط

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

بعد ذلك، نقوم بإدراج مخطط دائري في العرض التقديمي. يمكنك تخصيص نوع المخطط وموضعه حسب الحاجة.

## الخطوة 3: الوصول إلى المصنف الخارجي

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 للوصول إلى المصنف الخارجي، نستخدم`setExternalWorkbook` الطريقة وتوفير المسار إلى مصنف Excel الذي يحتوي على البيانات.

## الخطوة 4: ربط بيانات المخطط

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

نقوم بربط المخطط بالبيانات من المصنف الخارجي عن طريق تحديد مراجع الخلايا للسلاسل والفئات.

## الخطوة 5: احفظ العرض التقديمي

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

وأخيرا، نقوم بحفظ العرض التقديمي مع مرجع المصنف الخارجي كملف PowerPoint.

## أكمل كود المصدر لتعيين المصنف الخارجي في شرائح Java

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

في هذا البرنامج التعليمي، تعلمنا كيفية تعيين مصنف خارجي في Java Slides باستخدام Aspose.Slides. يمكنك الآن إنشاء عروض تقديمية تشير ديناميكيًا إلى البيانات من مصنفات Excel، مما يعزز مرونة الشرائح وتفاعلها.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ Java؟

يمكن تثبيت Aspose.Slides for Java عن طريق إضافة المكتبة إلى مشروع Java الخاص بك. يمكنك تنزيل المكتبة من موقع Aspose واتباع تعليمات التثبيت المتوفرة في الوثائق.

### هل يمكنني استخدام أنواع مختلفة من المخططات مع المصنفات الخارجية؟

نعم، يمكنك استخدام أنواع المخططات المختلفة التي يدعمها Aspose.Slides وربطها بالبيانات من المصنفات الخارجية. قد تختلف العملية قليلاً حسب نوع المخطط الذي تختاره.

### ماذا لو تغيرت بنية بيانات المصنف الخارجي الخاص بي؟

إذا تغيرت بنية بيانات المصنف الخارجي، فقد تحتاج إلى تحديث مراجع الخلايا في كود Java الخاص بك لضمان بقاء بيانات المخطط دقيقة.

### هل Aspose.Slides متوافق مع أحدث إصدارات Java؟

يتم تحديث Aspose.Slides for Java بانتظام لضمان التوافق مع أحدث إصدارات Java. تأكد من التحقق من وجود تحديثات واستخدام أحدث إصدار من المكتبة للحصول على الأداء الأمثل والتوافق.

### هل يمكنني إضافة مخططات متعددة تشير إلى نفس المصنف الخارجي؟

نعم، يمكنك إضافة مخططات متعددة إلى العرض التقديمي الخاص بك، تشير جميعها إلى نفس المصنف الخارجي. ما عليك سوى تكرار الخطوات الموضحة في هذا البرنامج التعليمي لكل مخطط تريد إنشاءه.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
