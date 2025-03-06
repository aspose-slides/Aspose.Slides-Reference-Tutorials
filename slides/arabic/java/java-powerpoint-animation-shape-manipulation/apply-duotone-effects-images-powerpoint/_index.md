---
title: تطبيق تأثيرات Duotone على الصور في PowerPoint
linktitle: تطبيق تأثيرات Duotone على الصور في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تطبيق تأثيرات Duotone على الصور في PowerPoint باستخدام Aspose.Slides لـ Java من خلال دليلنا خطوة بخطوة. تعزيز العروض التقديمية الخاصة بك.
weight: 20
url: /ar/java/java-powerpoint-animation-shape-manipulation/apply-duotone-effects-images-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يمكن أن تؤدي إضافة تأثيرات مرئية إلى عروض PowerPoint التقديمية إلى تعزيز جاذبيتها وفعاليتها بشكل كبير. أحد هذه التأثيرات الجذابة هو تأثير Duotone، الذي يطبق لونين متباينين على الصورة، مما يمنحها مظهرًا عصريًا واحترافيًا. في هذا الدليل الشامل، سنرشدك خلال عملية تطبيق تأثيرات Duotone على الصور في PowerPoint باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك ما يلي:
1.  Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك. يمكنك تنزيله من[موقع أوراكل JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides لمكتبة Java: يمكنك تنزيل المكتبة من[صفحة تنزيل Aspose.Slides](https://releases.aspose.com/slides/java/).
3. بيئة التطوير المتكاملة (IDE): بيئة تطوير متكاملة مثل IntelliJ IDEA أو Eclipse لكتابة وتنفيذ كود Java الخاص بك.
4.  ملف الصورة: ملف صورة (على سبيل المثال،`aspose-logo.jpg`) لتطبيق تأثير Duotone.
## حزم الاستيراد
أولاً، ستحتاج إلى استيراد الحزم الضرورية في برنامج Java الخاص بك. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## الخطوة 1: إنشاء عرض تقديمي جديد
ابدأ بإنشاء كائن عرض تقديمي جديد. ستكون هذه هي اللوحة القماشية التي ستضيف فيها صورتك وتطبق تأثير Duotone.
```java
Presentation presentation = new Presentation();
```
## الخطوة 2: قراءة ملف الصورة
بعد ذلك، اقرأ ملف الصورة من الدليل الخاص بك. ستتم إضافة هذه الصورة إلى العرض التقديمي وسيتم تطبيق تأثير Duotone عليها.
```java
try {
    byte[] imageBytes = Files.readAllBytes(Paths.get("Your Document Directory/aspose-logo.jpg"));
```
## الخطوة 3: أضف الصورة إلى العرض التقديمي
أضف الصورة إلى مجموعة صور العرض التقديمي. هذه الخطوة تجعل الصورة متاحة للاستخدام داخل العرض التقديمي.
```java
    IPPImage backgroundImage = presentation.getImages().addImage(imageBytes);
```
## الخطوة 4: قم بتعيين الصورة كخلفية للشريحة
الآن، قم بتعيين الصورة كخلفية للشريحة الأولى. يتضمن ذلك تكوين نوع الخلفية وتنسيق التعبئة.
```java
    presentation.getSlides().get_Item(0).getBackground().setType(BackgroundType.OwnBackground);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().setFillType(FillType.Picture);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().setImage(backgroundImage);
```
## الخطوة 5: إضافة تأثير Duotone
أضف تأثير Duotone إلى صورة الخلفية. تتضمن هذه الخطوة إنشاء كائن Duotone وتعيين خصائصه.
```java
    IDuotone duotone = presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().getImageTransform().addDuotoneEffect();
```
## الخطوة 6: تعيين خصائص الفرز الثنائي
قم بتكوين تأثير Duotone عن طريق ضبط الألوان. هنا، نحن نستخدم ألوان المخطط لتأثير Duotone.
```java
    duotone.getColor1().setColorType(ColorType.Scheme);
    duotone.getColor1().setSchemeColor(SchemeColor.Accent1);
    duotone.getColor2().setColorType(ColorType.Scheme);
    duotone.getColor2().setSchemeColor(SchemeColor.Dark2);
```
## الخطوة 7: استرجاع وعرض قيم الفرز الثنائي الفعالة
للتحقق من التأثير، قم باسترداد القيم الفعالة لتأثير Duotone وطباعتها على وحدة التحكم.
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
يمكن أن يؤدي تطبيق تأثير Duotone على الصور في PowerPoint إلى منح عروضك التقديمية مظهرًا أنيقًا واحترافيًا. باستخدام Aspose.Slides لـ Java، تكون هذه العملية واضحة وقابلة للتخصيص بدرجة كبيرة. اتبع الخطوات الموضحة في هذا البرنامج التعليمي لإضافة تأثير Duotone إلى صورك وجعل عروضك التقديمية مميزة.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء عروض PowerPoint التقديمية وتعديلها ومعالجتها برمجياً.
### كيف أقوم بتثبيت Aspose.Slides لـ Java؟
 يمكنك تنزيل Aspose.Slides لـ Java من[صفحة التحميل](https://releases.aspose.com/slides/java/). اتبع تعليمات التثبيت المتوفرة في الوثائق.
### هل يمكنني استخدام Aspose.Slides لـ Java مع أي بيئة تطوير متكاملة (IDE)؟
نعم، Aspose.Slides for Java متوافق مع جميع بيئات التطوير المتكاملة (IDEs) الرئيسية، بما في ذلك IntelliJ IDEA وEclipse وNetBeans.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ Java؟
 نعم، يمكنك الحصول على نسخة تجريبية مجانية من[Aspose.Slides صفحة تجريبية مجانية](https://releases.aspose.com/).
### أين يمكنني العثور على المزيد من الأمثلة والوثائق الخاصة بـ Aspose.Slides لـ Java؟
 يمكنك العثور على وثائق وأمثلة شاملة على الموقع[صفحة وثائق Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
