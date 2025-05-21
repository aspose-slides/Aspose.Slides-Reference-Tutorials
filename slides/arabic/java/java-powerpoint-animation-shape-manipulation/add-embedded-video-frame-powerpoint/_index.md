---
"description": "تعلّم كيفية تضمين إطارات الفيديو في PowerPoint باستخدام Aspose.Slides لجافا من خلال هذا البرنامج التعليمي خطوة بخطوة. حسّن عروضك التقديمية بسهولة."
"linktitle": "إضافة إطار فيديو مضمن في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إطار فيديو مضمن في PowerPoint"
"url": "/ar/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار فيديو مضمن في PowerPoint

## مقدمة
إضافة مقاطع فيديو إلى عروض PowerPoint التقديمية تجعلها أكثر تشويقًا وإثراءً بالمعلومات. باستخدام Aspose.Slides لجافا، يمكنك بسهولة تضمين مقاطع الفيديو مباشرةً في شرائحك. في هذا البرنامج التعليمي، سنشرح لك العملية خطوة بخطوة، مع ضمان فهمك لكل جزء من الشيفرة البرمجية وكيفية عملها. سواء كنت مطورًا محترفًا أو مبتدئًا، سيساعدك هذا الدليل على تحسين عروضك التقديمية باستخدام مقاطع فيديو مدمجة.
## المتطلبات الأساسية
قبل الغوص في الكود، تأكد من توفر المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت JDK على جهازك.
2. Aspose.Slides لـ Java: قم بتنزيل وتثبيت مكتبة Aspose.Slides لـ Java.
3. بيئة التطوير المتكاملة (IDE): استخدم بيئة التطوير المتكاملة مثل IntelliJ IDEA أو Eclipse للحصول على تجربة تطوير أفضل.
4. ملف الفيديو: هل لديك ملف فيديو تريد تضمينه في عرض PowerPoint الخاص بك.
## استيراد الحزم
أولاً، ستحتاج إلى استيراد الحزم اللازمة للعمل مع Aspose.Slides. ستساعدك هذه الاستيرادات في إدارة الشرائح ومقاطع الفيديو وملفات العروض التقديمية.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## الخطوة 1: إعداد البيئة الخاصة بك
قبل البدء بالبرمجة، تأكد من إعداد بيئتك بشكل صحيح. يتضمن ذلك إنشاء المجلدات اللازمة وتجهيز ملف الفيديو.
```java
// المسار إلى دليل المستندات.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء فئة العرض التقديمي
إنشاء مثيل لـ `Presentation` هذه الفئة تمثل ملف PowerPoint الخاص بك.
```java
// إنشاء فئة عرض تقديمي تمثل PPTX
Presentation pres = new Presentation();
```
## الخطوة 3: الحصول على الشريحة الأولى
انتقل إلى الشريحة الأولى في العرض التقديمي حيث ستقوم بتضمين الفيديو.
```java
// احصل على الشريحة الأولى
ISlide sld = pres.getSlides().get_Item(0);
```
## الخطوة 4: إضافة الفيديو إلى العرض التقديمي
أدرج ملف الفيديو في العرض التقديمي. تأكد من تحديد مسار الفيديو بشكل صحيح.
```java
// تضمين الفيديو داخل العرض التقديمي
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## الخطوة 5: إضافة إطار فيديو إلى الشريحة
قم بإنشاء إطار فيديو على الشريحة وحدد أبعاده وموضعه.
```java
// إضافة إطار فيديو
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## الخطوة 6: تكوين خصائص إطار الفيديو
قم بضبط الفيديو على إطار الفيديو وقم بتكوين إعدادات التشغيل الخاصة به مثل وضع التشغيل ومستوى الصوت.
```java
// تعيين الفيديو إلى إطار الفيديو
vf.setEmbeddedVideo(vid);
// ضبط وضع التشغيل ومستوى صوت الفيديو
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 7: حفظ العرض التقديمي
احفظ العرض التقديمي مع الفيديو المضمن في الدليل المحدد.
```java
// اكتب ملف PPTX على القرص
pres.save(resultPath, SaveFormat.Pptx);
```
## الخطوة 8: تنظيف الموارد
أخيرًا، تخلص من كائن العرض لتحرير الموارد.
```java
// التخلص من كائن العرض
if (pres != null) pres.dispose();
```
## خاتمة
تضمين فيديو في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا عملية سهلة وبسيطة. باتباع الخطوات الموضحة في هذا الدليل، يمكنك تحسين عروضك التقديمية بمحتوى فيديو جذاب. تذكر، الممارسة تصنع الإتقان، لذا جرّب تضمين مقاطع فيديو مختلفة وتعديل خصائصها لاختيار الأنسب لاحتياجاتك.
## الأسئلة الشائعة
### هل يمكنني تضمين مقاطع فيديو متعددة في شريحة واحدة؟
نعم، يمكنك تضمين مقاطع فيديو متعددة في شريحة واحدة عن طريق إضافة إطارات فيديو متعددة.
### كيف يمكنني التحكم في تشغيل الفيديو؟
يمكنك التحكم في التشغيل باستخدام `setPlayMode` و `setVolume` طرق `IVideoFrame` فصل.
### ما هي تنسيقات الفيديو التي يدعمها Aspose.Slides؟
يدعم Aspose.Slides تنسيقات الفيديو المختلفة بما في ذلك MP4 وAVI وWMV.
### هل أحتاج إلى ترخيص لاستخدام Aspose.Slides؟
نعم، تحتاج إلى ترخيص صالح لاستخدام Aspose.Slides. يمكنك الحصول على ترخيص مؤقت للتقييم.
### هل يمكنني تخصيص حجم وموضع إطار الفيديو؟
نعم، يمكنك تخصيص الحجم والموضع عن طريق تعيين المعلمات المناسبة عند إضافة إطار الفيديو.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}