---
"description": "تعلّم كيفية دمج محتوى الفيديو بسلاسة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لجافا. شرائحك مزودة بعناصر وسائط متعددة لجذب جمهورك."
"linktitle": "إضافة إطار فيديو في PowerPoint"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint في Java من Aspose.Slides"
"title": "إضافة إطار فيديو في PowerPoint"
"url": "/ar/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إضافة إطار فيديو في PowerPoint

## مقدمة
في هذا البرنامج التعليمي، سنرشدك خلال عملية إضافة إطار فيديو إلى عرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. باتباع هذه التعليمات خطوة بخطوة، ستتمكن من دمج محتوى الفيديو بسلاسة في عروضك التقديمية بسهولة.
## المتطلبات الأساسية
قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- مجموعة تطوير Java (JDK) مثبتة على نظامك
- تم تنزيل Aspose.Slides لمكتبة Java وإعدادها في مشروع Java الخاص بك
## استيراد الحزم
أولاً، يتعين عليك استيراد الحزم اللازمة لاستخدام وظائف Aspose.Slides في كود Java الخاص بك. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## الخطوة 1: إعداد دليل المستندات
تأكد من إعداد دليل لتخزين ملفات PowerPoint الخاصة بك.
```java
String dataDir = "Your Document Directory";
```
## الخطوة 2: إنشاء كائن العرض التقديمي
إنشاء مثيل `Presentation` الفئة لتمثيل ملف PowerPoint.
```java
Presentation pres = new Presentation();
```
## الخطوة 3: إضافة إطار فيديو إلى الشريحة
احصل على الشريحة الأولى وأضف إطار فيديو إليها.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## الخطوة 4: ضبط وضع التشغيل ومستوى الصوت
ضبط وضع التشغيل ومستوى صوت إطار الفيديو.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## الخطوة 5: حفظ العرض التقديمي
احفظ ملف PowerPoint المعدّل على القرص.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية إضافة إطار فيديو إلى عرض تقديمي في PowerPoint باستخدام Aspose.Slides لجافا. حسّن عروضك التقديمية بإضافة عناصر وسائط متعددة لجذب جمهورك بفعالية.
## الأسئلة الشائعة
### هل يمكنني إضافة مقاطع فيديو بأي صيغة إلى عرض PowerPoint؟
يدعم Aspose.Slides تنسيقات فيديو متنوعة، مثل AVI وWMV وMP4 وغيرها. تأكد من توافق التنسيق مع PowerPoint.
### هل Aspose.Slides متوافق مع إصدارات Java المختلفة؟
نعم، Aspose.Slides for Java متوافق مع إصدارات JDK 6 وما فوق.
### كيف يمكنني تعديل حجم وموضع إطار الفيديو؟
يمكنك تخصيص أبعاد وإحداثيات إطار الفيديو عن طريق تعديل المعلمات في `addVideoFrame` طريقة.
### هل يمكنني التحكم في إعدادات تشغيل الفيديو؟
نعم، يمكنك ضبط وضع التشغيل وحجم إطار الفيديو وفقًا لتفضيلاتك.
### أين يمكنني العثور على مزيد من الدعم والموارد لـ Aspose.Slides؟
قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11) للحصول على المساعدة والتوثيق ودعم المجتمع.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}