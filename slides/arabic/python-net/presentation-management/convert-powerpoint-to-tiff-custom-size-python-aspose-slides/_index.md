---
"date": "2025-04-23"
"description": "تعرّف على كيفية تحويل عروض PowerPoint التقديمية إلى صور TIFF عالية الجودة باستخدام Python وAspose.Slides. خصّص الأبعاد، وحسّن الجودة، وأدر التعليقات."
"title": "تحويل PowerPoint إلى TIFF بأبعاد مخصصة في Python باستخدام Aspose.Slides"
"url": "/ar/python-net/presentation-management/convert-powerpoint-to-tiff-custom-size-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# تحويل عروض PowerPoint إلى TIFF بأبعاد مخصصة باستخدام Aspose.Slides لـ Python

يُعد تحويل عروض PowerPoint التقديمية إلى صور TIFF عالية الدقة أمرًا ضروريًا لأغراض المشاركة والأرشفة والطباعة. يرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Slides for Python لتحويل عروضك التقديمية إلى صيغة TIFF بأبعاد مخصصة. ستتعلم كيفية إدارة جودة الصورة، وإضافة ملاحظات وتعليقات على التصميم، وتحسين أداء التحويل.

## ما سوف تتعلمه:
- تثبيت وإعداد Aspose.Slides لـ Python
- تحويل شرائح PowerPoint إلى صور TIFF بأبعاد مخصصة
- تكوين الخيارات لإدراج الملاحظات والتعليقات
- تطبيق أفضل الممارسات لتحسين عملية التحويل الخاصة بك

دعونا نبدأ بمراجعة المتطلبات الأساسية!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

### المكتبات والتبعيات المطلوبة:
- **Aspose.Slides لـ Python**:تعتبر هذه المكتبة ضرورية للتعامل مع ملفات PowerPoint.
- **بيئة بايثون**:تأكد من التوافق مع Python 3.6 أو الإصدارات الأحدث.
- **مدير حزمة PIP**:تستخدم لتثبيت Aspose.Slides.

### متطلبات التثبيت:
- المعرفة الأساسية ببرمجة بايثون ومعالجة الملفات.
- بيئة تطوير تم إعدادها لتشغيل نصوص Python، مثل VSCode أو PyCharm.

## إعداد Aspose.Slides لـ Python

لتحويل عروض PowerPoint إلى تنسيق TIFF، قم أولاً بتثبيت مكتبة Aspose.Slides:

### تثبيت pip:
```bash
pip install aspose.slides
```

#### الحصول على الترخيص:
- **نسخة تجريبية مجانية**:ابدأ بتنزيل نسخة تجريبية مجانية من [صفحة إصدار Aspose](https://releases.aspose.com/slides/python-net/).
- **رخصة مؤقتة**:تقدم بطلب للحصول على ترخيص ممتد لفتح المزيد من الميزات [هنا](https://purchase.aspose.com/temporary-license/).
- **شراء**:لفتح الإمكانيات الكاملة، فكر في شراء اشتراك في [موقع شراء Aspose](https://purchase.aspose.com/buy).

#### التهيئة الأساسية:
بمجرد التثبيت، يمكنك تهيئة Aspose.Slides بالإعداد التالي:
```python
import aspose.slides as slides

# مثال على تهيئة وتحميل ملف عرض تقديمي مع slides.Presentation("path/to/presentation.pptx") كعرض تقديمي:
    print("Presentation loaded successfully!")
```

## دليل التنفيذ

الآن، دعنا نستكشف تحويل عروض PowerPoint إلى صور TIFF ذات أبعاد مخصصة.

### تحويل عرض PowerPoint إلى TIFF بأبعاد مخصصة

يتناول هذا القسم تنفيذ تحويل العرض التقديمي إلى صورة TIFF مع تحديد الأبعاد ونوع الضغط.

#### تحميل العرض التقديمي الخاص بك
ابدأ بتحميل ملف PowerPoint الخاص بك باستخدام Aspose.Slides:
```python
import aspose.slides as slides

def convert_to_tiff_custom_size():
    # حدد مسار دليل المستند الخاص بك
    with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/welcome-to-powerpoint.pptx") as pres:
        # تهيئة TiffOptions لإعدادات التحويل
```

#### تكوين خيارات TIFF
قم بتعيين نوع الضغط وخيارات التخطيط وDPI وحجم الصورة المخصص:
```python
tiff_options = slides.export.TiffOptions()
        
        # تعيين نوع ضغط LZW الافتراضي
        tiff_options.compression_type = slides.export.TiffCompressionTypes.DEFAULT
        
        # تكوين تخطيط الملاحظات والتعليقات
        slides_layout_options = slides.export.NotesCommentsLayoutingOptions()
        slides_layout_options.notes_position = slides.export.NotesPositions.BOTTOM_FULL
        tiff_options.slides_layout_options = slides_layout_options
        
        # تحديد DPI مخصص لجودة الصورة
        tiff_options.dpi_x = 200
        tiff_options.dpi_y = 100
        
        # تعيين حجم الإخراج المطلوب لصور TIFF
        tiff_options.image_size = drawing.Size(1728, 1078)
```

#### حفظ ملف TIFF المُحوّل
وأخيرًا، احفظ العرض التقديمي الخاص بك كملف TIFF:
```python
        # حدد دليل الإخراج واسم الملف
        pres.save("YOUR_OUTPUT_DIRECTORY/convert_to_tiff_custom_size_out.tiff\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}