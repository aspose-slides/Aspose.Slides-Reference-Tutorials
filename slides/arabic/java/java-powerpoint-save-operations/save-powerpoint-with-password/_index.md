---
"description": "تعرّف على كيفية إضافة حماية بكلمة مرور لعروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. وفّر الحماية لعروضك التقديمية بسهولة."
"linktitle": "حفظ PowerPoint بكلمة مرور"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "حفظ PowerPoint بكلمة مرور"
"url": "/ar/java/java-powerpoint-save-operations/save-powerpoint-with-password/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# حفظ PowerPoint بكلمة مرور

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية حفظ عرض تقديمي في PowerPoint بكلمة مرور باستخدام Aspose.Slides لجافا. إضافة كلمة مرور لعرضك التقديمي تُعزز أمانه، مما يضمن وصول الأشخاص المصرح لهم فقط إلى محتواه.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على نظامك.
2. Aspose.Slides لـ Java: قم بتنزيل Aspose.Slides لـ Java وتثبيته من [صفحة التحميل](https://releases.aspose.com/slides/java/).

## استيراد الحزم
أولاً، عليك استيراد الحزم الضرورية في ملف Java الخاص بك:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

import java.io.File;
```
## الخطوة 1: إعداد البيئة
تأكد من وجود مجلد لتخزين ملف العرض التقديمي. إذا لم يكن موجودًا، فأنشئ واحدًا.
```java
// المسار إلى دليل المستندات.
String dataDir = "path/to/your/directory/";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء كائن عرض تقديمي
إنشاء كائن عرض تقديمي يمثل ملف PowerPoint.
```java
// إنشاء كائن عرض تقديمي
Presentation pres = new Presentation();
```
## الخطوة 3: تعيين حماية كلمة المرور
تعيين كلمة مرور للعرض التقديمي باستخدام `encrypt` طريقة `ProtectionManager`.
```java
// تعيين كلمة المرور
pres.getProtectionManager().encrypt("your_password");
```
يستبدل `"your_password"` مع كلمة المرور المطلوبة لعرضك التقديمي.
## الخطوة 4: حفظ العرض التقديمي
احفظ العرض التقديمي الخاص بك في ملف باستخدام كلمة المرور المحددة.
```java
// احفظ عرضك التقديمي في ملف
pres.save(dataDir + "SaveWithPassword_out.pptx", SaveFormat.Pptx);
```
سيقوم هذا الكود بحفظ العرض التقديمي الخاص بك بكلمة المرور في الدليل المحدد.

## خاتمة
يُعدّ تأمين عروض PowerPoint التقديمية بكلمات مرور أمرًا بالغ الأهمية لحماية المعلومات الحساسة. مع Aspose.Slides لـ Java، يمكنك بسهولة إضافة حماية بكلمة مرور إلى عروضك التقديمية، مما يضمن وصول المستخدمين المصرح لهم فقط إليها.

## الأسئلة الشائعة
### هل يمكنني إزالة حماية كلمة المرور من عرض تقديمي في PowerPoint؟
نعم، يمكنك إزالة حماية كلمة المرور باستخدام Aspose.Slides. راجع الوثائق للاطلاع على التعليمات المفصلة.
### هل Aspose.Slides متوافق مع كافة إصدارات PowerPoint؟
يدعم Aspose.Slides تنسيقات PowerPoint متنوعة، بما في ذلك PPTX وPPT وغيرها. راجع الوثائق لمعرفة تفاصيل التوافق.
### هل يمكنني تعيين كلمات مرور مختلفة لتحرير العرض التقديمي وعرضه؟
نعم، يسمح لك Aspose.Slides بتعيين كلمات مرور منفصلة لأذونات التحرير والعرض.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose [موقع إلكتروني](https://releases.aspose.com/).
### كيف يمكنني الحصول على الدعم الفني لـ Aspose.Slides؟
يمكنك زيارة منتدى Aspose.Slides للحصول على المساعدة الفنية من المجتمع وموظفي دعم Aspose.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}