---
"description": "تعرّف على كيفية ضبط عرض الفجوة في شرائح جافا باستخدام Aspose.Slides لجافا. حسّن عرض المخططات في عروض PowerPoint التقديمية."
"linktitle": "تعيين عرض الفجوة في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين عرض الفجوة في شرائح Java"
"url": "/ar/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين عرض الفجوة في شرائح Java


## مقدمة لضبط عرض الفجوة في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية ضبط عرض الفجوة في مخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يُحدد عرض الفجوة المسافة بين الأعمدة أو الأشرطة في المخطط، مما يتيح لك التحكم في مظهره المرئي.

## المتطلبات الأساسية

قبل البدء، تأكد من تثبيت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من موقع Aspose الإلكتروني. [هنا](https://releases.aspose.com/slides/java/).

## دليل خطوة بخطوة

اتبع الخطوات التالية لتعيين عرض الفجوة في مخطط باستخدام Aspose.Slides لـ Java:

### 1. إنشاء عرض تقديمي فارغ

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء عرض تقديمي فارغ 
Presentation presentation = new Presentation();
```

### 2. الوصول إلى الشريحة الأولى

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. إضافة مخطط بالبيانات الافتراضية

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. اضبط فهرس ورقة بيانات الرسم البياني

```java
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
```

### 5. احصل على مصنف بيانات الرسم البياني

```java
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. إضافة سلسلة إلى الرسم البياني

```java
// إضافة سلسلة إلى الرسم البياني
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. إضافة فئات إلى الرسم البياني

```java
// إضافة فئات إلى الرسم البياني
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. ملء بيانات السلسلة

```java
// ملء بيانات السلسلة
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// ملء نقاط بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. اضبط عرض الفجوة

```java
// تعيين قيمة عرض الفجوة
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. احفظ العرض التقديمي

```java
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## الكود المصدر الكامل لتعيين عرض الفجوة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ 
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// إضافة سلسلة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// إضافة الفئات
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// خذ سلسلة الرسم البياني الثانية
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// تعيين قيمة GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية ضبط عرض الفجوة في مخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. يتيح لك ضبط عرض الفجوة التحكم في المسافة بين الأعمدة أو الأشرطة في مخططك، مما يُحسّن العرض المرئي لبياناتك.

## الأسئلة الشائعة

### كيف يمكنني تغيير قيمة عرض الفجوة؟

لتغيير عرض الفجوة، استخدم `setGapWidth` الطريقة على `ParentSeriesGroup` في المثال الموضح، قمنا بتعيين عرض الفجوة إلى ٥٠، ولكن يمكنك تعديل هذه القيمة حسب التباعد المطلوب.

### هل يمكنني تخصيص خصائص أخرى للرسم البياني؟

نعم، يوفر Aspose.Slides لجافا إمكانيات واسعة لتخصيص المخططات. يمكنك تعديل خصائص متنوعة للمخططات، مثل الألوان والتسميات والعناوين وغيرها. راجع مرجع واجهة برمجة التطبيقات (API Reference) لمزيد من المعلومات حول خيارات تخصيص المخططات.

### أين يمكنني العثور على المزيد من الموارد والوثائق؟

يمكنك العثور على وثائق شاملة وموارد إضافية حول Aspose.Slides for Java على [موقع Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}