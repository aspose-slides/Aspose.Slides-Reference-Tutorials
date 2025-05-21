---
"date": "2025-04-16"
"description": "تعرّف على كيفية إنشاء صور من شرائح PowerPoint وتغيير حجمها بدقة باستخدام Aspose.Slides .NET. مثالي للصور المصغرة، والمواد المطبوعة، أو لدمج الأنظمة."
"title": "كيفية إنشاء صور PowerPoint وتغيير حجمها باستخدام Aspose.Slides .NET"
"url": "/ar/net/images-multimedia/create-scale-powerpoint-images-aspose-slides-dot-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء صور PowerPoint وتغيير حجمها باستخدام Aspose.Slides .NET

**مقدمة**

هل تحتاج إلى تحويل شرائح PowerPoint إلى صور مع الحفاظ على أبعاد محددة؟ توفر مكتبة Aspose.Slides .NET القوية حلاً مثاليًا. سواء كنت تُنشئ صورًا مصغرة، أو تُنشئ مواد جاهزة للطباعة، أو تُدمجها مع أنظمة أخرى، فإن تغيير حجم صور الشرائح وتحويلها أمر بالغ الأهمية. سيرشدك هذا البرنامج التعليمي خلال إنشاء الصور وتغيير حجمها من شريحة PowerPoint باستخدام Aspose.Slides .NET.

**ما سوف تتعلمه:**
- إعداد البيئة الخاصة بك لـ Aspose.Slides .NET.
- خطوات إنشاء الصور وتغيير حجمها من الشرائح.
- طرق حفظ هذه الصور بالصيغة التي تريدها.
- التطبيقات العملية لهذه الميزة.
- نصائح لتحسين الأداء مع Aspose.Slides .NET.

**المتطلبات الأساسية**

قبل البدء، تأكد من إعداد كل شيء بشكل صحيح:

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides لـ .NET**:المكتبة الأساسية لمعالجة ملفات PowerPoint. تأكد من تثبيت الإصدار 22.10 أو أحدث.
  

### متطلبات إعداد البيئة
- **بيئة التطوير**:استخدم بيئة تطوير .NET مثل Visual Studio (2019 أو أحدث).

### متطلبات المعرفة
- فهم أساسي لبرمجة C# والتعرف على أطر عمل .NET.
- إن التعرف على بيئات سطر الأوامر لإدارة الحزم أمر مفيد.

**إعداد Aspose.Slides لـ .NET**

لنبدأ بتثبيت Aspose.Slides لمشروع .NET الخاص بك:

### تثبيت

