---
title: الخصائص الموصى بها للقراءة فقط في شرائح Java
linktitle: الخصائص الموصى بها للقراءة فقط في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تمكين الخصائص الموصى بها للقراءة فقط في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java. اتبع دليلنا خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر لتعزيز أمان العرض التقديمي.
weight: 17
url: /ar/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة لتمكين الخصائص الموصى بها للقراءة فقط في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية تمكين الخصائص الموصى بها للقراءة فقط لعروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. يمكن أن تكون الخصائص الموصى بها للقراءة فقط مفيدة عندما تريد تشجيع المستخدمين على مشاهدة عرض تقديمي دون إجراء أية تغييرات. تشير هذه الخصائص إلى أنه يجب فتح العرض التقديمي في وضع القراءة فقط. سنزودك بدليل خطوة بخطوة بالإضافة إلى كود مصدر Java لتحقيق ذلك.

## المتطلبات الأساسية

 قبل أن نبدأ، تأكد من إعداد مكتبة Aspose.Slides for Java في مشروعك. يمكنك تنزيله من[Aspose.Slides لموقع جافا](https://products.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد لـ PowerPoint

سنبدأ بإنشاء عرض تقديمي جديد لبرنامج PowerPoint باستخدام Aspose.Slides لـ Java. إذا كان لديك عرض تقديمي بالفعل، فيمكنك تخطي هذه الخطوة.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

في الكود أعلاه، قمنا بتحديد المسار لملف PowerPoint الناتج وقمنا بإنشاء كائن عرض تقديمي جديد.

## الخطوة 2: تمكين الخاصية الموصى بها للقراءة فقط

الآن، دعونا نقوم بتمكين الخاصية الموصى بها للقراءة فقط للعرض التقديمي.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 في مقتطف الكود هذا، نستخدم`getProtectionManager().setReadOnlyRecommended(true)` طريقة لتعيين الخاصية الموصى بها للقراءة فقط`true`. وهذا يضمن أنه عندما يفتح شخص ما العرض التقديمي، ستتم مطالبته بفتحه في وضع القراءة فقط.

## الخطوة 3: احفظ العرض التقديمي

وأخيرًا، نقوم بحفظ العرض التقديمي مع تمكين خاصية القراءة الموصى بها فقط.

## أكمل كود المصدر للخصائص الموصى بها للقراءة فقط في شرائح Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية تمكين خاصية القراءة فقط الموصى بها لعرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. يمكن أن تكون هذه الميزة مفيدة عندما تريد تقييد التحرير وتشجيع المشاهدين على استخدام العرض التقديمي في وضع القراءة فقط. يمكنك تعزيز الأمان بشكل أكبر عن طريق تعيين كلمة مرور للعرض التقديمي.

## الأسئلة الشائعة

### كيف أقوم بتعطيل الخاصية الموصى بها للقراءة فقط؟

لتعطيل الخاصية الموصى بها للقراءة فقط، ما عليك سوى استخدام الكود التالي:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### هل يمكنني تعيين كلمة مرور للعرض التقديمي الموصى به للقراءة فقط؟

نعم، يمكنك تعيين كلمة مرور للعرض التقديمي الموصى به للقراءة فقط باستخدام Aspose.Slides لـ Java. يمكنك استخدام ال`setPassword` طريقة تعيين كلمة المرور للعرض التقديمي. إذا تم تعيين كلمة مرور، فسيحتاج المستخدمون إلى إدخالها لفتح العرض التقديمي، حتى في وضع القراءة فقط.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 تذكر أن تحل محل`"YourPassword"` مع كلمة المرور المطلوبة.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
