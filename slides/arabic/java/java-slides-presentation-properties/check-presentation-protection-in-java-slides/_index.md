---
"description": "تعرّف على كيفية التحقق من حماية العروض التقديمية في شرائح جافا باستخدام Aspose.Slides لجافا. يقدم هذا الدليل التفصيلي أمثلة برمجية للتحقق من حماية الكتابة والفتح."
"linktitle": "التحقق من حماية العرض التقديمي في Java Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "التحقق من حماية العرض التقديمي في Java Slides"
"url": "/ar/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# التحقق من حماية العرض التقديمي في Java Slides


## مقدمة للتحقق من حماية العرض التقديمي في Java Slides

في هذا البرنامج التعليمي، سنستكشف كيفية التحقق من حماية العرض التقديمي باستخدام Aspose.Slides لجافا. سنغطي حالتين: التحقق من حماية الكتابة والتحقق من حماية الفتح للعرض التقديمي. سنقدم أمثلة برمجية خطوة بخطوة لكل حالة.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides لجافا في مشروع جافا. يمكنك تنزيلها من موقع Aspose الإلكتروني وإضافتها إلى تبعيات مشروعك.

### تبعية Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

يستبدل `your_version_here` مع إصدار Aspose.Slides لـ Java الذي تستخدمه.

## الخطوة 1: التحقق من الحماية ضد الكتابة

للتحقق مما إذا كان العرض التقديمي محميًا ضد الكتابة بكلمة مرور، يمكنك استخدام `IPresentationInfo` الواجهة. إليك الكود للقيام بذلك:

```java
// المسار لعرض المصدر
String pptxFile = "path_to_presentation.pptx";

// التحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

يستبدل `"path_to_presentation.pptx"` مع المسار الفعلي لملف العرض التقديمي الخاص بك و `"password_here"` مع كلمة مرور الحماية ضد الكتابة.

## الخطوة 2: التحقق من الحماية المفتوحة

للتحقق مما إذا كان العرض التقديمي محميًا بكلمة مرور لفتحه، يمكنك استخدام `IPresentationInfo` الواجهة. إليك الكود للقيام بذلك:

```java
// المسار لعرض المصدر
String pptFile = "path_to_presentation.ppt";

// التحقق من حماية العرض التقديمي المفتوح عبر واجهة IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

يستبدل `"path_to_presentation.ppt"` مع المسار الفعلي لملف العرض التقديمي الخاص بك.

## كود المصدر الكامل للتحقق من حماية العرض التقديمي في شرائح Java

```java
//مسار لعرض المصدر
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// التحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// التحقق من كلمة مرور الحماية ضد الكتابة عبر واجهة IProtectionManager
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
// التحقق من حماية العرض التقديمي المفتوح عبر واجهة IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية التحقق من حماية العروض التقديمية في شرائح جافا باستخدام Aspose.Slides لجافا. غطينا حالتين: التحقق من حماية الكتابة والتحقق من حماية الفتح. يمكنك الآن دمج هذه الفحوصات في تطبيقات جافا لديك للتعامل مع العروض التقديمية المحمية بفعالية.

## الأسئلة الشائعة

### كيف يمكنني الحصول على Aspose.Slides لـ Java؟

يمكنك تنزيل Aspose.Slides لـ Java من موقع Aspose الإلكتروني أو إضافته كتبعية Maven في مشروعك، كما هو موضح في قسم المتطلبات الأساسية.

### هل يمكنني التحقق من الحماية ضد الكتابة والحماية المفتوحة للعرض التقديمي؟

نعم، يمكنك التحقق من حماية الكتابة وحماية الفتح لعرض تقديمي باستخدام أمثلة التعليمات البرمجية المقدمة.

### ماذا يجب أن أفعل إذا نسيت كلمة المرور للحماية؟

إذا نسيت كلمة مرور الحماية لعرض تقديمي، فلا توجد طريقة مُضمنة لاستعادتها. احرص على تسجيل كلمات مرورك لتجنب مثل هذه المواقف.

### هل Aspose.Slides for Java متوافق مع أحدث تنسيقات ملفات PowerPoint؟

نعم، يدعم Aspose.Slides for Java أحدث تنسيقات ملفات PowerPoint، بما في ذلك ملفات .pptx.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}