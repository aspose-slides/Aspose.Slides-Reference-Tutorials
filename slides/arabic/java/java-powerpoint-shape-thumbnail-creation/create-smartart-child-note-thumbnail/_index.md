---
title: إنشاء صورة مصغرة لملاحظة SmartArt التابعة
linktitle: إنشاء صورة مصغرة لملاحظة SmartArt التابعة
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية إنشاء صور مصغرة لملاحظات SmartArt الفرعية في Java باستخدام Aspose.Slides، مما يعزز عروض PowerPoint التقديمية دون عناء.
weight: 15
url: /ar/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة لملاحظة SmartArt التابعة

## مقدمة
في هذا البرنامج التعليمي، سوف نستكشف كيفية إنشاء صور مصغرة لملاحظات الأطفال SmartArt في Java باستخدام Aspose.Slides. Aspose.Slides عبارة عن واجهة برمجة تطبيقات Java قوية تتيح للمطورين العمل مع عروض PowerPoint التقديمية برمجيًا، مما يمكنهم من إنشاء الشرائح وتعديلها ومعالجتها بسهولة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2.  تم تنزيل Aspose.Slides لمكتبة Java وتكوينها في مشروعك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/java/).

## حزم الاستيراد
تأكد من استيراد الحزم الضرورية في فئة Java الخاصة بك:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## الخطوة 1: قم بإعداد مشروعك
تأكد من إعداد مشروع Java وتكوينه باستخدام مكتبة Aspose.Slides.
## الخطوة 2: إنشاء عرض تقديمي
 إنشاء مثيل`Presentation` فئة لتمثيل ملف PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة SmartArt
أضف SmartArt إلى شريحة العرض التقديمي:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## الخطوة 4: الحصول على مرجع العقدة
الحصول على مرجع العقدة باستخدام فهرسها:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## الخطوة 5: الحصول على الصورة المصغرة
استرداد الصورة المصغرة لعقدة SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## الخطوة 6: حفظ الصورة المصغرة
حفظ الصورة المصغرة في ملف:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
كرر هذه الخطوات لكل عقدة SmartArt حسب الحاجة في العرض التقديمي الخاص بك.

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء صور مصغرة لملاحظات SmartArt الفرعية في Java باستخدام Aspose.Slides. باستخدام هذه المعرفة، يمكنك تحسين عروض PowerPoint التقديمية الخاصة بك برمجيًا، وإضافة عناصر جذابة بصريًا بسهولة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides لمعالجة ملفات PowerPoint الموجودة؟
نعم، يتيح لك Aspose.Slides تعديل ملفات PowerPoint الموجودة، بما في ذلك إضافة الشرائح ومحتوياتها أو إزالتها أو تحريرها.
### هل يدعم Aspose.Slides تصدير الشرائح إلى تنسيقات ملفات مختلفة؟
قطعاً! يدعم Aspose.Slides تصدير الشرائح إلى تنسيقات مختلفة، بما في ذلك PDF والصور وHTML وغيرها.
### هل Aspose.Slides مناسب لأتمتة PowerPoint على مستوى المؤسسة؟
نعم، تم تصميم Aspose.Slides للتعامل مع مهام أتمتة PowerPoint على مستوى المؤسسة بكفاءة وموثوقية.
### هل يمكنني إنشاء مخططات SmartArt معقدة برمجيًا باستخدام Aspose.Slides؟
بالتأكيد! يوفر Aspose.Slides دعمًا شاملاً لإنشاء ومعالجة مخططات SmartArt ذات التعقيدات المختلفة.
### هل يقدم Aspose.Slides الدعم الفني للمطورين؟
 نعم، يوفر Aspose.Slides دعمًا فنيًا مخصصًا للمطورين من خلال[المنتدى](https://forum.aspose.com/c/slides/11) وغيرها من القنوات.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
