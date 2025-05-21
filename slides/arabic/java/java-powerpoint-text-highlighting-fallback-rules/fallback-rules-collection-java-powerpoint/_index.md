---
"description": "تعرّف على كيفية إدارة قواعد الخطوط البديلة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. حسّن التوافق بين الأجهزة بسهولة."
"linktitle": "مجموعة قواعد احتياطية في Java PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "مجموعة قواعد احتياطية في Java PowerPoint"
"url": "/ar/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# مجموعة قواعد احتياطية في Java PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنتعمق في كيفية إدارة قواعد الخطوط البديلة باستخدام Aspose.Slides لجافا. تُعد قواعد الخطوط البديلة أساسية لضمان عرض عروضك التقديمية بشكل صحيح في بيئات مختلفة، خاصةً عند عدم توفر خطوط معينة. سنرشدك خطوة بخطوة خلال استيراد الحزم اللازمة، وإعداد البيئة، وتطبيق قواعد الخطوط البديلة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- تم تثبيت JDK (Java Development Kit) على نظامك.
- تم تنزيل وإعداد مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/java/).
- تم تثبيت IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
## استيراد الحزم
ابدأ باستيراد الحزم اللازمة لمشروع Java الخاص بك:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## إعداد كائن العرض التقديمي
أولاً، قم بتهيئة كائن العرض التقديمي الذي ستحدد فيه قواعد الرجوع إلى الخط الخاص بك.
```java
Presentation presentation = new Presentation();
```
## إنشاء مجموعة قواعد احتياطية للخطوط
بعد ذلك، قم بإنشاء كائن FontFallBackRulesCollection لإدارة قواعد الرجوع إلى الخطوط المخصصة لديك.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## إضافة قواعد الرجوع إلى الخطوط
الآن، قم بإضافة قواعد خط بديلة محددة باستخدام نطاقات Unicode وأسماء الخطوط البديلة.
### الخطوة 1: تحديد نطاق Unicode والخط
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
يحدد هذا السطر قاعدة احتياطية لنطاق Unicode من 0x0B80 إلى 0x0BFF لاستخدام الخط "Vijaya" إذا كان الخط الأساسي غير متوفر.
### الخطوة 2: تعريف نطاق Unicode وخط آخر
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
هنا، تحدد القاعدة أن نطاق Unicode من 0x3040 إلى 0x309F يجب أن يعود إلى الخطوط "MS Mincho" أو "MS Gothic".
## تطبيق قواعد الرجوع إلى الخطوط على العرض التقديمي
قم بتطبيق مجموعة قواعد الخطوط الاحتياطية التي تم إنشاؤها على FontsManager الخاص بالعرض التقديمي.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## التخلص من كائن العرض التقديمي
أخيرًا، تأكد من إدارة الموارد بشكل صحيح عن طريق التخلص من كائن العرض التقديمي داخل كتلة try-finally.
```java
try {
    // استخدم كائن العرض حسب الحاجة
} finally {
    if (presentation != null) presentation.dispose();
}
```
## خاتمة
في هذا البرنامج التعليمي، استكشفنا كيفية إدارة قواعد الخطوط البديلة باستخدام Aspose.Slides في Java. يضمن فهم وتطبيق قواعد الخطوط البديلة عرضًا متسقًا وموثوقًا للخطوط عبر منصات وبيئات مختلفة. باتباع هذه الخطوات، يمكنك تخصيص سلوك الخطوط البديلة لتلبية متطلبات العرض التقديمي المحددة بسلاسة.

## الأسئلة الشائعة
### ما هي قواعد الرجوع إلى الخط؟
تعرف قواعد الرجوع إلى الخطوط الخطوط البديلة التي يجب استخدامها عندما لا يتوفر الخط المحدد، مما يضمن عرض النص بشكل متسق.
### كيف يمكنني تنزيل Aspose.Slides لـ Java؟
يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـJava قبل الشراء؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
الوثائق التفصيلية متاحة [هنا](https://reference.aspose.com/slides/java/).
### كيف أحصل على الدعم لـ Aspose.Slides لـ Java؟
للحصول على الدعم، قم بزيارة منتدى Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}