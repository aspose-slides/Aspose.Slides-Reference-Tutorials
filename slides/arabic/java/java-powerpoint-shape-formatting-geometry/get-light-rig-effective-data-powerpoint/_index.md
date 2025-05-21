---
"description": "تعرف على كيفية استرداد بيانات Light Rig الفعالة من عروض PowerPoint باستخدام Aspose.Slides لـ Java في هذا الدليل المفصل خطوة بخطوة."
"linktitle": "احصل على بيانات Light Rig الفعالة في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "احصل على بيانات Light Rig الفعالة في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-formatting-geometry/get-light-rig-effective-data-powerpoint/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# احصل على بيانات Light Rig الفعالة في PowerPoint

## مقدمة
هل ترغب في أتمتة مهام عروض PowerPoint التقديمية باستخدام جافا؟ لا داعي للبحث أكثر! Aspose.Slides لجافا هي مكتبة فعّالة تُمكّن المطورين من إنشاء ملفات PowerPoint ومعالجتها وتحويلها دون الحاجة إلى تثبيت Microsoft PowerPoint. في هذا الدليل الشامل، سنشرح لك خطوات الحصول على بيانات فعّالة من عرض PowerPoint التقديمي باستخدام Aspose.Slides لجافا. سواء كنت مطور جافا محترفًا أو مبتدئًا، سيساعدك هذا البرنامج التعليمي على الاستفادة القصوى من إمكانات Aspose.Slides في مشاريعك.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK 8 أو أعلى على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).
3. IDE: استخدم بيئة التطوير المتكاملة (IDE) مثل IntelliJ IDEA أو Eclipse للترميز.
4. ملف العرض التقديمي: ملف PowerPoint نموذجي (`Presentation1.pptx`) لاختبار الكود.
## استيراد الحزم
أولاً، لنُعِدّ مشروعنا ونستورد الحزم اللازمة. أنشئ مشروع جافا جديدًا في بيئة التطوير المتكاملة لديك، وأضف مكتبة Aspose.Slides for Java إلى مسار بناء مشروعك.
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## الخطوة 1: إعداد دليل المشروع
ابدأ بإعداد دليل مشروعك. أنشئ مجلدًا لتخزين ملفات جافا وعرض PowerPoint التقديمي (`Presentation1.pptx`).
```java
String dataDir = "Your Document Directory";  // استبدل بالمسار الفعلي إلى دليل المستند الخاص بك
```
## الخطوة 2: تحميل العرض التقديمي
بعد ذلك، ستقوم بتحميل عرض PowerPoint باستخدام `Presentation` الفئة من Aspose.Slides.
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
## الخطوة 4: استرداد بيانات جهاز الإضاءة الفعّال
مع تحديد الشريحة والشكل الأولين، يمكنك استرداد خصائص جهاز الإضاءة الفعّالة.
```java
System.out.println("= Effective light rig properties =");
System.out.println("Type: " + threeDEffectiveData.getLightRig().getLightType());
System.out.println("Direction: " + threeDEffectiveData.getLightRig().getDirection());
```
## الخطوة 5: التخلص من كائن العرض التقديمي
وأخيرًا، تأكد من التخلص من كائن العرض لتحرير الموارد.
```java
} finally {
    if (pres != null) pres.dispose();
}
```
## خاتمة
تهانينا! لقد نجحت في استرداد بيانات جهاز الإضاءة الفعّال من عرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. غطّى هذا البرنامج التعليمي الخطوات الأساسية، من إعداد مشروعك إلى الوصول إلى خصائص جهاز الإضاءة وعرضها. يوفر Aspose.Slides مجموعة واسعة من الميزات التي تساعدك على التعامل مع ملفات PowerPoint برمجيًا، مما يجعله أداة قيّمة للمطورين.
## الأسئلة الشائعة
### ما هو Aspose.Slides لـ Java؟
Aspose.Slides for Java هي مكتبة قوية لإنشاء ملفات PowerPoint ومعالجتها وتحويلها باستخدام Java.
### هل يمكنني استخدام Aspose.Slides دون تثبيت Microsoft PowerPoint؟
نعم، يمكنك استخدام Aspose.Slides دون الحاجة إلى تثبيت Microsoft PowerPoint.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides؟
يمكنك الحصول على ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/).
### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ Java؟
الوثائق متاحة على [هذا الرابط](https://reference.aspose.com/slides/java/).
### كيف أحصل على الدعم لـ Aspose.Slides؟
يمكنك الحصول على الدعم من منتدى دعم Aspose.Slides [هنا](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}