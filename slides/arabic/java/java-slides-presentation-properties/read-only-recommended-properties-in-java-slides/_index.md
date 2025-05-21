---
"description": "تعرّف على كيفية تفعيل خصائص \"موصى بها للقراءة فقط\" في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides لـ Java. اتبع دليلنا المفصل مع أمثلة على الكود المصدري لتعزيز أمان العرض التقديمي."
"linktitle": "خصائص موصى بها للقراءة فقط في شرائح Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "خصائص موصى بها للقراءة فقط في شرائح Java"
"url": "/ar/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# خصائص موصى بها للقراءة فقط في شرائح Java


## مقدمة حول تمكين خصائص القراءة فقط الموصى بها في شرائح Java

في هذا البرنامج التعليمي، سنستكشف كيفية تفعيل خصائص "موصى بها للقراءة فقط" لعروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. تُعدّ خصائص "موصى بها للقراءة فقط" مفيدة عندما ترغب في تشجيع المستخدمين على مشاهدة عرض تقديمي دون إجراء أي تغييرات. تقترح هذه الخصائص فتح العرض التقديمي في وضع القراءة فقط. سنقدم لك دليلًا خطوة بخطوة مع شفرة مصدر جافا لتحقيق ذلك.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا في مشروعك. يمكنك تنزيلها من [موقع Aspose.Slides لـ Java](https://products.aspose.com/slides/java/).

## الخطوة 1: إنشاء عرض تقديمي جديد في PowerPoint

سنبدأ بإنشاء عرض تقديمي جديد على PowerPoint باستخدام Aspose.Slides لجافا. إذا كان لديك عرض تقديمي بالفعل، يمكنك تخطي هذه الخطوة.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

في الكود أعلاه، قمنا بتحديد المسار لملف PowerPoint الناتج وإنشاء كائن عرض تقديمي جديد.

## الخطوة 2: تمكين خاصية القراءة فقط الموصى بها

الآن، دعنا نقوم بتمكين خاصية "الموصى بها للقراءة فقط" للعرض التقديمي.

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

في مقتطف الكود هذا، نستخدم `getProtectionManager().setReadOnlyRecommended(true)` طريقة لتعيين خاصية "الموصى بها للقراءة فقط" إلى `true`يضمن هذا أنه عندما يفتح شخص ما العرض التقديمي، سيُطلب منه فتحه في وضع القراءة فقط.

## الخطوة 3: حفظ العرض التقديمي

وأخيرًا، نقوم بحفظ العرض التقديمي مع تمكين خاصية "الموصى بها للقراءة فقط".

## كود المصدر الكامل للخصائص الموصى بها للقراءة فقط في شرائح Java

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

في هذا البرنامج التعليمي، تعلمت كيفية تفعيل خاصية "موصى به للقراءة فقط" لعرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. يمكن أن تكون هذه الميزة مفيدة عند الرغبة في تقييد التحرير وتشجيع المشاهدين على استخدام العرض التقديمي في وضع القراءة فقط. يمكنك تعزيز الأمان بشكل أكبر بتعيين كلمة مرور للعرض التقديمي.

## الأسئلة الشائعة

### كيف يمكنني تعطيل خاصية "الموصى بها للقراءة فقط"؟

لتعطيل خاصية "الموصى بها للقراءة فقط"، استخدم الكود التالي ببساطة:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### هل يمكنني تعيين كلمة مرور لعرض تقديمي موصى به للقراءة فقط؟

نعم، يمكنك تعيين كلمة مرور لعرض تقديمي مُوصى به للقراءة فقط باستخدام Aspose.Slides لجافا. يمكنك استخدام `setPassword` طريقة تعيين كلمة مرور للعرض التقديمي. في حال تعيين كلمة مرور، سيحتاج المستخدمون إلى إدخالها لفتح العرض التقديمي، حتى في وضع القراءة فقط.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

تذكر أن تستبدل `"YourPassword"` مع كلمة المرور المطلوبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}