اختر إحدى هذه الطرق لتثبيت Aspose.Slides:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
- افتح الحل الخاص بك في Visual Studio.
- انتقل إلى **إدارة حزم NuGet** لمشروعك.
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص
لاستكشاف كافة الميزات دون قيود، فكر في الحصول على ترخيص:
- **نسخة تجريبية مجانية**:تحميل من [إصدارات Aspose](https://releases.aspose.com/slides/net/).
- **رخصة مؤقتة**:تقدم بطلب للحصول على [صفحة الشراء](https://purchase.aspose.com/temporary-license/) للتقييم.
- **شراء كامل**:للاستخدام طويل الأمد، قم بالشراء من خلال [بوابة شراء Aspose](https://purchase.aspose.com/buy).

### التهيئة والإعداد الأساسي

بمجرد التثبيت، قم بتشغيل Aspose.Slides في مشروعك:
```csharp
using Aspose.Slides;
```

بعد اكتمال الإعداد، دعنا ننفذ ميزتنا.

**دليل التنفيذ**

في هذا القسم، سنقوم بإنشاء صورة وتغيير حجمها من شريحة PowerPoint باستخدام الأبعاد التي يحددها المستخدم.

### ملخص
تتيح لك هذه الميزة إنشاء صور لشرائح العرض التقديمي بأحجام مخصصة، وهو أمر ضروري لأغراض العرض أو تكامل التطبيقات.

#### الخطوة 1: تحميل العرض التقديمي الخاص بك
قم بتحميل ملف العرض التقديمي الخاص بك:
```csharp
using System.IO;
using Aspose.Slides;

namespace Aspose.Slides.Examples.CSharp.Slides.Thumbnail
{
    public class ThumbnailWithUserDefinedDimensions
    {
        public static void Run()
        {
            string dataDir = "YOUR_DOCUMENT_DIRECTORY";
            
            using (Presentation pres = new Presentation(Path.Combine(dataDir, "ThumbnailWithUserDefinedDimensions.pptx")))
            {
                // وسوف تتبع الخطوات التالية هنا...
```

#### الخطوة 2: الوصول إلى الشريحة المطلوبة
قم بالوصول إلى الشريحة التي ترغب في تحويلها:
```csharp
// الوصول إلى الشريحة الأولى
ISlide sld = pres.Slides[0];
```

#### الخطوة 3: تحديد الأبعاد وحساب عوامل القياس
قم بتعيين أبعاد الصورة المطلوبة، ثم احسب عوامل المقياس:
```csharp
int desiredX = 1200;
int desiredY = 800;

float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

#### الخطوة 4: إنشاء الصورة المصغرة وحفظها
قم بإنشاء الصورة من الشريحة الخاصة بك باستخدام عوامل القياس:
```csharp
IImage img = sld.GetThumbnail(ScaleX, ScaleY);

string outputDir = "YOUR_OUTPUT_DIRECTORY";
Directory.CreateDirectory(outputDir); // تأكد من وجود الدليل
img.Save(Path.Combine(outputDir, "Thumbnail2_out.jpg"), System.Drawing.Imaging.ImageFormat.Jpeg);
```

### خيارات تكوين المفاتيح
- **تنسيق الصورة**:احفظ الصور بتنسيقات مختلفة مثل JPEG أو PNG أو BMP عن طريق تغيير `ImageFormat`.
- **إدارة الدليل**:تأكد من وجود دليل الإخراج لتجنب الأخطاء.

**التطبيقات العملية**
1. **إنشاء الصور المصغرة**:إنشاء صور مصغرة لمعاينات الشرائح على تطبيقات الويب أو أنظمة إدارة المحتوى.
2. **صور جاهزة للطباعة**:إنشاء صور بأبعاد مخصصة مناسبة لمواد الطباعة مثل الكتيبات.
3. **تكامل المحتوى**:دمج صور الشرائح في التقارير أو لوحات المعلومات ضمن أدوات الاستخبارات التجارية.

**اعتبارات الأداء**
يعد تحسين الأداء أمرًا بالغ الأهمية، خاصة في البيئات كثيفة الموارد:
- **إدارة الذاكرة**:التخلص من `Presentation` الأشياء لتحرير الذاكرة على الفور.
- **معالجة الصور بكفاءة**:معالجة الصور دفعة واحدة وتجنب عمليات التدرج غير الضرورية.

**خاتمة**

لقد شرحنا كيفية إنشاء صور الشرائح وتعديل حجمها باستخدام Aspose.Slides .NET، وهو أمر أساسي لمهام مثل إنشاء الصور المصغرة أو إعداد محتوى جاهز للطباعة. استكشف المزيد من الميزات مثل انتقالات الشرائح أو الرسوم المتحركة باستخدام Aspose.Slides. للاستفسارات، انضم إلى [منتدى أسبوزي](https://forum.aspose.com/c/slides/11).

**قسم الأسئلة الشائعة**
1. **كيف يمكنني حفظ الصور بتنسيقات غير JPEG؟**
   - يتغير `ImageFormat.Jpeg` إلى التنسيق المطلوب مثل `ImageFormat.Png`.
2. **ماذا لو لم يكن دليل الإخراج موجودًا؟**
   - تأكد من إنشائه باستخدام `Directory.CreateDirectory(outputDir);` قبل حفظ الصورة.
3. **هل يمكنني تغيير حجم كافة الشرائح في العرض التقديمي مرة واحدة؟**
   - نعم، قم بالمرور على كل شريحة وتطبيق المنطق المماثل بشكل فردي.
4. **كيف يمكنني التعامل مع العروض التقديمية الكبيرة دون مشاكل في الأداء؟**
   - قم بمعالجة الشرائح واحدة تلو الأخرى والتخلص من الكائنات على الفور.
5. **أين يمكنني العثور على المزيد من الوثائق التفصيلية حول ميزات Aspose.Slides؟**
   - استكشف [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) للإرشاد.

**موارد**
- [التوثيق](https://reference.aspose.com/slides/net/)
- [تنزيل Aspose.Slides](https://releases.aspose.com/slides/net/)
- [شراء ترخيص](https://purchase.aspose.com/buy)
- [نسخة تجريبية مجانية](https://releases.aspose.com/slides/net/)
- [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- [منتدى الدعم](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}