---
title: احصل على بيانات Light Rig الفعالة في PowerPoint
linktitle: احصل على بيانات Light Rig الفعالة في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية استرداد البيانات الفعالة لجهاز الإضاءة من عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java في هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 25
url: /ar/java/java-powerpoint-shape-formatting-geometry/get-light-rig-effective-data-powerpoint/
---
## مقدمة
هل تتطلع إلى أتمتة مهام عرض PowerPoint التقديمي باستخدام Java؟ لا مزيد من البحث! Aspose.Slides for Java هي مكتبة قوية تسمح للمطورين بإنشاء ملفات PowerPoint ومعالجتها وتحويلها دون الحاجة إلى تثبيت Microsoft PowerPoint. في هذا الدليل الشامل، سنوجهك عبر الخطوات اللازمة للحصول على بيانات فعالة من عرض تقديمي لـ PowerPoint باستخدام Aspose.Slides for Java. سواء كنت مطور Java متمرسًا أو بدأت للتو، سيساعدك هذا البرنامج التعليمي على الاستفادة من الإمكانات الكاملة لـ Aspose.Slides في مشاريعك.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK 8 أو إصدار أعلى على نظامك.
2.  Aspose.Slides for Java: قم بتنزيل المكتبة من[هنا](https://releases.aspose.com/slides/java/).
3. IDE: استخدم بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse للبرمجة.
4. ملف العرض التقديمي: نموذج لملف PowerPoint (`Presentation1.pptx`) لاختبار الكود.
## حزم الاستيراد
أولاً، لنقم بإعداد مشروعنا واستيراد الحزم الضرورية. قم بإنشاء مشروع Java جديد في IDE الخاص بك وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## الخطوة 1: إعداد دليل المشروع
ابدأ بإعداد دليل مشروعك. قم بإنشاء مجلد حيث سيتم تخزين ملفات Java وعرض PowerPoint التقديمي (`Presentation1.pptx`).
```java
String dataDir = "Your Document Directory";  // استبدل بالمسار الفعلي إلى دليل المستندات الخاص بك
```
## الخطوة 2: قم بتحميل العرض التقديمي
 بعد ذلك، ستقوم بتحميل عرض PowerPoint التقديمي باستخدام ملف`Presentation` فئة من Aspose.Slides.
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## الخطوة 3: الوصول إلى الشريحة الأولى
بمجرد تحميل العرض التقديمي، قم بالوصول إلى الشريحة الأولى في العرض التقديمي.
```java
try {
    IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
}
```
## الخطوة 4: استرداد بيانات جهاز الإضاءة الفعال
مع تحديد الشريحة والشكل الأولين، يمكنك استرداد خصائص جهاز الإضاءة الفعال.
```java
System.out.println("= Effective light rig properties =");
System.out.println("Type: " + threeDEffectiveData.getLightRig().getLightType());
System.out.println("Direction: " + threeDEffectiveData.getLightRig().getDirection());
```
## الخطوة 5: التخلص من كائن العرض التقديمي
وأخيرًا، تأكد من التخلص من كائن العرض التقديمي لتحرير الموارد.
```java
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
تهانينا! لقد نجحت في استرداد بيانات جهاز الإضاءة الفعال من عرض PowerPoint التقديمي باستخدام Aspose.Slides لـ Java. غطى هذا البرنامج التعليمي الخطوات الأساسية، بدءًا من إعداد مشروعك وحتى الوصول إلى خصائص جهاز الإضاءة وعرضها. يوفر Aspose.Slides مجموعة كبيرة من الميزات التي يمكن أن تساعدك في التعامل مع ملفات PowerPoint برمجيًا، مما يجعلها أداة لا تقدر بثمن للمطورين.
## الأسئلة الشائعة
### ما هو Aspose.Slides لجافا؟
Aspose.Slides for Java هي مكتبة قوية لإنشاء ملفات PowerPoint ومعالجتها وتحويلها باستخدام Java.
### هل يمكنني استخدام Aspose.Slides دون تثبيت Microsoft PowerPoint؟
نعم، يمكنك استخدام Aspose.Slides دون الحاجة إلى تثبيت Microsoft PowerPoint.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
 الوثائق متاحة في[هذا الرابط](https://reference.aspose.com/slides/java/).
### كيف يمكنني الحصول على الدعم لـ Aspose.Slides؟
 يمكنك الحصول على الدعم من منتدى دعم Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).