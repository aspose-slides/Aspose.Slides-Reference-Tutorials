---
title: إضافة إطار فيديو مضمن في PowerPoint
linktitle: إضافة إطار فيديو مضمن في PowerPoint
second_title: Aspose.Slides واجهة برمجة تطبيقات معالجة Java PowerPoint
description: تعرف على كيفية تضمين إطارات الفيديو في PowerPoint باستخدام Aspose.Slides لـ Java من خلال هذا البرنامج التعليمي خطوة بخطوة. تعزيز العروض التقديمية الخاصة بك بسهولة.
weight: 21
url: /ar/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار فيديو مضمن في PowerPoint

## مقدمة
يمكن أن تؤدي إضافة مقاطع فيديو إلى عروض PowerPoint التقديمية إلى جعلها أكثر جاذبية وغنية بالمعلومات. باستخدام Aspose.Slides for Java، يمكنك بسهولة تضمين مقاطع الفيديو مباشرة في الشرائح الخاصة بك. في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة، مما يضمن فهمك لكل جزء من التعليمات البرمجية وكيفية عمله. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا الدليل على تحسين عروضك التقديمية باستخدام مقاطع الفيديو المضمنة.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من توفر المتطلبات الأساسية التالية:
1. Java Development Kit (JDK): تأكد من تثبيت JDK على جهازك.
2. Aspose.Slides for Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides for Java.
3. بيئة التطوير المتكاملة (IDE): استخدم IDE مثل IntelliJ IDEA أو Eclipse للحصول على تجربة تطوير أفضل.
4. ملف الفيديو: لديك ملف فيديو تريد تضمينه في عرض PowerPoint التقديمي الخاص بك.
## حزم الاستيراد
أولاً، ستحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Slides. ستساعدك عمليات الاستيراد هذه على إدارة الشرائح ومقاطع الفيديو وملفات العروض التقديمية.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## الخطوة 1: إعداد بيئتك
قبل البدء في البرمجة، تأكد من إعداد البيئة الخاصة بك بشكل صحيح. يتضمن ذلك إنشاء الدلائل اللازمة وإعداد ملف الفيديو.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء مثيل لفئة العرض التقديمي
 إنشاء مثيل لـ`Presentation` فصل. يمثل هذا الفصل ملف PowerPoint الخاص بك.
```java
// إنشاء فئة العرض التقديمي التي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: احصل على الشريحة الأولى
قم بالوصول إلى الشريحة الأولى في العرض التقديمي حيث ستقوم بتضمين الفيديو.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: أضف الفيديو إلى العرض التقديمي
تضمين ملف الفيديو في العرض التقديمي. تأكد من تحديد مسار الفيديو بشكل صحيح.
```java
// تضمين الفيديو داخل العرض التقديمي
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## الخطوة 5: إضافة إطار فيديو إلى الشريحة
قم بإنشاء إطار فيديو على الشريحة وضبط أبعاده وموضعه.
```java
// إضافة إطار الفيديو
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## الخطوة 6: تكوين خصائص إطار الفيديو
اضبط الفيديو على إطار الفيديو وقم بتكوين إعدادات التشغيل الخاصة به مثل وضع التشغيل ومستوى الصوت.
```java
// اضبط الفيديو على إطار الفيديو
vf.setEmbeddedVideo(vid);
// ضبط وضع التشغيل وحجم الفيديو
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 7: احفظ العرض التقديمي
احفظ العرض التقديمي مع الفيديو المضمن في الدليل المحدد الخاص بك.
```java
// اكتب ملف PPTX على القرص
pres.save(resultPath, SaveFormat.Pptx);
```
## الخطوة 8: تنظيف الموارد
وأخيراً، تخلص من كائن العرض التقديمي لتحرير الموارد.
```java
// تخلص من كائن العرض التقديمي
if (pres != null) pres.dispose();
```
## خاتمة
يعد تضمين مقطع فيديو في عروض PowerPoint التقديمية باستخدام Aspose.Slides for Java عملية مباشرة. باتباع الخطوات الموضحة في هذا الدليل، يمكنك تحسين عروضك التقديمية بمحتوى فيديو جذاب. تذكر أن الممارسة تؤدي إلى الإتقان، لذا حاول تضمين مقاطع فيديو مختلفة وضبط خصائصها لمعرفة ما يناسب احتياجاتك بشكل أفضل.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو متعددة في شريحة واحدة؟
نعم، يمكنك تضمين مقاطع فيديو متعددة في شريحة واحدة عن طريق إضافة إطارات فيديو متعددة.
### كيف يمكنني التحكم في تشغيل الفيديو؟
 يمكنك التحكم في التشغيل باستخدام`setPlayMode` و`setVolume` أساليب`IVideoFrame` فصل.
### ما هي تنسيقات الفيديو التي يدعمها Aspose.Slides؟
يدعم Aspose.Slides تنسيقات الفيديو المختلفة بما في ذلك MP4 وAVI وWMV.
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides؟
نعم، أنت بحاجة إلى ترخيص صالح لاستخدام Aspose.Slides. يمكنك الحصول على ترخيص مؤقت للتقييم.
### هل يمكنني تخصيص حجم وموضع إطار الفيديو؟
نعم، يمكنك تخصيص الحجم والموضع عن طريق تعيين المعلمات المناسبة عند إضافة إطار الفيديو.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
