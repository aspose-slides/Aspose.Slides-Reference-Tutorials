---
title: تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java
linktitle: تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java لضمان طباعة متسقة عبر الأنظمة الأساسية والأجهزة المختلفة.
weight: 13
url: /ar/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
Aspose.Slides for Java هي أداة قوية لمطوري Java الذين يسعون إلى التعامل مع عروض PowerPoint التقديمية برمجياً. في هذا البرنامج التعليمي، سوف نتعمق في عملية تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java. من خلال تضمين الخطوط، فإنك تتأكد من أن العروض التقديمية الخاصة بك تحافظ على مظهرها المقصود عبر الأنظمة الأساسية والأجهزة المختلفة، حتى إذا لم يتم تثبيت الخطوط المطلوبة محليًا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على نظامك.
2.  Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من[صفحة التحميل](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): اختر بيئة التطوير المتكاملة المفضلة لديك لتطوير Java، مثل IntelliJ IDEA أو Eclipse.

## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة لبدء تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java.
```java
import com.aspose.slides.*;
```
## الخطوة 1: تحديد أدلة المستندات والإخراج
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 تأكد من استبدال`"Your Document Directory"` و`"Your Output Directory"` مع المسارات إلى عرض PowerPoint التقديمي الخاص بك ودليل الإخراج المطلوب، على التوالي.
## الخطوة 2: قم بتحميل العرض التقديمي
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
تقوم هذه الخطوة بتحميل عرض PowerPoint التقديمي إلى الذاكرة، مما يسمح لك بإجراء عمليات متنوعة عليه.
## الخطوة 3: استبعاد الخطوط الافتراضية
```java
String[] fontNameExcludeList = { "Arial" };
```
حدد الخطوط التي تريد استبعادها من التضمين. في هذا المثال، نستبعد Arial.
## الخطوة 4: تضمين الخطوط في HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 في هذه الخطوة، نقوم بإنشاء مثيل`EmbedAllFontsHtmlController` لتضمين كافة الخطوط باستثناء تلك المحددة في قائمة الاستبعاد. ثم نحدد`HtmlOptions`وقم بتعيين منسق HTML مخصص لتضمين الخطوط. وأخيرًا، نقوم بحفظ العرض التقديمي بتنسيق HTML مع الخطوط المضمنة.

## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية تضمين الخطوط في HTML باستخدام Aspose.Slides لـ Java. من خلال اتباع الخطوات المقدمة، يمكنك التأكد من أن عروضك التقديمية تحافظ على طباعة متسقة عبر الأنظمة الأساسية والأجهزة المختلفة، مما يعزز تجربة المشاهدة الشاملة.
## الأسئلة الشائعة
### هل يمكنني تضمين خطوط معينة بدلاً من استبعادها؟
 نعم، يمكنك تحديد الخطوط التي تريد تضمينها عن طريق تعديل ملف`fontNameExcludeList` مجموعة وفقا لذلك.
### هل يدعم Aspose.Slides for Java تضمين الخطوط بتنسيقات أخرى إلى جانب HTML؟
نعم، يدعم Aspose.Slides تضمين الخطوط في تنسيقات الإخراج المختلفة، بما في ذلك PDF والصور.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على دعم أو مساعدة إضافية فيما يتعلق بـ Aspose.Slides لـ Java؟
 يمكنك زيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على دعم المجتمع أو الاتصال بدعم Aspose للحصول على المساعدة المهنية.
### هل يمكنني شراء ترخيص مؤقت لـ Aspose.Slides لـ Java؟
نعم، يمكنك الحصول على ترخيص مؤقت من[صفحة الشراء](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
