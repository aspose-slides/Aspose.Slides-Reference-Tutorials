---
title: حفظ الخصائص في شرائح جافا
linktitle: حفظ الخصائص في شرائح جافا
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: قم بتحسين عروض PowerPoint التقديمية الخاصة بك باستخدام Aspose.Slides لـ Java. تعلم كيفية ضبط الخصائص وتعطيل التشفير وإضافة الحماية بكلمة المرور والحفظ دون عناء.
weight: 12
url: /ar/java/saving-options/save-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## مقدمة لحفظ الخصائص في شرائح جافا

في هذا البرنامج التعليمي، سنرشدك خلال عملية حفظ الخصائص في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. ستتعلم كيفية تعيين خصائص المستند، وتعطيل التشفير لخصائص المستند، وتعيين كلمة مرور لحماية العرض التقديمي الخاص بك، وحفظه في ملف. سنزودك بتعليمات خطوة بخطوة وأمثلة على التعليمات البرمجية المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج مكتبة Aspose.Slides for Java في مشروع Java الخاص بك. يمكنك تحميل المكتبة من موقع Aspose[هنا](https://downloads.aspose.com/slides/java).

## الخطوة 1: استيراد المكتبات المطلوبة

للبدء، قم باستيراد الفئات والمكتبات الضرورية:

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## الخطوة 2: إنشاء كائن العرض التقديمي

قم بإنشاء مثيل لكائن العرض التقديمي لتمثيل عرض PowerPoint التقديمي الخاص بك. يمكنك إما إنشاء عرض تقديمي جديد أو تحميل عرض موجود. في هذا المثال، سنقوم بإنشاء عرض تقديمي جديد.

```java
// المسار إلى الدليل الذي تريد حفظ العرض التقديمي فيه
String dataDir = "Your Document Directory";

// إنشاء مثيل لكائن العرض التقديمي
Presentation presentation = new Presentation();
```

## الخطوة 3: تعيين خصائص المستند

يمكنك تعيين خصائص مختلفة للمستند مثل العنوان والمؤلف والكلمات الأساسية والمزيد. هنا، سنقوم بتعيين بعض الخصائص المشتركة:

```java
// قم بتعيين عنوان العرض التقديمي
presentation.getDocumentProperties().setTitle("My Presentation");

//قم بتعيين مؤلف العرض التقديمي
presentation.getDocumentProperties().setAuthor("John Doe");

// تعيين الكلمات الرئيسية للعرض التقديمي
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## الخطوة 4: تعطيل التشفير لخصائص المستند

افتراضيًا، يقوم Aspose.Slides بتشفير خصائص المستند. إذا كنت تريد تعطيل التشفير لخصائص المستند، استخدم الكود التالي:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## الخطوة 5: قم بتعيين كلمة مرور لحماية العرض التقديمي

 يمكنك حماية العرض التقديمي الخاص بك بكلمة مرور لتقييد الوصول. استخدم ال`encrypt` طريقة تعيين كلمة المرور:

```java
// قم بتعيين كلمة مرور لحماية العرض التقديمي
presentation.getProtectionManager().encrypt("your_password");
```

 يستبدل`"your_password"` مع كلمة المرور المطلوبة.

## الخطوة 6: احفظ العرض التقديمي

وأخيرًا، احفظ العرض التقديمي في ملف. في هذا المثال، سنقوم بحفظه كملف PPTX:

```java
// احفظ العرض التقديمي في ملف
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

 يستبدل`"Password_Protected_Presentation_out.pptx"` مع اسم الملف المطلوب والمسار.

## أكمل كود المصدر لحفظ الخصائص في شرائح Java

```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل لكائن العرض التقديمي الذي يمثل ملف PPT
Presentation presentation = new Presentation();
try
{
	//....قم ببعض الأعمال هنا .....
	// ضبط الوصول إلى خصائص المستند في الوضع المحمي بكلمة مرور
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// ضبط كلمة المرور
	presentation.getProtectionManager().encrypt("pass");
	// احفظ العرض التقديمي الخاص بك في ملف
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمت كيفية حفظ خصائص المستند في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides لـ Java. يمكنك تعيين خصائص مختلفة، وتعطيل التشفير لخصائص المستند، وتعيين كلمة مرور للحماية، وحفظ العرض التقديمي بالتنسيق المطلوب.

## الأسئلة الشائعة

### كيف يمكنني تعيين خصائص المستند في Aspose.Slides لـ Java؟

 لتعيين خصائص المستند في Aspose.Slides لـ Java، يمكنك استخدام`DocumentProperties` فصل. فيما يلي مثال لكيفية تعيين خصائص مثل العنوان والمؤلف والكلمات الرئيسية:

```java
// قم بتعيين عنوان العرض التقديمي
presentation.getDocumentProperties().setTitle("My Presentation");

//قم بتعيين مؤلف العرض التقديمي
presentation.getDocumentProperties().setAuthor("John Doe");

// تعيين الكلمات الرئيسية للعرض التقديمي
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### ما هو الغرض من تعطيل التشفير لخصائص الوثيقة؟

يتيح لك تعطيل التشفير لخصائص المستند إمكانية تخزين بيانات تعريف المستند بدون تشفير. يمكن أن يكون هذا مفيدًا عندما تريد أن تكون خصائص المستند (مثل العنوان والمؤلف وما إلى ذلك) مرئية ويمكن الوصول إليها دون إدخال كلمة مرور.

يمكنك تعطيل التشفير باستخدام الكود التالي:

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### كيف يمكنني حماية عرض PowerPoint التقديمي الخاص بي بكلمة مرور باستخدام Aspose.Slides لـ Java؟

لحماية عرض PowerPoint التقديمي الخاص بك بكلمة مرور، يمكنك استخدام`encrypt` الطريقة المقدمة من`ProtectionManager` فصل. إليك كيفية تعيين كلمة المرور:

```java
// قم بتعيين كلمة مرور لحماية العرض التقديمي
presentation.getProtectionManager().encrypt("your_password");
```

 يستبدل`"your_password"` مع كلمة المرور المطلوبة.

### هل يمكنني حفظ العرض التقديمي بتنسيق مختلف غير تنسيق PPTX؟

 نعم، يمكنك حفظ العرض التقديمي بتنسيقات مختلفة يدعمها Aspose.Slides لـ Java، مثل PPT وPDF والمزيد. للحفظ بتنسيق مختلف، قم بتغيير`SaveFormat` المعلمة في`presentation.save` طريقة. على سبيل المثال، للحفظ بصيغة PDF:

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### هل من الضروري التخلص من كائن العرض التقديمي بعد الحفظ؟

 من الممارسات الجيدة التخلص من كائن العرض التقديمي لتحرير موارد النظام. يمكنك استخدام أ`finally` الكتلة لضمان التخلص السليم، كما هو موضح في مثال الكود:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

يساعد هذا على منع تسرب الذاكرة في التطبيق الخاص بك.

### كيف يمكنني معرفة المزيد عن Aspose.Slides لـ Java وميزاته؟

 يمكنك استكشاف وثائق Aspose.Slides for Java على[هنا](https://docs.aspose.com/slides/java/) للحصول على معلومات تفصيلية ودروس تعليمية وأمثلة حول استخدام المكتبة.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
