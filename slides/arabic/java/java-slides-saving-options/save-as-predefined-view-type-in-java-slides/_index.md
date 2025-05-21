---
"description": "تعرّف على كيفية تعيين أنواع العرض المُعرّفة مسبقًا في شرائح جافا باستخدام Aspose.Slides لجافا. دليل خطوة بخطوة مع أمثلة برمجية وأسئلة شائعة."
"linktitle": "حفظ كنوع عرض محدد مسبقًا في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "حفظ كنوع عرض محدد مسبقًا في شرائح Java"
"url": "/ar/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# حفظ كنوع عرض محدد مسبقًا في شرائح Java


## مقدمة لحفظ نوع العرض المحدد مسبقًا في شرائح Java

في هذا الدليل التفصيلي، سنستكشف كيفية حفظ عرض تقديمي بنوع عرض مُحدد مسبقًا باستخدام Aspose.Slides لجافا. سنزودك بالرمز والشروحات اللازمة لإنجاز هذه المهمة بنجاح.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت Aspose.Slides لمكتبة Java.
- بيئة التطوير المتكاملة (IDE) حسب اختيارك.

## إعداد بيئتك

للبدء، اتبع الخطوات التالية لإعداد بيئة التطوير الخاصة بك:

1. قم بإنشاء مشروع Java جديد في IDE الخاص بك.
2. أضف مكتبة Aspose.Slides for Java إلى مشروعك كاعتمادية.

الآن بعد أن قمت بإعداد بيئتك، دعنا ننتقل إلى الكود.

## الخطوة 1: إنشاء عرض تقديمي

لتوضيح كيفية حفظ عرض تقديمي بنوع عرض مُحدد مسبقًا، سنُنشئ أولًا عرضًا تقديميًا جديدًا. إليك الكود اللازم لإنشاء العرض التقديمي:

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// فتح ملف العرض التقديمي
Presentation presentation = new Presentation();
```

في هذا الكود نقوم بإنشاء كود جديد `Presentation` الكائن الذي يمثل عرض PowerPoint الخاص بنا.

## الخطوة 2: ضبط نوع العرض

بعد ذلك، سنحدد نوع العرض لعرضنا التقديمي. تُحدد أنواع العرض كيفية عرض العرض التقديمي عند فتحه. في هذا المثال، سنضبطه على "عرض الشريحة الرئيسية". إليك الكود:

```java
// ضبط نوع العرض
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

في الكود أعلاه، نستخدم `setLastView` طريقة `ViewProperties` الفئة لتعيين نوع العرض إلى `SlideMasterView`يمكنك اختيار أنواع أخرى من العرض حسب الحاجة.

## الخطوة 3: حفظ العرض التقديمي

بعد أن أنشأنا عرضنا التقديمي وحددنا نوع العرض، حان وقت حفظه. سنحفظه بصيغة PPTX. إليك الكود:

```java
// حفظ العرض التقديمي
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

في هذا الكود نستخدم `save` طريقة `Presentation` فئة لحفظ العرض التقديمي باسم الملف والتنسيق المحددين.

## كود المصدر الكامل لحفظ نوع العرض المحدد مسبقًا في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// فتح ملف العرض التقديمي
Presentation presentation = new Presentation();
try
{
	// ضبط نوع العرض
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

في هذا البرنامج التعليمي، تعلمنا كيفية حفظ عرض تقديمي بنوع عرض مُحدد مسبقًا في جافا باستخدام Aspose.Slides for Java. باتباع التعليمات البرمجية والخطوات المُقدمة، يمكنك بسهولة تحديد نوع عرض عروضك التقديمية وحفظها بالتنسيق المطلوب.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع العرض إلى شيء آخر غير "عرض الشريحة الرئيسية"؟

لتغيير نوع العرض إلى شيء آخر غير "عرض الشريحة الرئيسية"، ما عليك سوى استبدال `ViewType.SlideMasterView` مع نوع العرض المطلوب، مثل `ViewType.NأوmalView` or `ViewType.SlideSorterView`، في الكود حيث قمنا بتعيين نوع العرض.

### هل يمكنني تعيين خصائص العرض للشرائح الفردية في العرض التقديمي؟

نعم، يمكنك ضبط خصائص العرض لكل شريحة على حدة باستخدام Aspose.Slides لجافا. يمكنك الوصول إلى خصائص كل شريحة على حدة والتحكم بها من خلال التكرار بين الشرائح في العرض التقديمي.

### ما هي التنسيقات الأخرى التي يمكنني حفظ العرض التقديمي بها؟

يدعم Aspose.Slides لجافا تنسيقات إخراج متنوعة، بما في ذلك PPTX وPDF وTIFF وHTML وغيرها. يمكنك تحديد التنسيق المطلوب عند حفظ عرضك التقديمي باستخدام الخيار المناسب. `SaveFormat` قيمة التعداد.

### هل برنامج Aspose.Slides for Java مناسب لمعالجة العروض التقديمية بشكل دفعات؟

نعم، يُعدّ Aspose.Slides for Java مثاليًا لمهام المعالجة الدفعية. يمكنك أتمتة معالجة عروض تقديمية متعددة، وتطبيق التغييرات، وحفظها دفعةً واحدة باستخدام شفرة Java.

### أين يمكنني العثور على مزيد من المعلومات والوثائق الخاصة بـ Aspose.Slides for Java؟

للحصول على وثائق ومراجع شاملة تتعلق بـ Aspose.Slides for Java، يرجى زيارة موقع الويب الخاص بالوثائق: [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}