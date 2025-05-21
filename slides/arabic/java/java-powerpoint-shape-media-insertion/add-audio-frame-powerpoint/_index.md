---
"description": "تعرّف على كيفية إضافة إطارات صوتية إلى عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية بعناصر صوتية جذابة بكل سهولة."
"linktitle": "إضافة إطار صوتي في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إطار صوتي في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار صوتي في PowerPoint

## مقدمة
يُمكن لتعزيز العروض التقديمية بعناصر صوتية أن يُعزز تأثيرها وتفاعل الجمهور معها بشكل ملحوظ. مع Aspose.Slides لجافا، يُصبح دمج إطارات الصوت في عروض PowerPoint التقديمية عمليةً سلسة. سيُرشدك هذا البرنامج التعليمي خطوة بخطوة خلال عملية إضافة إطارات الصوت إلى عروضك التقديمية باستخدام Aspose.Slides لجافا.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك المتطلبات الأساسية التالية:
1. مجموعة تطوير Java (JDK): تأكد من تثبيت Java على نظامك.
2. مكتبة Aspose.Slides لجافا: نزّل وثبّت مكتبة Aspose.Slides لجافا. يمكنك تنزيلها من [توثيق Aspose.Slides لـ Java](https://reference.aspose.com/slides/java/).
3. ملف الصوت: قم بإعداد ملف الصوت (على سبيل المثال، تنسيق WAV) الذي تريد إضافته إلى العرض التقديمي الخاص بك.
## استيراد الحزم
استيراد الحزم اللازمة إلى مشروع Java الخاص بك:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## الخطوة 1: إعداد دليل المشروع الخاص بك
تأكد من إعداد هيكلية دليل لمشروعك. إذا لم يكن الأمر كذلك، فأنشئ واحدًا لتنظيم ملفاتك بفعالية.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## الخطوة 2: إنشاء فئة العرض التقديمي
إنشاء مثيل `Presentation` فئة لتمثيل عرض PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: الحصول على الشريحة وتحميل ملف الصوت
استرداد الشريحة الأولى وتحميل ملف الصوت من الدليل الخاص بك.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## الخطوة 4: إضافة إطار صوتي
أضف إطار الصوت إلى الشريحة.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## الخطوة 5: تعيين خصائص الصوت
تعيين خصائص مثل التشغيل عبر الشرائح، وإعادة الصوت، ووضع التشغيل، ومستوى الصوت.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 6: حفظ العرض التقديمي
احفظ العرض التقديمي المعدّل مع إطار الصوت المضاف.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## خاتمة
إن دمج عناصر الصوت في عروض PowerPoint التقديمية يُعزز فعاليتها ويجذب جمهورك. مع Aspose.Slides لجافا، تُصبح عملية إضافة إطارات الصوت سهلة، مما يُتيح لك إنشاء عروض تقديمية ديناميكية وجذابة دون عناء.

## الأسئلة الشائعة
### هل يمكنني إضافة ملفات صوتية بتنسيقات مختلفة إلى العرض التقديمي الخاص بي؟
نعم، يدعم Aspose.Slides for Java تنسيقات الصوت المختلفة، بما في ذلك WAV وMP3 والمزيد.
### هل من الممكن تعديل توقيت تشغيل الصوت في الشرائح؟
بالتأكيد. يمكنك مزامنة تشغيل الصوت مع انتقالات شرائح محددة باستخدام Aspose.Slides لـ Java.
### هل يوفر Aspose.Slides for Java الدعم للتوافق بين الأنظمة الأساسية؟
نعم، يمكنك إنشاء عروض تقديمية في PowerPoint مع إطارات صوتية مضمنة متوافقة مع منصات مختلفة.
### هل يمكنني تخصيص مظهر مشغل الصوت في العرض التقديمي؟
يوفر Aspose.Slides for Java خيارات تخصيص واسعة النطاق، مما يسمح لك بتخصيص مظهر مشغل الصوت ليناسب تفضيلاتك.
### هل هناك نسخة تجريبية متاحة لـ Aspose.Slides لـ Java؟
نعم، يمكنك الوصول إلى نسخة تجريبية مجانية من Aspose.Slides for Java من خلال [موقع إلكتروني](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}