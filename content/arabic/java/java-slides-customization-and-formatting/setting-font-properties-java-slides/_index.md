---
title: ضبط خصائص الخط في شرائح جافا
linktitle: ضبط خصائص الخط في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين خصائص الخط في شرائح Java باستخدام Aspose.Slides لـ Java. يتضمن هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية والأسئلة الشائعة.
type: docs
weight: 15
url: /ar/java/customization-and-formatting/setting-font-properties-java-slides/
---

## مقدمة لإعداد خصائص الخط في شرائح جافا

في هذا البرنامج التعليمي، سنستكشف كيفية تعيين خصائص الخط للنص في شرائح Java باستخدام Aspose.Slides for Java. يمكن تخصيص خصائص الخط مثل الخط الغامق وحجم الخط لتحسين مظهر الشرائح.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إضافة مكتبة Aspose.Slides for Java إلى مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: تهيئة العرض التقديمي

 أولاً، تحتاج إلى تهيئة كائن العرض التقديمي عن طريق تحميل ملف PowerPoint موجود. يستبدل`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## الخطوة 2: إضافة مخطط

في هذا المثال، سنعمل مع مخطط على الشريحة الأولى. يمكنك تغيير فهرس الشرائح وفقًا لاحتياجاتك. سنقوم بإضافة مخطط عمودي متفاوت المسافات وتمكين جدول البيانات.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.setDataTable(true);
```

## الخطوة 3: تخصيص خصائص الخط

الآن، دعونا نخصص خصائص الخط لجدول بيانات المخطط. سنقوم بتعيين الخط ليكون غامقًا ونضبط ارتفاع الخط (حجمه).

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
```

- `setFontBold(NullableBool.True)`: هذا السطر يضبط الخط ليكون غامقًا.
- `setFontHeight(20)`: هذا الخط يضبط ارتفاع الخط على 20 نقطة. يمكنك ضبط هذه القيمة حسب الحاجة.

## الخطوة 4: احفظ العرض التقديمي

وأخيراً، احفظ العرض التقديمي المعدل في ملف جديد. يمكنك تحديد تنسيق الإخراج. وفي هذه الحالة، نقوم بحفظه كملف PPTX.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لإعداد خصائص الخط في شرائح Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.setDataTable(true);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
	chart.getChartDataTable().getTextFormat().getPortionFormat().setFontHeight(20);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تعيين خصائص الخط للنص في شرائح Java باستخدام Aspose.Slides for Java. يمكنك تطبيق هذه التقنيات لتحسين مظهر النص في عروض PowerPoint التقديمية.

## الأسئلة الشائعة

### كيف يمكنني تغيير لون الخط؟

 لتغيير لون الخط استخدم`setFontColor` الطريقة وتحديد اللون المطلوب. على سبيل المثال:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontColor(Color.RED);
```

### هل يمكنني تغيير الخط للنص الآخر في الشرائح؟

نعم، يمكنك تغيير الخط لعناصر النص الأخرى في الشرائح، مثل العناوين والتسميات. استخدم الكائنات والأساليب المناسبة للوصول إلى خصائص الخط وتخصيصها لعناصر نصية محددة.

### كيف أقوم بتعيين نمط الخط المائل؟

 لتعيين نمط الخط إلى الخط المائل، استخدم`setFontItalic` طريقة:

```java
chart.getChartDataTable().getTextFormat().getPortionFormat().setFontItalic(NullableBool.True);
```

 أضبط ال`NullableBool.True` المعلمة حسب الحاجة لتمكين أو تعطيل النمط المائل.

### كيف يمكنني تغيير خط تسميات البيانات في المخطط؟

لتغيير خط تسميات البيانات في المخطط، تحتاج إلى الوصول إلى تنسيق نص تسمية البيانات باستخدام الطرق المناسبة. على سبيل المثال:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0); // قم بتغيير الفهرس حسب الحاجة
series.getLabels().getDefaultDataLabelFormat().getPortionFormat().setFontBold(NullableBool.True);
```

يقوم هذا الرمز بتعيين خط تسميات البيانات في السلسلة الأولى إلى غامق.

### كيف يمكنني تغيير الخط لجزء معين من النص؟

 إذا كنت تريد تغيير الخط لجزء معين من النص داخل عنصر النص، فيمكنك استخدام الخيار`PortionFormat` فصل. قم بالوصول إلى الجزء الذي تريد تعديله ثم قم بتعيين خصائص الخط المطلوبة.

```java
IAutoShape textShape = (IAutoShape)slide.getShapes().get_Item(0); // قم بتغيير الفهرس حسب الحاجة
ITextFrame textFrame = textShape.getTextFrame();
IParagraph paragraph = textFrame.getParagraphs().get_Item(0); // قم بتغيير الفهرس حسب الحاجة
IPortion portion = paragraph.getPortions().get_Item(0); // قم بتغيير الفهرس حسب الحاجة

portion.getPortionFormat().setFontBold(NullableBool.True);
portion.getPortionFormat().setFontHeight(24);
```

يقوم هذا الرمز بتعيين خط الجزء الأول من النص داخل الشكل ليكون غامقًا ويضبط ارتفاع الخط.

### كيف يمكنني تطبيق تغييرات الخط على كافة الشرائح في العرض التقديمي؟

لتطبيق تغييرات الخط على كافة الشرائح في العرض التقديمي، يمكنك التكرار عبر الشرائح وضبط خصائص الخط حسب الحاجة. استخدم حلقة للوصول إلى كل شريحة وعناصر النص الموجودة بداخلها، ثم قم بتخصيص خصائص الخط.

```java
for (ISlide slide : pres.getSlides()) {
    // يمكنك الوصول إلى خصائص خطوط عناصر النص وتخصيصها هنا
}
```