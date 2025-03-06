---
title: إضافة خط عادي إلى الشريحة
linktitle: إضافة خط عادي إلى الشريحة
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إضافة خط عادي إلى شريحة PowerPoint برمجياً باستخدام Aspose.Slides لـ Java. عزز إنتاجيتك باستخدام هذا الدليل المفصّل خطوة بخطوة.
weight: 14
url: /ar/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## مقدمة
Aspose.Slides for Java هي مكتبة قوية تسمح لمطوري Java بالعمل مع عروض PowerPoint التقديمية برمجياً. باستخدام Aspose.Slides، يمكنك إنشاء ملفات PowerPoint وتعديلها وتحويلها بسهولة، مما يوفر لك الوقت والجهد. في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة خط عادي إلى شريحة في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- تم تثبيت Java Development Kit (JDK) على نظامك
- تم تنزيل Aspose.Slides لمكتبة Java وإضافتها إلى مشروع Java الخاص بك
- المعرفة الأساسية بلغة البرمجة جافا

## حزم الاستيراد
للبدء، تحتاج إلى استيراد الحزم الضرورية في كود Java الخاص بك. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## الخطوة 1: إعداد البيئة
 أولاً، قم بإنشاء مشروع Java جديد وأضف مكتبة Aspose.Slides for Java إلى مسار الفصل الخاص بمشروعك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).
## الخطوة 2: إنشاء عرض تقديمي جديد
 بعد ذلك، قم بإنشاء مثيل`Presentation` فئة لإنشاء عرض تقديمي جديد ل PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شريحة
احصل على الشريحة الأولى من العرض التقديمي وقم بتخزينها في متغير.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل خط
الآن، قم بإضافة شكل تلقائي لخط الكتابة إلى الشريحة.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## الخطوة 5: احفظ العرض التقديمي
وأخيرا، احفظ العرض التقديمي على القرص.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد نجحت في إضافة سطر عادي إلى شريحة في عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. باستخدام Aspose.Slides، يمكنك التعامل بسهولة مع ملفات PowerPoint برمجيًا، مما يفتح عالمًا من الإمكانيات لتطبيقات Java الخاصة بك.

## الأسئلة الشائعة
### هل يمكنني تخصيص خصائص شكل الخط؟
نعم، يمكنك تخصيص خصائص مختلفة مثل لون الخط والعرض والنمط والمزيد باستخدام Aspose.Slides API.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides تنسيقات PowerPoint المتنوعة، بما في ذلك PPT وPPTX وغيرها، مما يضمن التوافق عبر الإصدارات المختلفة.
### هل يوفر Aspose.Slides الدعم لإضافة أشكال أخرى إلى جانب الخطوط؟
قطعاً! يقدم Aspose.Slides مجموعة واسعة من أنواع الأشكال، بما في ذلك المستطيلات والدوائر والأسهم والمزيد.
### هل يمكنني إضافة نص إلى الشريحة مع شكل الخط؟
نعم، يمكنك إضافة نص وصور ومحتويات أخرى إلى الشريحة باستخدام Aspose.Slides API.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides من[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
