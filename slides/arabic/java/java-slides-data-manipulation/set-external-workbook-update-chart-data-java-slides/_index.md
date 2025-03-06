---
title: قم بتعيين المصنف الخارجي مع تحديث بيانات المخطط في شرائح Java
linktitle: قم بتعيين المصنف الخارجي مع تحديث بيانات المخطط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين المصنفات الخارجية وتحديث بيانات المخطط في Java Slides باستخدام Aspose.Slides for Java. تعزيز مهاراتك في أتمتة PowerPoint.
weight: 20
url: /ar/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لتعيين المصنف الخارجي مع تحديث بيانات المخطط في شرائح Java

في هذا الدليل الشامل، سنرشدك خلال عملية إعداد مصنف خارجي يحتوي على بيانات مخطط محدثة في Java Slides باستخدام Aspose.Slides for Java API. تسمح لك هذه المكتبة القوية بمعالجة عروض PowerPoint التقديمية برمجياً، مما يجعل من السهل أتمتة المهام مثل تحديث بيانات المخطط من مصدر خارجي. بحلول نهاية هذا البرنامج التعليمي، سيكون لديك فهم واضح لكيفية تحقيق هذه المهمة من خلال تعليمات خطوة بخطوة وكود Java المصاحب.

## المتطلبات الأساسية

قبل أن نتعمق في التنفيذ، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for Java: يجب أن تكون مكتبة Aspose.Slides for Java مثبتة لديك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).

2. بيئة تطوير Java: تأكد من إعداد بيئة تطوير Java على نظامك.

## الخطوة 1: إنشاء عرض تقديمي جديد

للبدء، لنقم بإنشاء عرض تقديمي جديد لـ PowerPoint باستخدام Aspose.Slides لـ Java. إليك كود Java للقيام بذلك:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط

الآن، دعونا نضيف مخططًا لعرضنا التقديمي. سنقوم بإنشاء مخطط دائري في هذا المثال:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## الخطوة 3: تعيين المصنف الخارجي

هذا هو المكان الذي قمنا فيه بتعيين المصنف الخارجي كمصدر بيانات لمخططنا. يتعين عليك توفير عنوان URL للمصنف الخارجي، حتى لو لم يكن موجودًا في الوقت الحالي:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://المسار/غير موجود/موجود"، خطأ)؛
```

## الخطوة 4: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي ببيانات المخطط المحدثة:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## أكمل كود المصدر لتعيين المصنف الخارجي مع تحديث بيانات المخطط في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://المسار/غير موجود/موجود"، خطأ)؛
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

تهانينا! لقد تعلمت كيفية تعيين مصنف خارجي يحتوي على بيانات مخطط محدثة في Java Slides باستخدام Aspose.Slides for Java. يمكن أن يكون هذا مفيدًا بشكل لا يصدق لتحديث المخططات ديناميكيًا في عروض PowerPoint التقديمية من مصادر البيانات الخارجية.

## الأسئلة الشائعة

### كيف يمكنني تحديث بيانات المصنف الخارجي للمخطط؟

لتحديث بيانات المصنف الخارجي للمخطط، ما عليك سوى تعديل البيانات الموجودة في المصنف الخارجي على عنوان URL المحدد. في المرة التالية التي تفتح فيها العرض التقديمي، سيقوم Aspose.Slides for Java بجلب البيانات المحدثة من المصنف الخارجي وتحديث المخطط وفقًا لذلك.

### هل يمكنني استخدام ملف محلي كمصنف خارجي؟

نعم، يمكنك استخدام ملف محلي كمصنف خارجي عن طريق توفير مسار الملف بدلاً من عنوان URL. فقط تأكد من أن مسار الملف صحيح ويمكن الوصول إليه من تطبيق Java الخاص بك.

### هل هناك أي قيود على استخدام المصنفات الخارجية مع Aspose.Slides لـ Java؟

أثناء استخدام المصنفات الخارجية يعد ميزة قوية، ضع في اعتبارك أن توفر بيانات المصنف الخارجي يعتمد على إمكانية الوصول إليها على عنوان URL أو مسار الملف المتوفر. تأكد من توفر مصدر البيانات الخارجي عند فتح العرض التقديمي لتجنب مشكلات استرداد البيانات.

### هل يمكنني تخصيص مظهر المخطط بعد إعداد المصنف الخارجي؟

نعم، يمكنك تخصيص مظهر المخطط، بما في ذلك عنوانه وتسمياته وألوانه والمزيد، حتى بعد إعداد المصنف الخارجي. يوفر Aspose.Slides for Java خيارات واسعة لتنسيق المخططات لتلبية احتياجاتك.

### أين يمكنني العثور على مزيد من الوثائق والموارد الخاصة بـ Aspose.Slides لـ Java؟

 للحصول على وثائق مفصلة وموارد إضافية، قم بزيارة وثائق Aspose.Slides for Java على[هنا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
