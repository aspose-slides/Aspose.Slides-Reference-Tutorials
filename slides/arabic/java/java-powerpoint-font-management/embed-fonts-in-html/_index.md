---
"description": "تعرف على كيفية تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java لضمان تناسق الطباعة عبر الأنظمة الأساسية والأجهزة المختلفة."
"linktitle": "تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java"
"url": "/ar/java/java-powerpoint-font-management/embed-fonts-in-html/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java

## مقدمة
Aspose.Slides for Java أداة فعّالة لمطوري Java الراغبين في التعامل مع عروض PowerPoint التقديمية برمجيًا. في هذا البرنامج التعليمي، سنتعمق في عملية تضمين الخطوط في HTML باستخدام Aspose.Slides for Java. بتضمين الخطوط، تضمن أن تحافظ عروضك التقديمية على مظهرها المطلوب عبر مختلف المنصات والأجهزة، حتى لو لم تكن الخطوط المطلوبة مُثبّتة محليًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المفضلة لديك لتطوير Java، مثل IntelliJ IDEA أو Eclipse.

## استيراد الحزم
أولاً، يتعين عليك استيراد الحزم اللازمة لبدء تضمين الخطوط في HTML باستخدام Aspose.Slides for Java.
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحديد أدلة المستندات والإخراج
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
تأكد من استبدال `"Your Document Directory"` و `"Your Output Directory"` مع المسارات إلى عرض PowerPoint المدخل ودليل الإخراج المطلوب، على التوالي.
## الخطوة 2: تحميل العرض التقديمي
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
تؤدي هذه الخطوة إلى تحميل عرض PowerPoint في الذاكرة، مما يسمح لك بإجراء عمليات مختلفة عليه.
## الخطوة 3: استبعاد الخطوط الافتراضية
```java
String[] fontNameExcludeList = { "Arial" };
```
حدد الخطوط التي تريد استبعادها من التضمين. في هذا المثال، استثنينا Arial.
## الخطوة 4: تضمين الخطوط في HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
في هذه الخطوة، نقوم بإنشاء مثيل لـ `EmbedAllFontsHtmlController` لتضمين جميع الخطوط باستثناء تلك المحددة في قائمة الاستبعاد. ثم نُعرّف `HtmlOptions` وضبط مُنسّق HTML مُخصّص لتضمين الخطوط. وأخيرًا، حفظنا العرض التقديمي بصيغة HTML مع تضمين الخطوط.

## خاتمة
في هذا البرنامج التعليمي، استكشفنا كيفية تضمين الخطوط في HTML باستخدام Aspose.Slides لجافا. باتباع الخطوات المذكورة، يمكنك ضمان تناسق خطوط عروضك التقديمية على مختلف المنصات والأجهزة، مما يُحسّن تجربة المشاهدة بشكل عام.
## الأسئلة الشائعة
### هل يمكنني تضمين خطوط محددة بدلاً من استبعادها؟
نعم، يمكنك تحديد الخطوط التي تريد تضمينها عن طريق تعديل `fontNameExcludeList` المصفوفة وفقا لذلك.
### هل يدعم Aspose.Slides for Java تضمين الخطوط بتنسيقات أخرى إلى جانب HTML؟
نعم، يدعم Aspose.Slides تضمين الخطوط في تنسيقات إخراج مختلفة، بما في ذلك PDF والصور.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم أو المساعدة الإضافية مع Aspose.Slides لـ Java؟
يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على دعم المجتمع أو الاتصال بدعم Aspose للحصول على مساعدة متخصصة.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
نعم يمكنك الحصول على ترخيص مؤقت من [صفحة الشراء](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}