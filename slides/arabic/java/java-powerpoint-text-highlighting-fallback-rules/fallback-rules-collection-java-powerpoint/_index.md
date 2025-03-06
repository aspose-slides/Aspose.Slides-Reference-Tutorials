---
title: مجموعة القواعد الاحتياطية في Java PowerPoint
linktitle: مجموعة القواعد الاحتياطية في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إدارة القواعد الاحتياطية للخطوط في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تعزيز التوافق عبر الأجهزة دون عناء.
weight: 11
url: /ar/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في هذا البرنامج التعليمي، سوف نتعمق في كيفية إدارة القواعد الاحتياطية للخط باستخدام Aspose.Slides لـ Java. تعد النسخ الاحتياطية للخطوط أمرًا بالغ الأهمية لضمان عرض العروض التقديمية بشكل صحيح عبر بيئات مختلفة، خاصة عند عدم توفر خطوط معينة. سنرشدك خلال استيراد الحزم الضرورية وإعداد البيئة وتنفيذ القواعد الاحتياطية خطوة بخطوة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
- المعرفة الأساسية ببرمجة جافا.
- JDK (Java Development Kit) مثبت على نظامك.
-  تم تنزيل وإعداد Aspose.Slides لمكتبة Java. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/java/).
- تم تثبيت IDE (بيئة التطوير المتكاملة) مثل IntelliJ IDEA أو Eclipse.
## حزم الاستيراد
ابدأ باستيراد الحزم الضرورية لمشروع Java الخاص بك:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## إعداد كائن العرض التقديمي
أولاً، قم بتهيئة كائن العرض التقديمي حيث ستحدد القواعد الاحتياطية للخط.
```java
Presentation presentation = new Presentation();
```
## إنشاء مجموعة قواعد الخط الاحتياطي
بعد ذلك، قم بإنشاء كائن FontFallBackRulesCollection لإدارة القواعد الاحتياطية للخط المخصص.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## إضافة قواعد الخط الاحتياطي
الآن، قم بإضافة قواعد احتياطية محددة للخطوط باستخدام نطاقات Unicode وأسماء الخطوط الاحتياطية.
### الخطوة 1: تحديد نطاق Unicode والخط
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
يقوم هذا السطر بتعيين قاعدة احتياطية لنطاق Unicode من 0x0B80 إلى 0x0BFF لاستخدام الخط "Vijaya" في حالة عدم توفر الخط الأساسي.
### الخطوة 2: تحديد نطاق وخط Unicode آخر
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
هنا، تحدد القاعدة أن نطاق Unicode من 0x3040 إلى 0x309F يجب أن يتراجع إلى الخطوط "MS Mincho" أو "MS Gothic".
## تطبيق قواعد الخط الاحتياطي على العرض التقديمي
قم بتطبيق مجموعة القواعد الاحتياطية للخط الذي تم إنشاؤه على FontsManager الخاص بالعرض التقديمي.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## التخلص من كائن العرض التقديمي
وأخيرًا، تأكد من الإدارة المناسبة للموارد عن طريق التخلص من كائن العرض التقديمي داخل كتلة المحاولة النهائية.
```java
try {
    // استخدم كائن العرض التقديمي حسب الحاجة
} finally {
    if (presentation != null) presentation.dispose();
}
```
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية إدارة القواعد الاحتياطية للخط باستخدام Aspose.Slides لـ Java. يضمن فهم الخطوط الاحتياطية وتنفيذها عرض الخطوط بشكل متسق وموثوق عبر الأنظمة الأساسية والبيئات المختلفة. باتباع هذه الخطوات، يمكنك تخصيص سلوك الخط الاحتياطي لتلبية متطلبات العرض التقديمي المحددة بسلاسة.

## الأسئلة الشائعة
### ما هي القواعد الاحتياطية للخط؟
تحدد القواعد الاحتياطية للخط الخطوط البديلة لاستخدامها عندما لا يكون الخط المحدد متاحًا، مما يضمن عرض نص متسق.
### كيف يمكنني تنزيل Aspose.Slides لنظام Java؟
 يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).
### هل يمكنني تجربة Aspose.Slides لـ Java قبل الشراء؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على وثائق Aspose.Slides لـ Java؟
 الوثائق التفصيلية متاحة[هنا](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على دعم Aspose.Slides لـ Java؟
للحصول على الدعم، قم بزيارة منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
