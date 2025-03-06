---
title: التقديم باستخدام الخط الاحتياطي في Java PowerPoint
linktitle: التقديم باستخدام الخط الاحتياطي في Java PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية عرض النص باستخدام الخطوط الاحتياطية في عروض Java PowerPoint التقديمية باستخدام Aspose.Slides. اتبع هذا الدليل خطوة بخطوة للتنفيذ السلس.
weight: 13
url: /ar/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
قد يكون إنشاء عروض PowerPoint التقديمية ومعالجتها في Java أمرًا صعبًا، ولكن باستخدام Aspose.Slides، يمكنك القيام بذلك بكفاءة. إحدى الميزات المهمة هي القدرة على عرض النص باستخدام الخطوط الاحتياطية. توفر هذه المقالة دليلاً تفصيليًا خطوة بخطوة حول كيفية تطبيق الخطوط الاحتياطية في شرائح PowerPoint باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل الغوص في التنفيذ، دعونا نتأكد من أن لديك كل ما تحتاجه:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Slides for Java: يمكنك تنزيله من[صفحة تنزيل Aspose.Slides لـ Java](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse ستجعل عملية التطوير الخاصة بك أكثر سلاسة.
4. التبعيات: قم بتضمين Aspose.Slides في تبعيات مشروعك.
## حزم الاستيراد
أولاً، نحتاج إلى استيراد الحزم الضرورية في برنامج Java الخاص بنا.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
دعونا نقسم العملية إلى خطوات يمكن التحكم فيها.
## الخطوة 1: قم بإعداد مشروعك
 قبل كتابة أي كود، تأكد من إعداد مشروعك بشكل صحيح. يتضمن ذلك إضافة مكتبة Aspose.Slides إلى مشروعك. يمكنك القيام بذلك عن طريق تنزيل المكتبة من[Aspose.Slides لجافا](https://releases.aspose.com/slides/java/) وإضافته إلى مسار البناء الخاص بك.
## الخطوة 2: تهيئة القواعد الاحتياطية للخط
 تحتاج إلى إنشاء مثيل لـ`IFontFallBackRulesCollection` الصف وإضافة القواعد إليه. تحدد هذه القواعد الخطوط الاحتياطية لنطاقات Unicode محددة.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
// إنشاء مثيل جديد لمجموعة القواعد
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// إنشاء عدد من القواعد
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## الخطوة 3: تعديل القواعد الاحتياطية
في هذه الخطوة، سنقوم بتعديل القواعد الاحتياطية عن طريق إزالة الخطوط الاحتياطية الموجودة وتحديث القواعد لنطاقات Unicode محددة.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // محاولة إزالة الخط FallBack "Tahoma" من القواعد المحملة
    fallBackRule.remove("Tahoma");
    // تحديث القواعد للنطاق المحدد
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//قم بإزالة أية قواعد موجودة من القائمة
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## الخطوة 4: قم بتحميل العرض التقديمي
قم بتحميل عرض PowerPoint التقديمي الذي تريد تعديله.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## الخطوة 5: تعيين القواعد الاحتياطية للعرض التقديمي
قم بتعيين القواعد الاحتياطية المعدة لمدير خطوط العرض التقديمي.
```java
try {
    // تخصيص قائمة القواعد المعدة للاستخدام
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // عرض صورة مصغرة باستخدام مجموعة القواعد التي تمت تهيئتها وحفظها في PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## الخطوة 6: الحفظ والاختبار
وأخيرًا، احفظ عملك واختبر التنفيذ للتأكد من أن كل شيء يعمل كما هو متوقع. إذا واجهت أية مشكلات، فتحقق مرة أخرى من الإعداد وتأكد من إضافة كافة التبعيات بشكل صحيح.
## خاتمة
باتباع هذا الدليل، يمكنك عرض النص بكفاءة باستخدام الخطوط الاحتياطية في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java. تضمن هذه العملية أن العروض التقديمية الخاصة بك تحافظ على التنسيق المتسق، حتى إذا كانت الخطوط الأساسية غير متوفرة. ترميز سعيد!
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة تتيح للمطورين إنشاء عروض PowerPoint التقديمية وتعديلها وتقديمها في تطبيقات Java.
### كيف يمكنني إضافة Aspose.Slides إلى مشروعي؟
 يمكنك تحميل المكتبة من[صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/) وإضافته إلى مسار بناء مشروعك.
### ما هي الخطوط الاحتياطية؟
الخطوط الاحتياطية هي خطوط بديلة تستخدم عندما لا يكون الخط المحدد متاحًا أو لا يدعم أحرفًا معينة.
### هل يمكنني استخدام قواعد احتياطية متعددة؟
نعم، يمكنك إضافة قواعد احتياطية متعددة للتعامل مع نطاقات وخطوط Unicode المختلفة.
### أين يمكنني الحصول على الدعم لـ Aspose.Slides؟
 يمكنك الحصول على الدعم من[منتدى دعم Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
