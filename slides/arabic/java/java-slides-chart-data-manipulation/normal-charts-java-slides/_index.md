---
"description": "أنشئ مخططات بيانية عادية في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع الكود المصدري لإنشاء المخططات البيانية وتخصيصها وحفظها في عروض PowerPoint التقديمية."
"linktitle": "المخططات العادية في شرائح جافا"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "المخططات العادية في شرائح جافا"
"url": "/ar/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# المخططات العادية في شرائح جافا


## مقدمة إلى المخططات العادية في شرائح Java

في هذا البرنامج التعليمي، سنشرح عملية إنشاء مخططات بيانية عادية في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. سنستخدم تعليمات خطوة بخطوة، بالإضافة إلى الكود المصدري، لتوضيح كيفية إنشاء مخطط بياني عمودي مجمع في عرض تقديمي على PowerPoint.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. تم تثبيت Aspose.Slides لـ Java API.
2. تم إعداد بيئة تطوير Java.
3. المعرفة الأساسية ببرمجة جافا.

## الخطوة 1: إعداد المشروع

تأكد من وجود مجلد لمشروعك. لنسمِّه "مجلد مستنداتك" كما هو مذكور في الكود. يمكنك استبداله بالمسار الفعلي لمجلد مشروعك.

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## الخطوة 2: إنشاء عرض تقديمي

الآن، دعنا نقوم بإنشاء عرض تقديمي على PowerPoint والوصول إلى الشريحة الأولى منه.

```java
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation pres = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```

## الخطوة 3: إضافة مخطط

سنضيف مخططًا عموديًا مجمعًا إلى الشريحة ونحدد عنوانه.

```java
// إضافة مخطط بالبيانات الافتراضية
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// عنوان مخطط الإعداد
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## الخطوة 4: إعداد بيانات الرسم البياني

بعد ذلك، سنقوم بتعيين بيانات الرسم البياني عن طريق تحديد السلسلة والفئات.

```java
// تعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;

// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// حذف السلسلة والفئات المولدة افتراضيًا
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## الخطوة 5: ملء بيانات السلسلة

الآن، دعونا نملأ نقاط بيانات السلسلة للرسم البياني.

```java
// خذ أول سلسلة مخططات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// تعيين لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);

// ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// تعيين لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## الخطوة 6: تخصيص العلامات

دعونا نقوم بتخصيص تسميات البيانات لسلسلة المخططات البيانية.

```java
// سيظهر الملصق الأول اسم الفئة
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// إظهار القيمة للعلامة الثالثة مع اسم السلسلة والفاصل
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## الخطوة 7: حفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي مع الرسم البياني في دليل المشروع الخاص بك.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي مجمع في عرض تقديمي باوربوينت باستخدام Aspose.Slides لجافا. يمكنك تخصيص هذا المخطط بشكل أكبر وفقًا لاحتياجاتك.

## كود المصدر الكامل للمخططات العادية في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// إنشاء فئة عرض تقديمي تمثل ملف PPTX
Presentation pres = new Presentation();
// الوصول إلى الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
// إضافة مخطط بالبيانات الافتراضية
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// عنوان مخطط الإعداد
// Chart.getChartTitle().getTextFrameForOverriding().setText("عنوان العينة");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// تعيين السلسلة الأولى لإظهار القيم
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// ضبط فهرس ورقة بيانات الرسم البياني
int defaultWorksheetIndex = 0;
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// حذف السلسلة والفئات المولدة افتراضيًا
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// إضافة سلسلة جديدة
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// إضافة فئات جديدة
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// خذ أول سلسلة مخططات
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// تعيين لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// خذ سلسلة الرسم البياني الثانية
series = chart.getChartData().getSeries().get_Item(1);
// يتم الآن ملء بيانات السلسلة
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// تعيين لون التعبئة للسلسلة
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// سيتم عرض العلامة الأولى باسم الفئة
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// إظهار القيمة للعلامة الثالثة
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// حفظ العرض التقديمي مع الرسم البياني
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء مخططات بيانية عادية في Java Slides باستخدام واجهة برمجة تطبيقات Aspose.Slides لـ Java. اتبعنا دليلاً خطوة بخطوة مع الكود المصدري لإنشاء مخطط بياني عمودي مجمع في عرض تقديمي على PowerPoint.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع الرسم البياني؟

لتغيير نوع الرسم البياني، قم بتعديل `ChartType` المعلمة عند إضافة الرسم البياني باستخدام `sld.getShapes().addChart()`يمكنك الاختيار من بين أنواع المخططات المتنوعة المتوفرة في Aspose.Slides.

### هل يمكنني تغيير ألوان سلسلة الرسم البياني؟

نعم، يمكنك تغيير ألوان سلسلة الرسم البياني عن طريق تعيين لون التعبئة لكل سلسلة باستخدام `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### كيف أضيف المزيد من الفئات أو السلاسل إلى الرسم البياني؟

يمكنك إضافة المزيد من الفئات أو السلاسل إلى الرسم البياني عن طريق إضافة نقاط بيانات جديدة وعلامات باستخدام `chart.getChartData().getCategories().add()` و `chart.getChartData().getSeries().add()` طُرق.

### كيف يمكنني تخصيص عنوان الرسم البياني بشكل أكبر؟

يمكنك تخصيص عنوان الرسم البياني بشكل أكبر عن طريق تعديل خصائص `chart.getChartTitle()` مثل محاذاة النص وحجم الخط واللون.

### كيف يمكنني حفظ الرسم البياني بتنسيق ملف مختلف؟

لحفظ الرسم البياني بتنسيق ملف مختلف، قم بتغيير `SaveFormat` المعلمة في `pres.save()` الطريقة إلى التنسيق المطلوب (على سبيل المثال، PDF، PNG، JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}