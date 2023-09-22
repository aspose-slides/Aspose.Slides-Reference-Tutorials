---
title: ضبط عرض الفجوة في شرائح جافا
linktitle: ضبط عرض الفجوة في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية ضبط عرض الفجوة في شرائح Java باستخدام Aspose.Slides لـ Java. قم بتحسين الرسوم البيانية المرئية لعروض PowerPoint التقديمية الخاصة بك.
type: docs
weight: 21
url: /ar/java/data-manipulation/set-gap-width-java-slides/
---

## مقدمة لإعداد عرض الفجوة في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية تعيين Gap Width لمخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يحدد Gap Width التباعد بين الأعمدة أو الأشرطة في المخطط، مما يسمح لك بالتحكم في المظهر المرئي للمخطط.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java. يمكنك تنزيله من موقع Aspose[هنا](https://releases.aspose.com/slides/java/).

## دليل خطوة بخطوة

اتبع هذه الخطوات لتعيين عرض الفجوة في المخطط باستخدام Aspose.Slides لـ Java:

### 1. قم بإنشاء عرض تقديمي فارغ

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

### 3. أضف مخططًا بالبيانات الافتراضية

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. قم بتعيين فهرس ورقة بيانات الرسم البياني

```java
// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
```

### 5. احصل على مصنف بيانات المخطط

```java
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. أضف سلسلة إلى المخطط

```java
// إضافة سلسلة إلى الرسم البياني
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. أضف فئات إلى المخطط

```java
// إضافة فئات إلى الرسم البياني
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. تعبئة بيانات السلسلة

```java
// تعبئة بيانات السلسلة
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// نشر نقاط بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. قم بتعيين عرض الفجوة

```java
// قم بتعيين قيمة عرض الفجوة
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. احفظ العرض التقديمي

```java
// احفظ العرض التقديمي مع المخطط
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لتعيين عرض الفجوة في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء عرض تقديمي فارغ
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// أضف سلسلة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// أضف الفئات
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// خذ سلسلة الرسم البياني الثانية
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// قم بتعيين قيمة GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// حفظ العرض التقديمي مع الرسم البياني
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تعيين عرض الفجوة للمخطط في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يتيح لك ضبط عرض الفجوة التحكم في التباعد بين الأعمدة أو الأشرطة في المخطط الخاص بك، مما يؤدي إلى تحسين التمثيل المرئي لبياناتك.

## الأسئلة الشائعة

### كيف أقوم بتغيير قيمة عرض الفجوة؟

 لتغيير عرض الفجوة، استخدم`setGapWidth` الطريقة على`ParentSeriesGroup` من سلسلة الرسم البياني. في المثال المقدم، قمنا بتعيين Gap Width على 50، ولكن يمكنك ضبط هذه القيمة حسب التباعد المطلوب.

### هل يمكنني تخصيص خصائص المخطط الأخرى؟

نعم، يوفر Aspose.Slides for Java إمكانات واسعة لتخصيص المخطط. يمكنك تعديل خصائص المخطط المختلفة، مثل الألوان والتسميات والعناوين والمزيد. تحقق من مرجع واجهة برمجة التطبيقات (API) للحصول على معلومات تفصيلية حول خيارات تخصيص المخطط.

### أين يمكنني العثور على المزيد من الموارد والوثائق؟

 يمكنك العثور على وثائق شاملة وموارد إضافية على Aspose.Slides for Java على الموقع[موقع أسبوز](https://reference.aspose.com/slides/java/).