---
"description": "تعرف على كيفية إنشاء صور مصغرة لملاحظات الأطفال SmartArt في Java باستخدام Aspose.Slides، مما يعزز عروض PowerPoint الخاصة بك بسهولة."
"linktitle": "إنشاء صورة مصغرة لملاحظة فرعية في SmartArt"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إنشاء صورة مصغرة لملاحظة فرعية في SmartArt"
"url": "/ar/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء صورة مصغرة لملاحظة فرعية في SmartArt

## مقدمة
في هذا البرنامج التعليمي، سنستكشف كيفية إنشاء صور مصغّرة لملاحظات فرعية بتقنية SmartArt في جافا باستخدام Aspose.Slides. Aspose.Slides هي واجهة برمجة تطبيقات Java فعّالة تُمكّن المطورين من العمل مع عروض PowerPoint التقديمية برمجيًا، مما يُمكّنهم من إنشاء الشرائح وتعديلها ومعالجتها بسهولة.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من أن لديك ما يلي:
1. تم تثبيت Java Development Kit (JDK) على نظامك.
2. تم تنزيل مكتبة Aspose.Slides لجافا وتهيئتها في مشروعك. يمكنك تنزيل المكتبة من [هنا](https://releases.aspose.com/slides/java/).

## استيراد الحزم
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
## الخطوة 1: إعداد مشروعك
تأكد من إعداد مشروع Java وتكوينه باستخدام مكتبة Aspose.Slides.
## الخطوة 2: إنشاء عرض تقديمي
إنشاء مثيل `Presentation` الفئة لتمثيل ملف PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة SmartArt
أضف SmartArt إلى شريحة العرض التقديمي الخاصة بك:
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
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء صور مصغّرة لملاحظات فرعية بتقنية SmartArt في جافا باستخدام Aspose.Slides. بفضل هذه المعرفة، يمكنك تحسين عروض PowerPoint التقديمية برمجيًا، وإضافة عناصر جذابة بصريًا بسهولة.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Slides للتعامل مع ملفات PowerPoint الموجودة؟
نعم، يسمح لك Aspose.Slides بتعديل ملفات PowerPoint الموجودة، بما في ذلك إضافة الشرائح ومحتوياتها أو إزالتها أو تحريرها.
### هل يدعم Aspose.Slides تصدير الشرائح إلى تنسيقات ملفات مختلفة؟
بالتأكيد! يدعم Aspose.Slides تصدير الشرائح إلى صيغ مختلفة، بما في ذلك PDF والصور وHTML وغيرها.
### هل Aspose.Slides مناسب لأتمتة PowerPoint على مستوى المؤسسات؟
نعم، تم تصميم Aspose.Slides للتعامل مع مهام أتمتة PowerPoint على مستوى المؤسسة بكفاءة وموثوقية.
### هل يمكنني إنشاء مخططات SmartArt معقدة برمجيًا باستخدام Aspose.Slides؟
بالتأكيد! يوفر Aspose.Slides دعمًا شاملاً لإنشاء ومعالجة مخططات SmartArt بدرجات متفاوتة من التعقيد.
### هل يقدم Aspose.Slides الدعم الفني للمطورين؟
نعم، يوفر Aspose.Slides دعمًا فنيًا مخصصًا للمطورين من خلال [المنتدى](https://forum.aspose.com/c/slides/11) وقنوات أخرى.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}