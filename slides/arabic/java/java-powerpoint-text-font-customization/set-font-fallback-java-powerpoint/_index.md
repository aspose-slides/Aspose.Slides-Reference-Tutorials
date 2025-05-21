---
"description": "تعرف على كيفية تعيين خطوط بديلة في Java PowerPoint باستخدام Aspose.Slides for Java لضمان عرض نص متسق."
"linktitle": "تعيين خط بديل في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تعيين خط بديل في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تعيين خط بديل في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في تفاصيل ضبط خيارات الخطوط البديلة في عروض PowerPoint التقديمية بلغة Java باستخدام Aspose.Slides for Java. تُعد خيارات الخطوط البديلة ضرورية لضمان عرض النص في عروضك التقديمية بشكل صحيح على مختلف الأجهزة وأنظمة التشغيل، حتى في حالة عدم توفر الخطوط المطلوبة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت Java Development Kit (JDK) على نظامك.
- مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- فهم أساسي للغة البرمجة جافا.
- بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
أولاً، قم بتضمين حزم Aspose.Slides اللازمة لـ Java في فئة Java الخاصة بك:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## الخطوة 1: تهيئة قواعد الرجوع إلى الخطوط
لتعيين خطوط بديلة، عليك تحديد قواعد تحدد نطاقات Unicode والخطوط البديلة المقابلة. إليك كيفية تهيئة هذه القواعد:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## الخطوة 2: تطبيق قواعد الرجوع إلى الخط
بعد ذلك، طبّق هذه القواعد على العرض التقديمي أو الشريحة التي تحتاج إلى ضبط خطوط بديلة. فيما يلي مثال على تطبيق هذه القواعد على شريحة في عرض تقديمي باوربوينت:
```java
// بافتراض أن الشريحة هي كائن الشريحة الخاص بك
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## خاتمة
يُعدّ ضبط خطوط بديلة في عروض PowerPoint التقديمية بلغة جافا باستخدام Aspose.Slides for Java أمرًا أساسيًا لضمان عرض نص متسق في بيئات مختلفة. بتحديد قواعد بديلة كما هو موضح في هذا البرنامج التعليمي، يمكنك التعامل مع حالات عدم توفر خطوط معينة، مع الحفاظ على سلامة عروضك التقديمية.

## الأسئلة الشائعة
### ما هي الخطوط الاحتياطية في عروض PowerPoint؟
تضمن خيارات الخطوط البديلة عرض النص بشكل صحيح عن طريق استبدال الخطوط المتوفرة بتلك التي لم يتم تثبيتها.
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [هنا](https://releases.aspose.com/slides/java/).
### هل Aspose.Slides for Java متوافق مع جميع بيئات التطوير المتكاملة Java IDE؟
نعم، يعد Aspose.Slides for Java متوافقًا مع بيئات التطوير المتكاملة Java IDE الشهيرة مثل IntelliJ IDEA وEclipse.
### هل يمكنني الحصول على تراخيص مؤقتة لمنتجات Aspose؟
نعم، يمكن الحصول على تراخيص مؤقتة لمنتجات Aspose من [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
للحصول على الدعم المتعلق بـ Aspose.Slides لـ Java، تفضل بزيارة [منتدى Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}