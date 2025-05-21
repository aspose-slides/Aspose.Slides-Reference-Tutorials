---
"description": "حسّن عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تعلّم كيفية تعديل المخططات البيانية الحالية برمجيًا. دليل خطوة بخطوة مع الكود المصدري لتخصيص المخططات البيانية."
"linktitle": "مخطط موجود في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مخطط موجود في شرائح Java"
"url": "/ar/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مخطط موجود في شرائح Java


## مقدمة إلى المخططات الموجودة في شرائح Java باستخدام Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنشرح كيفية تعديل مخطط موجود في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. سنشرح خطوات تغيير بيانات المخطط، وأسماء الفئات، وأسماء السلاسل، وإضافة سلسلة جديدة إليه. تأكد من تثبيت Aspose.Slides لجافا في مشروعك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تضمين Aspose.Slides لمكتبة Java في مشروعك.
2. عرض تقديمي موجود في PowerPoint يحتوي على مخطط تريد تعديله.
3. تم إعداد بيئة تطوير Java.

## الخطوة 1: تحميل العرض التقديمي

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## الخطوة 2: الوصول إلى الشريحة والمخطط

```java
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);

// الوصول إلى الرسم البياني على الشريحة
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## الخطوة 3: تغيير بيانات الرسم البياني وأسماء الفئات

```java
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// تغيير أسماء فئات الرسم البياني
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## الخطوة 4: تحديث سلسلة المخططات الأولى

```java
// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// تحديث اسم السلسلة
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// تحديث بيانات السلسلة
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## الخطوة 5: تحديث سلسلة المخططات الثانية

```java
// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);

// تحديث اسم السلسلة
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// تحديث بيانات السلسلة
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## الخطوة 6: إضافة سلسلة جديدة إلى الرسم البياني

```java
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// خذ سلسلة المخططات الثالثة
series = chart.getChartData().getSeries().get_Item(2);

// ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## الخطوة 7: تغيير نوع الرسم البياني

```java
// تغيير نوع الرسم البياني إلى أسطوانة مجمعة
chart.setType(ChartType.ClusteredCylinder);
```

## الخطوة 8: حفظ العرض التقديمي المعدّل

```java
// احفظ العرض التقديمي بالمخطط المعدل
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في تعديل مخطط موجود في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يمكنك الآن استخدام هذا الكود لتخصيص المخططات في عروض PowerPoint التقديمية برمجيًا.

## كود المصدر الكامل للمخطط الموجود في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء فئة عرض تقديمي تمثل ملف PPTX// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = (IChart) sld.getShapes().get_Item(0);
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// تغيير اسم فئة الرسم البياني
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// خذ أول سلسلة مخططات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// يتم الآن تحديث بيانات السلسلة
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// تعديل اسم السلسلة
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// سلسلة مخططات Take Second
series = chart.getChartData().getSeries().get_Item(1);
// يتم الآن تحديث بيانات السلسلة
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// تعديل اسم السلسلة
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// الآن، إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// خذ سلسلة الرسم البياني الثالثة
series = chart.getChartData().getSeries().get_Item(2);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// حفظ العرض التقديمي مع الرسم البياني
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## خاتمة

في هذا البرنامج التعليمي الشامل، تعلمنا كيفية تعديل مخطط موجود في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. باتباع الدليل المفصل واستخدام أمثلة من الكود المصدري، يمكنك بسهولة تخصيص المخططات وتحديثها لتلبية متطلباتك الخاصة. إليك ملخص لما تناولناه:

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

يمكنك تغيير نوع الرسم البياني باستخدام `chart.setType(ChartType.ChartTypeHere)` الطريقة. استبدال `ChartTypeHere` مع نوع الرسم البياني المطلوب، مثل `ChartType.ClusteredCylinder` في مثالنا.

### هل يمكنني إضافة المزيد من نقاط البيانات إلى سلسلة؟

نعم، يمكنك إضافة المزيد من نقاط البيانات إلى سلسلة باستخدام `series.getDataPoints().addDataPointForBarSeries(cell)` الطريقة. تأكد من توفير بيانات الخلية المناسبة.

### كيف أقوم بتحديث أسماء الفئات؟

يمكنك تحديث أسماء الفئات باستخدام `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` لتعيين أسماء الفئات الجديدة.

### كيف يمكنني تعديل أسماء السلسلة؟

لتعديل أسماء السلسلة، استخدم `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` لتعيين أسماء السلسلة الجديدة.

### هل هناك طريقة لإزالة سلسلة من الرسم البياني؟

نعم، يمكنك إزالة سلسلة من الرسم البياني باستخدام `chart.getChartData().getSeries().removeAt(index)` الطريقة، حيث `index` هو فهرس السلسلة التي تريد إزالتها.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}