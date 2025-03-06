---
title: التحويل بدون خيارات XPS في شرائح Java
linktitle: التحويل بدون خيارات XPS في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تحويل عروض PowerPoint التقديمية إلى تنسيق XPS باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع كود المصدر.
weight: 33
url: /ar/java/presentation-conversion/convert-without-xps-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة قم بتحويل PowerPoint إلى XPS بدون خيارات XPS في Aspose.Slides لـ Java

في هذا البرنامج التعليمي، سنرشدك خلال عملية تحويل عرض PowerPoint التقديمي إلى مستند XPS (مواصفات ورق XML) باستخدام Aspose.Slides لـ Java دون تحديد أي خيارات XPS. سنزودك بتعليمات خطوة بخطوة وكود مصدر Java لتحقيق هذه المهمة.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for Java: تأكد من تثبيت مكتبة Aspose.Slides for Java وتكوينها في مشروع Java الخاص بك. يمكنك تنزيله من[Aspose.Slides لموقع جافا](https://downloads.aspose.com/slides/java).

2. بيئة تطوير جافا: يجب أن يكون لديك بيئة تطوير جافا مثبتة على جهاز الكمبيوتر الخاص بك.

## الخطوة 1: استيراد Aspose.Slides إلى Java

في مشروع Java الخاص بك، قم باستيراد فئات Aspose.Slides for Java الضرورية في بداية ملف Java الخاص بك:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: قم بتحميل عرض PowerPoint التقديمي

الآن، سنقوم بتحميل عرض PowerPoint التقديمي الذي تريد تحويله إلى XPS. يستبدل`"Your Document Directory"` بالمسار الفعلي لملف عرض PowerPoint التقديمي الخاص بك:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";

// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

 تأكد من استبدال`"Convert_XPS.pptx"` بالاسم الفعلي لملف PowerPoint الخاص بك.

## الخطوة 3: احفظ باسم XPS بدون خيارات XPS

باستخدام Aspose.Slides for Java، يمكنك بسهولة حفظ العرض التقديمي الذي تم تحميله كمستند XPS دون تحديد أي خيارات XPS. وإليك كيف يمكنك القيام بذلك:

```java
try {
    // حفظ العرض التقديمي في مستند XPS
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

 يقوم مقطع التعليمات البرمجية هذا بحفظ العرض التقديمي كمستند XPS بالاسم`"XPS_Output_Without_XPSOption_out.xps"`. يمكنك تغيير اسم ملف الإخراج حسب الحاجة.

## أكمل كود المصدر للتحويل بدون خيارات XPS في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف العرض التقديمي
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// حفظ العرض التقديمي في مستند XPS
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

 في هذا البرنامج التعليمي، تعلمت كيفية تحويل عرض PowerPoint التقديمي إلى مستند XPS دون تحديد أي خيارات XPS باستخدام Aspose.Slides لـ Java. يمكنك تخصيص عملية التحويل بشكل أكبر من خلال استكشاف الخيارات التي يوفرها Aspose.Slides لـ Java. للحصول على المزيد من الميزات المتقدمة والوثائق المتعمقة، قم بزيارة[Aspose.Slides لتوثيق جافا](https://docs.aspose.com/slides/java/).

## الأسئلة الشائعة

### كيف أحدد خيارات XPS أثناء التحويل؟

 لتحديد خيارات XPS أثناء تحويل عرض تقديمي لـ PowerPoint، يمكنك استخدام`XpsOptions` فئة وتعيين خصائص مختلفة مثل ضغط الصور وتضمين الخط. إذا كانت لديك متطلبات محددة لتحويل XPS، فارجع إلى[Aspose.Slides لتوثيق جافا](https://docs.aspose.com/slides/java/) لمزيد من التفاصيل.

### هل هناك أي خيارات إضافية للحفظ بتنسيقات أخرى؟

 نعم، يوفر Aspose.Slides for Java تنسيقات إخراج متنوعة إلى جانب XPS، مثل PDF وTIFF وHTML. يمكنك تحديد تنسيق الإخراج المطلوب عن طريق تغيير`SaveFormat` المعلمة عند استدعاء`save` طريقة. راجع الوثائق للحصول على قائمة كاملة بالتنسيقات المدعومة.

### كيف يمكنني التعامل مع الاستثناءات أثناء عملية التحويل؟

 يمكنك تنفيذ معالجة الاستثناءات للتعامل بأمان مع أية أخطاء قد تحدث أثناء عملية التحويل. كما هو موضح في الكود أ`try` و`finally` تُستخدم الكتلة لضمان التخلص المناسب من الموارد حتى في حالة حدوث استثناء.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
