---
title: تعيين الخط الاحتياطي في Java PowerPoint
linktitle: تعيين الخط الاحتياطي في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تعيين خطوط احتياطية في Java PowerPoint باستخدام Aspose.Slides لـ Java لضمان عرض نص متسق.
type: docs
weight: 16
url: /ar/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---
## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في تعقيدات إعداد الخطوط الاحتياطية في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides for Java. تعتبر احتياطيات الخطوط ضرورية لضمان عرض النص في العروض التقديمية بشكل صحيح عبر الأجهزة وأنظمة التشغيل المختلفة، حتى في حالة عدم توفر الخطوط المطلوبة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Slides لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- الفهم الأساسي للغة البرمجة جافا.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
أولاً، قم بتضمين حزم Aspose.Slides for Java الضرورية في فئة Java الخاصة بك:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## الخطوة 1: تهيئة القواعد الاحتياطية للخط
لتعيين خطوط احتياطية، تحتاج إلى تحديد القواعد التي تحدد نطاقات Unicode والخطوط الاحتياطية المقابلة. إليك كيفية تهيئة هذه القواعد:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## الخطوة 2: تطبيق قواعد الخط الاحتياطية
بعد ذلك، يمكنك تطبيق هذه القواعد على العرض التقديمي أو الشريحة التي تحتاج إلى تعيين خطوط احتياطية. فيما يلي مثال لتطبيق هذه القواعد على شريحة في عرض PowerPoint التقديمي:
```java
// بافتراض أن الشريحة هي كائن الشريحة الخاص بك
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## خاتمة
يعد تعيين خطوط احتياطية في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides لـ Java أمرًا ضروريًا لضمان عرض نص متسق عبر بيئات مختلفة. من خلال تحديد القواعد الاحتياطية كما هو موضح في هذا البرنامج التعليمي، يمكنك التعامل مع المواقف التي لا تتوفر فيها خطوط معينة، مع الحفاظ على سلامة العروض التقديمية الخاصة بك.

## الأسئلة الشائعة
### ما هي الخطوط الاحتياطية في عروض PowerPoint التقديمية؟
تضمن النسخ الاحتياطية للخطوط عرض النص بشكل صحيح عن طريق استبدال الخطوط المتوفرة بتلك التي لم يتم تثبيتها.
### كيف يمكنني تنزيل Aspose.Slides لجافا؟
 يمكنك تنزيل Aspose.Slides لـ Java من[هنا](https://releases.aspose.com/slides/java/).
### هل Aspose.Slides for Java متوافق مع جميع بيئة تطوير Java IDEs؟
نعم، Aspose.Slides for Java متوافق مع Java IDEs الشائعة مثل IntelliJ IDEA وEclipse.
### هل يمكنني الحصول على تراخيص مؤقتة لمنتجات Aspose؟
نعم، يمكن الحصول على التراخيص المؤقتة لمنتجات Aspose من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
 للحصول على الدعم المتعلق بـ Aspose.Slides for Java، قم بزيارة[منتدى Aspose](https://forum.aspose.com/c/slides/11).