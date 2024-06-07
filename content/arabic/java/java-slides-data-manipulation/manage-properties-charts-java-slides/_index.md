---
title: إدارة مخططات الخصائص في شرائح جافا
linktitle: إدارة مخططات الخصائص في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعلم كيفية إنشاء مخططات مذهلة وإدارة الخصائص في شرائح Java باستخدام Aspose.Slides. دليل خطوة بخطوة مع الكود المصدري للعروض التقديمية القوية.
type: docs
weight: 13
url: /ar/java/data-manipulation/manage-properties-charts-java-slides/
---

## مقدمة لإدارة الخصائص والمخططات في شرائح Java باستخدام Aspose.Slides

في هذا البرنامج التعليمي، سوف نستكشف كيفية إدارة الخصائص وإنشاء المخططات في شرائح Java باستخدام Aspose.Slides. Aspose.Slides عبارة عن واجهة برمجة تطبيقات Java قوية للعمل مع عروض PowerPoint التقديمية. سنتناول العملية خطوة بخطوة، بما في ذلك أمثلة التعليمات البرمجية المصدر.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides الخاصة بـ Java وإعدادها في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## إضافة مخطط إلى شريحة

لإضافة مخطط إلى شريحة، اتبع الخطوات التالية:

1. قم باستيراد الفئات الضرورية وإنشاء مثيل لفئة العرض التقديمي.

```java
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
```

2. قم بالوصول إلى الشريحة التي تريد إضافة المخطط إليها. في هذا المثال، نصل إلى الشريحة الأولى.

```java
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
```

3. إضافة مخطط بالبيانات الافتراضية. في هذه الحالة، نقوم بإضافة مخطط StackedColumn3D.

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## إعداد بيانات الرسم البياني

لتعيين بيانات المخطط، نحتاج إلى إنشاء مصنف بيانات المخطط وإضافة سلسلة وفئات. اتبع الخطوات التالية:

4. قم بتعيين فهرس ورقة بيانات المخطط.

```java
// إعداد فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
```

5. احصل على مصنف بيانات المخطط.

```java
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. إضافة سلسلة إلى الرسم البياني. في هذا المثال، نضيف سلسلتين باسم "السلسلة 1" و"السلسلة 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. إضافة فئات إلى الرسم البياني. وهنا نضيف ثلاث فئات.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ضبط خصائص التدوير ثلاثي الأبعاد

الآن، لنقم بتعيين خصائص التدوير ثلاثي الأبعاد للمخطط:

8. ضبط محاور الزاوية اليمنى.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. اضبط زوايا الدوران للمحورين X وY. في هذا المثال، نقوم بتدوير X بمقدار 40 درجة وY بمقدار 270 درجة.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. اضبط نسبة العمق على 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## تعبئة بيانات السلسلة

11. خذ سلسلة المخططات الثانية واملأها بنقاط البيانات.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// تعبئة بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ضبط التداخل

12. قم بتعيين قيمة التداخل للسلسلة. على سبيل المثال، يمكنك ضبطه على 100 لعدم وجود تداخل.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## حفظ العرض التقديمي

وأخيرا، احفظ العرض التقديمي على القرص.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي مكدس ثلاثي الأبعاد بخصائص مخصصة باستخدام Aspose.Slides في Java.

## أكمل كود المصدر لإدارة مخططات الخصائص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لفئة العرض التقديمي
Presentation presentation = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide slide = presentation.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// ضبط خصائص التدوير ثلاثي الأبعاد
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// خذ سلسلة الرسم البياني الثانية
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// تعيين قيمة التداخل
series.getParentSeriesGroup().setOverlap((byte) 100);
// كتابة العرض التقديمي على القرص
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا البرنامج التعليمي، بحثنا في عالم إدارة الخصائص وإنشاء المخططات في شرائح Java باستخدام Aspose.Slides. Aspose.Slides عبارة عن واجهة برمجة تطبيقات Java قوية تمكن المطورين من العمل مع عروض PowerPoint التقديمية بكفاءة. لقد قمنا بتغطية الخطوات الأساسية وقدمنا أمثلة على التعليمات البرمجية المصدر لإرشادك خلال العملية.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

 يمكنك تغيير نوع المخطط عن طريق تعديل`ChartType`المعلمة عند إضافة الرسم البياني. راجع وثائق Aspose.Slides للتعرف على أنواع المخططات المتوفرة.

### هل يمكنني تخصيص ألوان الرسم البياني؟

نعم، يمكنك تخصيص ألوان المخطط عن طريق تعيين خصائص التعبئة لنقاط البيانات المتسلسلة أو الفئات.

### كيف يمكنني إضافة المزيد من نقاط البيانات إلى سلسلة؟

 يمكنك إضافة المزيد من نقاط البيانات إلى سلسلة باستخدام`series.getDataPoints().addDataPointForBarSeries()` الطريقة وتحديد الخلية التي تحتوي على قيمة البيانات.

### كيف يمكنني ضبط زاوية دوران مختلفة؟

 لتعيين زاوية دوران مختلفة للمحورين X وY، استخدم`chart.getRotation3D().setRotationX()` و`chart.getRotation3D().setRotationY()` مع قيم الزاوية المطلوبة.

### ما هي الخصائص ثلاثية الأبعاد الأخرى التي يمكنني تخصيصها؟

يمكنك استكشاف الخصائص ثلاثية الأبعاد الأخرى للمخطط، مثل العمق والمنظور والإضاءة، من خلال الرجوع إلى وثائق Aspose.Slides.