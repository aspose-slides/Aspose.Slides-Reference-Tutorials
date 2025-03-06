---
title: تحديد محور الموضع في شرائح جافا
linktitle: تحديد محور الموضع في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين الرسوم البيانية الخاصة بك باستخدام Aspose.Slides لـ Java. تعرف على كيفية تعيين محور الموضع في شرائح Java، وإنشاء عروض تقديمية مذهلة، وتخصيص تخطيطات المخططات بسهولة.
weight: 16
url: /ar/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# تحديد محور الموضع في شرائح جافا


## مقدمة لإعداد محور الموضع في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سوف نتعلم كيفية تعيين محور الموضع في المخطط باستخدام Aspose.Slides لـ Java. يمكن أن يكون تحديد موضع المحور مفيدًا عندما تريد تخصيص مظهر المخطط وتخطيطه. سنقوم بإنشاء مخطط عمودي متفاوت المسافات وضبط موضع المحور الأفقي بين الفئات.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for Java وإعدادها في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي

أولاً، لنقم بإنشاء عرض تقديمي جديد للعمل معه:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 تأكد من استبدال`"Your Document Directory"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: إضافة مخطط

بعد ذلك، سنضيف مخططًا عموديًا متفاوت المسافات إلى الشريحة. نحدد نوع المخطط وموضعه (إحداثيات x وy) وأبعاده (العرض والارتفاع):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

لقد أضفنا هنا مخططًا عموديًا متفاوت المسافات في الموضع (50، 50) بعرض 450 وارتفاع 300. ويمكنك ضبط هذه القيم حسب الحاجة.

## الخطوة 3: تحديد محور الموضع

لتعيين محور الموضع بين الفئات، يمكنك استخدام الكود التالي:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

يقوم هذا الرمز بتعيين المحور الأفقي الذي سيتم عرضه بين الفئات، وهو ما يمكن أن يكون مفيدًا لتخطيطات مخططات معينة.

## الخطوة 4: حفظ العرض التقديمي

أخيرًا، لنحفظ العرض التقديمي بالمخطط:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 يستبدل`"AsposeClusteredColumnChart.pptx"` مع اسم الملف المطلوب.

هذا كل شيء! لقد نجحت في إنشاء مخطط عمودي متفاوت المسافات وتعيين محور الموضع بين الفئات باستخدام Aspose.Slides لـ Java.

## كود المصدر الكامل
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية تعيين محور الموضع في المخطط باستخدام Aspose.Slides لـ Java. باتباع الخطوات الموضحة في هذا الدليل، تعلمت كيفية إنشاء مخطط عمودي متفاوت المسافات وتخصيص مظهره عن طريق وضع المحور الأفقي بين الفئات. يوفر Aspose.Slides for Java ميزات قوية للعمل مع المخططات والعروض التقديمية، مما يجعله أداة قيمة لمطوري Java.

## الأسئلة الشائعة

### كيف يمكنني تخصيص المخطط بشكل أكبر؟

يمكنك تخصيص جوانب مختلفة من المخطط، بما في ذلك سلسلة البيانات وعنوان المخطط ووسائل الإيضاح والمزيد. الرجوع إلى[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) للحصول على تعليمات وأمثلة مفصلة.

### هل يمكنني تغيير نوع الرسم البياني؟

 نعم، يمكنك تغيير نوع المخطط عن طريق تعديل`ChartType` المعلمة عند إضافة الرسم البياني. يدعم Aspose.Slides for Java أنواعًا مختلفة من المخططات مثل المخططات الشريطية والمخططات الخطية والمزيد.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟

 يمكنك العثور على وثائق شاملة ومزيد من الأمثلة على[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/) صفحة.

تذكر التخلص من كائن العرض التقديمي عند الانتهاء منه لتحرير موارد النظام:

```java
if (pres != null) pres.dispose();
```

هذا كل شيء لهذا البرنامج التعليمي. لقد تعلمت كيفية تعيين محور الموضع في المخطط باستخدام Aspose.Slides لـ Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
