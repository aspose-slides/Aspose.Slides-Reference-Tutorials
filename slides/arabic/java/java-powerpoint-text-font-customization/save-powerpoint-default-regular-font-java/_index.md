---
"description": "تعلّم كيفية التعامل مع عروض PowerPoint برمجيًا باستخدام Aspose.Slides لـ Java. أتقن التعامل مع PowerPoint بلغة Java من خلال دروس تعليمية خطوة بخطوة."
"linktitle": "حفظ PowerPoint باستخدام الخط العادي الافتراضي باستخدام Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "حفظ PowerPoint باستخدام الخط العادي الافتراضي باستخدام Java"
"url": "/ar/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# حفظ PowerPoint باستخدام الخط العادي الافتراضي باستخدام Java

## مقدمة
في مجال تطوير جافا، يُمكن لإنشاء عروض PowerPoint التقديمية ومعالجتها برمجيًا أن يُحسّن الإنتاجية وخيارات التخصيص بشكل كبير. Aspose.Slides for Java هي مكتبة قوية تُمكّن المطورين من التعامل بكفاءة مع ملفات PowerPoint، مُقدمةً مجموعة شاملة من الميزات، من التعديلات البسيطة إلى العروض التقديمية المُعقدة.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.Slides لـ Java، تأكد من إعداد المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): يتطلب Aspose.Slides for Java إصدار JDK 1.8 أو أعلى ليعمل بشكل صحيح.
2. Aspose.Slides for Java JAR: قم بتنزيل أحدث إصدار من Aspose.Slides for Java من [هنا](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): استخدم IntelliJ IDEA، أو Eclipse، أو أي بيئة تطوير متكاملة Java أخرى من اختيارك.
4. الفهم الأساسي للغة جافا: من الضروري أن تكون على دراية بأساسيات لغة برمجة جافا.

## استيراد الحزم
للبدء في استخدام Aspose.Slides لـ Java، قم باستيراد الحزم الضرورية:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
يضمن هذا أن يكون لديك حق الوصول إلى جميع الفئات والطرق التي يوفرها Aspose.Slides لـ Java.
## الخطوة 1: إعداد مشروعك
أولاً، قم بإنشاء مشروع Java جديد في IDE الخاص بك وقم بتضمين ملف Aspose.Slides for Java JAR في مسار بناء المشروع.
## الخطوة 2: تهيئة كائن العرض التقديمي
إنشاء مثيل `Presentation` يمكنك إنشاء كائن عن طريق تحميل ملف PowerPoint (.pptx) الموجود من الدليل المحلي لديك.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// تحميل العرض التقديمي
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
يستبدل `"Your Document Directory"` و `"Your Output Directory"` مع مسارات الملفات الفعلية الخاصة بك.
## الخطوة 3: حفظ العرض التقديمي باستخدام الخطوط العادية الافتراضية
حدد الخط العادي الافتراضي لتنسيقات الإخراج (HTML وPDF) باستخدام `HtmlOptions` و `PdfOptions` على التوالى.
```java
try {
    // خيارات حفظ HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // خيارات حفظ ملف PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
تأكد من الاستبدال `"Arial Black"` و `"Lucida Console"` مع الخطوط العادية الافتراضية المطلوبة.

## خاتمة
باتباع هذه الخطوات، ستتعلم كيفية إدارة عروض PowerPoint التقديمية بكفاءة باستخدام Aspose.Slides for Java. تتيح لك هذه الميزة أتمتة المهام وتخصيص العروض التقديمية وتحسين تطبيقات Java لديك باستخدام وظائف متقدمة في PowerPoint.
## الأسئلة الشائعة
### هل يمكن لـ Aspose.Slides for Java العمل مع الإصدارات الأقدم من JDK؟
يتطلب Aspose.Slides for Java إصدار JDK 1.8 أو أعلى للتوافق.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على المزيد من الوثائق التفصيلية حول Aspose.Slides لـ Java؟
استكشف الوثائق الشاملة [هنا](https://reference.aspose.com/slides/java/).
### هل يتوفر دعم مجتمعي لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الحصول على دعم المجتمع [هنا](https://forum.aspose.com/c/slides/11).
### هل يمكنني تجربة Aspose.Slides لـJava مجانًا؟
نعم، قم بتنزيل النسخة التجريبية المجانية [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}