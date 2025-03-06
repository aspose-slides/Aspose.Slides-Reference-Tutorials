---
title: تحقق من حماية العرض التقديمي في شرائح Java
linktitle: تحقق من حماية العرض التقديمي في شرائح Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية التحقق من حماية العرض التقديمي في شرائح Java باستخدام Aspose.Slides لـ Java. يوفر هذا الدليل خطوة بخطوة أمثلة على التعليمات البرمجية لعمليات التحقق من الحماية أثناء الكتابة والفتح.
weight: 15
url: /ar/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## مقدمة للتحقق من حماية العرض التقديمي في شرائح جافا

في هذا البرنامج التعليمي، سنستكشف كيفية التحقق من حماية العرض التقديمي باستخدام Aspose.Slides لـ Java. سنغطي سيناريوهين: التحقق من الحماية ضد الكتابة والتحقق من الحماية المفتوحة للعرض التقديمي. سنقدم أمثلة التعليمات البرمجية خطوة بخطوة لكل سيناريو.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من إعداد مكتبة Aspose.Slides for Java في مشروع Java الخاص بك. يمكنك تنزيله من موقع Aspose وإضافته إلى تبعيات مشروعك.

### تبعية مافن

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 يستبدل`your_version_here` مع إصدار Aspose.Slides لـ Java الذي تستخدمه.

## الخطوة 1: التحقق من الحماية ضد الكتابة

 للتحقق مما إذا كان العرض التقديمي محميًا ضد الكتابة بكلمة مرور، يمكنك استخدام`IPresentationInfo` واجهه المستخدم. إليك الكود للقيام بذلك:

```java
// مسار العرض التقديمي المصدر
String pptxFile = "path_to_presentation.pptx";

// تحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 يستبدل`"path_to_presentation.pptx"` بالمسار الفعلي لملف العرض التقديمي الخاص بك و`"password_here"` مع كلمة مرور الحماية ضد الكتابة.

## الخطوة 2: التحقق من الحماية المفتوحة

 للتحقق مما إذا كان العرض التقديمي محميًا بكلمة مرور للفتح، يمكنك استخدام`IPresentationInfo` واجهه المستخدم. إليك الكود للقيام بذلك:

```java
// مسار العرض التقديمي المصدر
String pptFile = "path_to_presentation.ppt";

// تحقق من الحماية المفتوحة للعرض التقديمي عبر واجهة IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 يستبدل`"path_to_presentation.ppt"` بالمسار الفعلي لملف العرض التقديمي الخاص بك.

## كود المصدر الكامل للتحقق من حماية العرض التقديمي في شرائح Java

```java
//مسار عرض المصدر
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// تحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// تحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IProtectionManager
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// تحقق من الحماية المفتوحة للعرض التقديمي عبر واجهة IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التحقق من حماية العرض التقديمي في شرائح Java باستخدام Aspose.Slides for Java. قمنا بتغطية سيناريوهين: التحقق من الحماية ضد الكتابة والتحقق من الحماية المفتوحة. يمكنك الآن دمج عمليات التحقق هذه في تطبيقات Java الخاصة بك للتعامل مع العروض التقديمية المحمية بشكل فعال.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides for Java من موقع Aspose على الويب أو إضافته كتبعية لـ Maven في مشروعك، كما هو موضح في قسم المتطلبات الأساسية.

### هل يمكنني التحقق من الحماية ضد الكتابة والحماية المفتوحة لعرض تقديمي؟

نعم، يمكنك التحقق من الحماية ضد الكتابة والحماية المفتوحة للعرض التقديمي باستخدام أمثلة التعليمات البرمجية المتوفرة.

### ماذا علي أن أفعل إذا نسيت كلمة مرور الحماية؟

إذا نسيت كلمة مرور الحماية لأحد العروض التقديمية، فلا توجد طريقة مضمنة لاستعادتها. تأكد من الاحتفاظ بسجل لكلمات المرور الخاصة بك لتجنب مثل هذه المواقف.

### هل يتوافق Aspose.Slides for Java مع أحدث تنسيقات ملفات PowerPoint؟

نعم، يدعم Aspose.Slides for Java أحدث تنسيقات ملفات PowerPoint، بما في ذلك ملفات .pptx.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
