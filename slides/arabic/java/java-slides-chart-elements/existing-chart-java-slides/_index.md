---
title: الرسم البياني الموجود في شرائح جافا
linktitle: الرسم البياني الموجود في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية الخاصة بك باستخدام Aspose.Slides لـ Java. تعلم كيفية تعديل المخططات الموجودة برمجياً. دليل خطوة بخطوة مع الكود المصدري لتخصيص المخطط.
weight: 12
url: /ar/java/chart-elements/existing-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة إلى المخطط الموجود في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنوضح كيفية تعديل مخطط موجود في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. سنستعرض خطوات تغيير بيانات المخطط وأسماء الفئات وأسماء السلاسل وإضافة سلسلة جديدة إلى المخطط. تأكد من إعداد Aspose.Slides for Java في مشروعك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لمكتبة Java المضمنة في مشروعك.
2. عرض تقديمي لـ PowerPoint موجود يحتوي على مخطط تريد تعديله.
3. إعداد بيئة تطوير جافا.

## الخطوة 1: قم بتحميل العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: الوصول إلى الشريحة والمخطط

```java
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);

// قم بالوصول إلى المخطط الموجود على الشريحة
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## الخطوة 3: تغيير بيانات المخطط وأسماء الفئات

```java
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// تغيير أسماء فئات المخطط
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## الخطوة 4: تحديث سلسلة الرسم البياني الأولى

```java
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// تحديث اسم المسلسل
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// تحديث بيانات السلسلة
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## الخطوة 5: تحديث سلسلة المخططات الثانية

```java
// خذ سلسلة الرسم البياني الثاني
series = chart.getChartData().getSeries().get_Item(1);

// تحديث اسم المسلسل
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// تحديث بيانات السلسلة
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## الخطوة 6: إضافة سلسلة جديدة إلى المخطط

```java
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// خذ سلسلة الرسم البياني الثالثة
series = chart.getChartData().getSeries().get_Item(2);

// تعبئة بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## الخطوة 7: تغيير نوع المخطط

```java
//قم بتغيير نوع المخطط إلى اسطوانة متفاوتة المسافات
chart.setType(ChartType.ClusteredCylinder);
```

## الخطوة 8: احفظ العرض التقديمي المعدل

```java
// احفظ العرض التقديمي بالمخطط المعدل
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في تعديل مخطط موجود في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك الآن استخدام هذا الرمز لتخصيص المخططات في عروض PowerPoint التقديمية الخاصة بك برمجياً.

## أكمل كود المصدر للمخطط الموجود في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX// إنشاء فئة العرض التقديمي التي تمثل ملف PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// الوصول إلى أول علامة شريحة
ISlide sld = pres.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = (IChart) sld.getShapes().get_Item(0);
// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// تغيير اسم فئة المخطط
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// الآن تحديث بيانات السلسلة
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// تعديل اسم المسلسل
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// الآن تحديث بيانات السلسلة
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// تعديل اسم المسلسل
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// الآن، إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// خذ سلسلة الرسم البياني الثالثة
series = chart.getChartData().getSeries().get_Item(2);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// حفظ العرض التقديمي مع الرسم البياني
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## خاتمة

في هذا البرنامج التعليمي الشامل، تعلمنا كيفية تعديل مخطط موجود في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. باتباع الدليل الموضح خطوة بخطوة واستخدام أمثلة التعليمات البرمجية المصدر، يمكنك تخصيص المخططات وتحديثها بسهولة لتلبية متطلباتك المحددة. فيما يلي ملخص لما قمنا بتغطيته:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

 يمكنك تغيير نوع المخطط باستخدام`chart.setType(ChartType.ChartTypeHere)` طريقة. يستبدل`ChartTypeHere` مع نوع المخطط المطلوب، مثل`ChartType.ClusteredCylinder` في مثالنا.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى سلسلة؟

 نعم، يمكنك إضافة المزيد من نقاط البيانات إلى سلسلة باستخدام`series.getDataPoints().addDataPointForBarSeries(cell)` طريقة. تأكد من توفير بيانات الخلية المناسبة.

### كيف أقوم بتحديث أسماء الفئات؟

 يمكنك تحديث أسماء الفئات باستخدام`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` لتعيين أسماء الفئات الجديدة.

### كيف يمكنني تعديل أسماء المسلسلات؟

 لتعديل أسماء السلسلة، استخدم`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` لتعيين أسماء المسلسلات الجديدة.

### هل هناك طريقة لإزالة سلسلة من الرسم البياني؟

 نعم، يمكنك إزالة سلسلة من المخطط باستخدام`chart.getChartData().getSeries().removeAt(index)` الطريقة، حيث`index`هو فهرس السلسلة التي تريد إزالتها.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
