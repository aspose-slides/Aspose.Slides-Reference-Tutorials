---
"description": "تعرّف على كيفية تعيين الخطوط الافتراضية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. حسّن مظهرك بسلاسة ووضوح."
"linktitle": "الخطوط الافتراضية في PowerPoint مع Aspose.Slides لـ Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "الخطوط الافتراضية في PowerPoint مع Aspose.Slides لـ Java"
"url": "/ar/java/java-powerpoint-font-management/default-fonts-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# الخطوط الافتراضية في PowerPoint مع Aspose.Slides لـ Java

## مقدمة
يُعد إنشاء عروض PowerPoint التقديمية باستخدام خطوط مخصصة متطلبًا شائعًا في العديد من المشاريع. يوفر Aspose.Slides for Java حلاً سلسًا لإدارة الخطوط الافتراضية، مما يضمن الاتساق في مختلف البيئات. في هذا البرنامج التعليمي، سنرشدك خلال عملية تعيين الخطوط الافتراضية في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [صفحة التحميل](https://releases.aspose.com/slides/java/).
3. المعرفة الأساسية بلغة جافا: التعرف على أساسيات لغة برمجة جافا.

## استيراد الحزم
ابدأ باستيراد الحزم الضرورية في مشروع Java الخاص بك:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: تعيين الخطوط الافتراضية
قم بتحديد المسار إلى دليل المستند الخاص بك وإنشاء خيارات التحميل لتحديد الخطوط العادية والآسيوية الافتراضية:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## الخطوة 2: تحميل العرض التقديمي
قم بتحميل عرض PowerPoint باستخدام خيارات التحميل المحددة:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## الخطوة 3: إنشاء المخرجات
إنشاء مخرجات مختلفة مثل الصور المصغرة للشرائح وملفات PDF وXPS:
```java
try {
    // إنشاء صورة مصغرة للشريحة
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // إنشاء ملف PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // إنشاء XPS
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## خاتمة
يُعدّ تعيين الخطوط الافتراضية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java أمرًا سهلًا وفعّالاً. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك ضمان تناسق أنماط الخطوط عبر مختلف المنصات والبيئات، مما يُحسّن المظهر المرئي لعروضك التقديمية.
## الأسئلة الشائعة
### هل يمكنني استخدام الخطوط المخصصة مع Aspose.Slides لـ Java؟
نعم، يمكنك تحديد الخطوط المخصصة في العروض التقديمية الخاصة بك باستخدام Aspose.Slides لـ Java.
### هل Aspose.Slides for Java متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides for Java مجموعة واسعة من إصدارات PowerPoint، مما يضمن التوافق عبر بيئات مختلفة.
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides لـ Java؟
يمكنك الحصول على الدعم لـ Aspose.Slides لـ Java من خلال [منتديات Aspose](https://forum.aspose.com/c/slides/11).
### هل يمكنني تجربة Aspose.Slides لـJava قبل الشراء؟
نعم، يمكنك استكشاف Aspose.Slides لـ Java من خلال نسخة تجريبية مجانية متاحة على [releases.aspose.com](https://releases.aspose.com/).
### أين يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ Java من [صفحة الشراء](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}