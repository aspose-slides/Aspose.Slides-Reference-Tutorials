---
title: حفظ كنوع عرض محدد مسبقًا في شرائح Java
linktitle: حفظ كنوع عرض محدد مسبقًا في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين أنواع العرض المحددة مسبقًا في Java Slides باستخدام Aspose.Slides لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية والأسئلة الشائعة.
weight: 10
url: /ar/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# حفظ كنوع عرض محدد مسبقًا في شرائح Java


## مقدمة للحفظ كنوع عرض محدد مسبقًا في شرائح Java

في هذا الدليل التفصيلي، سنستكشف كيفية حفظ عرض تقديمي بنوع عرض محدد مسبقًا باستخدام Aspose.Slides لـ Java. سنزودك بالكود والشروحات اللازمة لإنجاز هذه المهمة بنجاح.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Aspose.Slides لمكتبة Java.
- بيئة التطوير المتكاملة (IDE) من اختيارك.

## إعداد بيئتك

للبدء، اتبع الخطوات التالية لإعداد بيئة التطوير الخاصة بك:

1. قم بإنشاء مشروع Java جديد في IDE الخاص بك.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك باعتبارها تبعية.

الآن بعد أن تم إعداد بيئتك، فلنتابع التعليمات البرمجية.

## الخطوة 1: إنشاء عرض تقديمي

لتوضيح حفظ عرض تقديمي باستخدام نوع عرض محدد مسبقًا، سنقوم أولاً بإنشاء عرض تقديمي جديد. إليك الكود لإنشاء عرض تقديمي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// فتح ملف العرض التقديمي
Presentation presentation = new Presentation();
```

 في هذا الكود نقوم بإنشاء جديد`Presentation` الكائن الذي يمثل عرض PowerPoint التقديمي الخاص بنا.

## الخطوة 2: تحديد نوع العرض

بعد ذلك، سنقوم بتعيين نوع العرض لعرضنا التقديمي. تحدد أنواع العرض كيفية عرض العرض التقديمي عند فتحه. في هذا المثال، سنقوم بتعيينه على "عرض الشريحة الرئيسية". إليك الكود:

```java
// تحديد نوع العرض
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 في الكود أعلاه نستخدم`setLastView` طريقة`ViewProperties` فئة لتعيين نوع العرض ل`SlideMasterView`. يمكنك اختيار أنواع عرض أخرى حسب الحاجة.

## الخطوة 3: حفظ العرض التقديمي

الآن بعد أن قمنا بإنشاء العرض التقديمي الخاص بنا وقمنا بتعيين نوع العرض، فقد حان الوقت لحفظ العرض التقديمي. سنقوم بحفظه بتنسيق PPTX. إليك الكود:

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 في هذا الكود نستخدم`save` طريقة`Presentation` class لحفظ العرض التقديمي باسم الملف والتنسيق المحددين.

## أكمل كود المصدر للحفظ كنوع عرض محدد مسبقًا في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// فتح ملف العرض التقديمي
Presentation presentation = new Presentation();
try
{
	// تحديد نوع العرض
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// حفظ العرض التقديمي
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية حفظ عرض تقديمي بنوع عرض محدد مسبقًا في Java باستخدام Aspose.Slides for Java. باتباع التعليمات البرمجية والخطوات المقدمة، يمكنك بسهولة تعيين نوع عرض العروض التقديمية الخاصة بك وحفظها بالتنسيق المطلوب.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع العرض إلى شيء آخر غير "عرض الشريحة الرئيسية"؟

 لتغيير نوع العرض إلى شيء آخر غير "عرض الشريحة الرئيسية"، ما عليك سوى استبداله`ViewType.SlideMasterView` مع نوع العرض المطلوب، مثل`ViewType.NormalView` أو`ViewType.SlideSorterView`، في الكود الذي قمنا بتعيين نوع العرض فيه.

### هل يمكنني تعيين خصائص العرض للشرائح الفردية في العرض التقديمي؟

نعم، يمكنك تعيين خصائص العرض للشرائح الفردية باستخدام Aspose.Slides لـ Java. يمكنك الوصول إلى خصائص كل شريحة ومعالجتها بشكل منفصل عن طريق التكرار عبر الشرائح في العرض التقديمي.

### ما التنسيقات الأخرى التي يمكنني حفظ العرض التقديمي بها؟

يدعم Aspose.Slides for Java تنسيقات الإخراج المختلفة، بما في ذلك PPTX وPDF وTIFF وHTML والمزيد. يمكنك تحديد التنسيق المطلوب عند حفظ العرض التقديمي الخاص بك باستخدام التنسيق المناسب`SaveFormat` قيمة التعداد.

### هل Aspose.Slides for Java مناسب للمعالجة المجمعة للعروض التقديمية؟

نعم، Aspose.Slides for Java مناسب تمامًا لمهام المعالجة المجمعة. يمكنك أتمتة معالجة العروض التقديمية المتعددة وتطبيق التغييرات وحفظها بشكل مجمّع باستخدام كود Java.

### أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Slides لـ Java؟

 للحصول على الوثائق والمراجع الشاملة المتعلقة بـ Aspose.Slides for Java، يرجى زيارة موقع التوثيق:[Aspose.Slides لتوثيق جافا](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
