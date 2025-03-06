---
title: احفظ PowerPoint بالخط العادي الافتراضي باستخدام Java
linktitle: احفظ PowerPoint بالخط العادي الافتراضي باستخدام Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية التعامل مع عروض PowerPoint التقديمية برمجياً باستخدام Aspose.Slides لـ Java. إتقان التعامل مع Java PowerPoint من خلال البرامج التعليمية خطوة بخطوة.
weight: 12
url: /ar/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
في مجال تطوير Java، يمكن أن يؤدي إنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا إلى تحسين خيارات الإنتاجية والتخصيص بشكل كبير. Aspose.Slides for Java هي مكتبة قوية تمكن المطورين من التعامل بكفاءة مع ملفات PowerPoint، وتقدم مجموعة شاملة من الميزات بدءًا من التعديلات البسيطة وحتى العروض التقديمية المعقدة.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.Slides لـ Java، تأكد من إعداد المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): يتطلب Aspose.Slides for Java إصدار JDK 1.8 أو أعلى ليعمل بشكل صحيح.
2. Aspose.Slides for Java JAR: قم بتنزيل أحدث إصدار من Aspose.Slides for Java من[هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IntelliJ IDEA أو Eclipse أو Java IDE آخر من اختيارك.
4. الفهم الأساسي لجافا: الإلمام بأساسيات لغة برمجة جافا ضروري.

## حزم الاستيراد
للبدء في استخدام Aspose.Slides لـ Java، قم باستيراد الحزم الضرورية:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
وهذا يضمن أن لديك إمكانية الوصول إلى جميع الفئات والأساليب التي يوفرها Aspose.Slides لـ Java.
## الخطوة 1: قم بإعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE الخاص بك وقم بتضمين ملف Aspose.Slides for Java JAR في مسار بناء مشروعك.
## الخطوة 2: تهيئة كائن العرض التقديمي
 إنشاء مثيل أ`Presentation` كائن عن طريق تحميل ملف PowerPoint موجود (.pptx) من الدليل المحلي الخاص بك.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// تحميل العرض التقديمي
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 يستبدل`"Your Document Directory"` و`"Your Output Directory"` مع مسارات الملفات الفعلية الخاصة بك.
## الخطوة 3: حفظ العرض التقديمي باستخدام الخطوط العادية الافتراضية
 حدد الخط العادي الافتراضي لتنسيقات الإخراج (HTML وPDF) التي تستخدمها`HtmlOptions` و`PdfOptions` على التوالى.
```java
try {
    // خيارات حفظ HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // خيارات حفظ PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 تأكد من الاستبدال`"Arial Black"` و`"Lucida Console"` مع الخطوط العادية الافتراضية المطلوبة.

## خاتمة
باتباع هذه الخطوات، تعلمت كيفية التعامل مع عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java بشكل فعال. تتيح لك هذه الإمكانية أتمتة المهام وتخصيص العروض التقديمية وتحسين تطبيقات Java الخاصة بك باستخدام وظائف معالجة PowerPoint المتقدمة.
## الأسئلة الشائعة
### هل يمكن لـ Aspose.Slides for Java العمل مع الإصدارات الأقدم من JDK؟
يتطلب Aspose.Slides لـ Java إصدار JDK 1.8 أو أعلى للتوافق.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على وثائق أكثر تفصيلاً حول Aspose.Slides لـ Java؟
 استكشاف الوثائق الشاملة[هنا](https://reference.aspose.com/slides/java/).
### هل يتوفر دعم مجتمعي لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على دعم المجتمع[هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني تجربة Aspose.Slides لـ Java مجانًا؟
 نعم، قم بتنزيل نسخة تجريبية مجانية[هنا](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
