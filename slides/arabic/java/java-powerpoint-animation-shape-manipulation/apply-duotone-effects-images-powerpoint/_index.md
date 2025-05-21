---
"description": "تعرّف على كيفية تطبيق تأثيرات Duotone على الصور في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا المفصّل. حسّن عروضك التقديمية."
"linktitle": "تطبيق تأثيرات Duotone على الصور في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "تطبيق تأثيرات Duotone على الصور في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/apply-duotone-effects-images-powerpoint/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تطبيق تأثيرات Duotone على الصور في PowerPoint

## مقدمة
إضافة تأثيرات بصرية إلى عروض PowerPoint التقديمية تُعزز جاذبيتها وفعاليتها بشكل ملحوظ. ومن هذه التأثيرات الجذابة تأثير Duotone، الذي يُضيف لونين متباينين إلى الصورة، مما يمنحها مظهرًا عصريًا واحترافيًا. في هذا الدليل الشامل، سنشرح لك عملية تطبيق تأثيرات Duotone على الصور في PowerPoint باستخدام Aspose.Slides لـ Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1. مجموعة تطوير جافا (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من [موقع Oracle JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides لمكتبة Java: يمكنك تنزيل المكتبة من [صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لكتابة وتنفيذ كود Java الخاص بك.
4. ملف الصورة: ملف صورة (على سبيل المثال، `aspose-logo.jpg`) لتطبيق تأثير Duotone.
## استيراد الحزم
أولاً، ستحتاج إلى استيراد الحزم اللازمة لبرنامج جافا. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء كائن عرض تقديمي جديد. سيكون هذا هو القماش الذي ستُضيف إليه صورتك وتُطبّق عليه تأثير التدرج اللوني.
```java
Presentation presentation = new Presentation();
```
## الخطوة 2: قراءة ملف الصورة
بعد ذلك، اقرأ ملف الصورة من مجلدك. ستُضاف هذه الصورة إلى العرض التقديمي، وسيُطبّق عليها تأثير Duotone.
```java
try {
    byte[] imageBytes = Files.readAllBytes(Paths.get("Your Document Directory/aspose-logo.jpg"));
```
## الخطوة 3: إضافة الصورة إلى العرض التقديمي
أضف الصورة إلى مجموعة صور العرض التقديمي. هذه الخطوة تجعل الصورة متاحة للاستخدام داخل العرض التقديمي.
```java
    IPPImage backgroundImage = presentation.getImages().addImage(imageBytes);
```
## الخطوة 4: تعيين الصورة كخلفية للشريحة
الآن، عيّن الصورة كخلفية للشريحة الأولى. يتضمن ذلك تحديد نوع الخلفية وتنسيق التعبئة.
```java
    presentation.getSlides().get_Item(0).getBackground().setType(BackgroundType.OwnBackground);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().setFillType(FillType.Picture);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().setImage(backgroundImage);
```
## الخطوة 5: إضافة تأثير Duotone
أضف تأثير Duotone إلى صورة الخلفية. تتضمن هذه الخطوة إنشاء كائن Duotone وضبط خصائصه.
```java
    IDuotone duotone = presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().getImageTransform().addDuotoneEffect();
```
## الخطوة 6: تعيين خصائص Duotone
اضبط تأثير التدرج اللوني بضبط الألوان. هنا، نستخدم ألوان المخطط لتأثير التدرج اللوني.
```java
    duotone.getColor1().setColorType(ColorType.Scheme);
    duotone.getColor1().setSchemeColor(SchemeColor.Accent1);
    duotone.getColor2().setColorType(ColorType.Scheme);
    duotone.getColor2().setSchemeColor(SchemeColor.Dark2);
```
## الخطوة 7: استرداد وعرض قيم Duotone الفعالة
للتحقق من التأثير، قم باسترداد القيم الفعالة لتأثير Duotone وطباعتها في وحدة التحكم.
```java
    IDuotoneEffectiveData duotoneEffective = duotone.getEffective();
    System.out.println("Duotone effective color1: " + duotoneEffective.getColor1());
    System.out.println("Duotone effective color2: " + duotoneEffective.getColor2());
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## خاتمة
تطبيق تأثير Duotone على الصور في PowerPoint يُضفي على عروضك التقديمية مظهرًا أنيقًا واحترافيًا. مع Aspose.Slides لجافا، هذه العملية سهلة وقابلة للتخصيص بدرجة كبيرة. اتبع الخطوات الموضحة في هذا البرنامج التعليمي لإضافة تأثير Duotone إلى صورك وجعل عروضك التقديمية مميزة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint وتعديلها والتلاعب بها برمجيًا.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
يمكنك تنزيل Aspose.Slides لـ Java من [صفحة التحميل](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت الواردة في الوثائق.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي IDE؟
نعم، Aspose.Slides for Java متوافق مع جميع بيئات التطوير المتكاملة الرئيسية، بما في ذلك IntelliJ IDEA، وEclipse، وNetBeans.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لنظام Java؟
نعم، يمكنك الحصول على نسخة تجريبية مجانية من [صفحة التجربة المجانية لـ Aspose.Slides](https://releases.aspose.com/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟
يمكنك العثور على وثائق وأمثلة شاملة على [صفحة توثيق Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}