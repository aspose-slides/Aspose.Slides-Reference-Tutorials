---
"description": "تعلّم كيفية إضافة خط عادي إلى شريحة PowerPoint برمجيًا باستخدام Aspose.Slides لجافا. عزّز إنتاجيتك باتباع هذا الدليل المفصّل."
"linktitle": "إضافة خط عادي إلى الشريحة"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة خط عادي إلى الشريحة"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة خط عادي إلى الشريحة

## مقدمة
Aspose.Slides لجافا هي مكتبة فعّالة تُمكّن مطوري جافا من العمل مع عروض PowerPoint التقديمية برمجيًا. باستخدام Aspose.Slides، يمكنك إنشاء ملفات PowerPoint وتعديلها وتحويلها بسهولة، مما يوفر عليك الوقت والجهد. في هذا البرنامج التعليمي، سنشرح لك عملية إضافة خط عادي إلى شريحة في عرض PowerPoint التقديمي باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
- مجموعة تطوير Java (JDK) مثبتة على نظامك
- تم تنزيل مكتبة Aspose.Slides لـ Java وإضافتها إلى مشروع Java الخاص بك
- المعرفة الأساسية بلغة البرمجة جافا

## استيراد الحزم
للبدء، عليك استيراد الحزم اللازمة في شيفرة جافا. إليك كيفية القيام بذلك:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## الخطوة 1: إعداد البيئة
أولاً، أنشئ مشروع جافا جديدًا وأضف مكتبة Aspose.Slides for Java إلى مسار مشروعك. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).
## الخطوة 2: إنشاء عرض تقديمي جديد
بعد ذلك، قم بإنشاء مثيل `Presentation` فئة لإنشاء عرض تقديمي جديد في PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة شريحة
احصل على الشريحة الأولى من العرض التقديمي وقم بتخزينها في متغير.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة شكل خط
الآن، قم بإضافة شكل تلقائي من نوع الخط إلى الشريحة.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## الخطوة 5: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي على القرص.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد نجحت في إضافة خط بسيط إلى شريحة في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لجافا. مع Aspose.Slides، يمكنك بسهولة التعامل مع ملفات PowerPoint برمجيًا، مما يفتح آفاقًا واسعة لتطبيقات Java الخاصة بك.

## الأسئلة الشائعة
### هل يمكنني تخصيص خصائص شكل الخط؟
نعم، يمكنك تخصيص خصائص مختلفة مثل لون الخط والعرض والنمط والمزيد باستخدام واجهة برمجة تطبيقات Aspose.Slides.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
نعم، يدعم Aspose.Slides تنسيقات PowerPoint المختلفة، بما في ذلك PPT وPPTX وغيرها، مما يضمن التوافق بين الإصدارات المختلفة.
### هل يوفر Aspose.Slides الدعم لإضافة أشكال أخرى بالإضافة إلى الخطوط؟
بالتأكيد! يوفر Aspose.Slides مجموعة واسعة من الأشكال، بما في ذلك المستطيلات والدوائر والأسهم وغيرها.
### هل يمكنني إضافة نص إلى الشريحة مع شكل الخط؟
نعم، يمكنك إضافة نصوص وصور ومحتوى آخر إلى الشريحة باستخدام واجهة برمجة التطبيقات Aspose.Slides.
### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Slides من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}