---
title: إضافة إطار كائن OLE في PowerPoint
linktitle: إضافة إطار كائن OLE في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية دمج إطارات كائنات OLE بسلاسة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java.
weight: 13
url: /ar/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## مقدمة
يمكن أن تؤدي إضافة إطار كائن OLE (ربط الكائنات وتضمينها) في عروض PowerPoint التقديمية إلى تحسين المظهر المرئي ووظائف الشرائح بشكل كبير. مع Aspose.Slides لـ Java، تصبح هذه العملية مبسطة وفعالة. في هذا البرنامج التعليمي، سنرشدك خلال الخطوات المطلوبة لدمج إطارات كائنات OLE بسلاسة في عروض PowerPoint التقديمية.
### المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1. بيئة تطوير Java: تأكد من تثبيت Java Development Kit (JDK) على نظامك.
2.  Aspose.Slides for Java: قم بتنزيل Aspose.Slides for Java وتثبيته من موقع الويب[هنا](https://releases.aspose.com/slides/java/).
3. الفهم الأساسي لبرمجة Java: تعرف على مفاهيم برمجة Java وبناء الجملة.
## حزم الاستيراد
أولاً، تحتاج إلى استيراد الحزم اللازمة للاستفادة من وظائف Aspose.Slides لـ Java. وإليك كيف يمكنك القيام بذلك:
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## الخطوة 1: إعداد بيئتك
تأكد من تكوين مشروعك بشكل صحيح ومن تضمين مكتبة Aspose.Slides في مسار الفصل الدراسي الخاص بك.
## الخطوة 2: تهيئة كائن العرض التقديمي
قم بإنشاء كائن عرض تقديمي لتمثيل ملف PowerPoint الذي تعمل به:
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: الوصول إلى الشريحة وتحميل الكائن
قم بالوصول إلى الشريحة التي تريد إضافة إطار كائن OLE إليها وتحميل ملف الكائن:
```java
ISlide sld = pres.getSlides().get_Item(0);
// قم بتحميل ملف للبث
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## الخطوة 4: إنشاء كائن بيانات مضمن
قم بإنشاء كائن بيانات لتضمين الملف:
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## الخطوة 5: إضافة إطار كائن OLE
أضف شكل إطار كائن OLE إلى الشريحة:
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدل على القرص:
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطار كائن OLE في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ Java. تسمح لك هذه الميزة القوية بتضمين أنواع مختلفة من الكائنات، مما يعزز التفاعل والجاذبية البصرية لشرائحك.

## الأسئلة الشائعة
### هل يمكنني تضمين كائنات أخرى غير ملفات Excel باستخدام Aspose.Slides لـ Java؟
نعم، يمكنك تضمين أنواع مختلفة من الكائنات بما في ذلك مستندات Word وملفات PDF والمزيد.
### هل Aspose.Slides متوافق مع الإصدارات المختلفة من PowerPoint؟
يوفر Aspose.Slides التوافق مع مجموعة واسعة من إصدارات PowerPoint، مما يضمن التكامل السلس.
### هل يمكنني تخصيص مظهر إطار كائن OLE؟
قطعاً! يوفر Aspose.Slides خيارات شاملة لتخصيص مظهر وسلوك إطارات كائنات OLE.
### هل هناك إصدار تجريبي متاح لـ Aspose.Slides لـ Java؟
 نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
### أين يمكنني العثور على الدعم لـ Aspose.Slides لـ Java؟
 يمكنك طلب الدعم والمساعدة من منتدى Aspose.Slides[هنا](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
