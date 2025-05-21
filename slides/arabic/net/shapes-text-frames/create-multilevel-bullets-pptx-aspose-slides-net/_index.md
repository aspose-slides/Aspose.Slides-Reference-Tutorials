---
"date": "2025-04-16"
"description": "تعرف على كيفية إنشاء نقاط متعددة المستويات برمجيًا في عروض PowerPoint باستخدام Aspose.Slides لـ .NET، وهي مكتبة قوية لأتمتة مهام العرض التقديمي."
"title": "إنشاء نقاط متعددة المستويات في PowerPoint باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/shapes-text-frames/create-multilevel-bullets-pptx-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء نقاط متعددة المستويات في PowerPoint باستخدام Aspose.Slides لـ .NET

## مقدمة

هل ترغب في أتمتة إنشاء عروض تقديمية معقدة برمجيًا؟ مع Aspose.Slides لـ .NET، يمكنك بسهولة إنشاء ملفات PowerPoint تحتوي على نقاط متعددة المستويات. سيرشدك هذا الدليل خلال إنشاء المجلدات، وإدارة الشرائح، وإضافة الأشكال التلقائية مع إطارات النص، وتنسيق الفقرات باستخدام Aspose.Slides. بإتقان هذه المهارات، ستكون مؤهلًا لإنتاج عروض تقديمية احترافية برمجيًا.

**ما سوف تتعلمه:**
- كيفية التحقق من الدلائل وإنشائها في .NET
- إنشاء عرض تقديمي في PowerPoint من الصفر
- إضافة الأشكال التلقائية على الشرائح ومعالجتها
- تنسيق النص باستخدام نقاط متعددة المستويات
- حفظ ملف العرض التقديمي

دعنا نتعمق في إعداد البيئة الخاصة بك قبل أن نبدأ.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:
- تم تثبيت .NET Framework أو .NET Core على جهازك.
- المعرفة ببرمجة C# والمفاهيم الأساسية الموجهة للكائنات.
- Visual Studio أو أي IDE مفضل لتطوير .NET.

### المكتبات والتبعيات المطلوبة
لمتابعة هذا البرنامج التعليمي، سنحتاج إلى Aspose.Slides لـ .NET. تأكد من تثبيته في مشروعك:

## إعداد Aspose.Slides لـ .NET

Aspose.Slides مكتبة فعّالة تُمكّنك من العمل مع عروض PowerPoint التقديمية برمجيًا. إليك كيفية تثبيتها باستخدام مديري حزم مختلفين:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
ابحث عن "Aspose.Slides" في مدير الحزم NuGet وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص

يمكنك البدء بفترة تجريبية مجانية من Aspose.Slides أو طلب ترخيص مؤقت لاستكشاف كامل إمكانياته. للاستخدام الإنتاجي، فكّر في شراء ترخيص من [صفحة شراء Aspose](https://purchase.aspose.com/buy).

بمجرد التثبيت، دعنا نبدأ في تهيئة بيئتنا وإعدادها:

```csharp
using Aspose.Slides;
```

## دليل التنفيذ

### إنشاء وإدارة الدلائل

أولاً، علينا التأكد من وجود المجلد الذي سنحفظ فيه عرضنا التقديمي. إليك كيفية القيام بذلك:

**الخطوة 1: التحقق من وجود الدليل**

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // قم بتعيين مسار المستند الخاص بك هنا
bool isExists = Directory.Exists(dataDir);
if (!isExists)
{
    Directory.CreateDirectory(dataDir); // إنشاء الدليل إذا لم يكن موجودًا
}
```

**توضيح:** يتحقق هذا المقطع من وجود دليل محدد. إذا لم يكن موجودًا، فسيتم إنشاء دليل لتخزين ملفات العرض التقديمي.

### إنشاء عرض تقديمي باستخدام Aspose.Slides

الآن دعنا ننشئ عرض تقديمي جديد في PowerPoint وننتقل إلى الشريحة الأولى منه:

```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0]; // الوصول إلى الشريحة الأولى
}
```

**توضيح:** نحن نقوم بتهيئة `Presentation` كائن يُمثل ملف PPTX الخاص بنا. افتراضيًا، يتضمن شريحة واحدة.

### إضافة الشكل التلقائي إلى الشريحة

لإضافة محتوى، سنقوم بإدراج شكل تلقائي (مستطيل) وتكوين إطار النص الخاص به:

```csharp
IAutoShape aShp = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 200, 400, 200); // موضع وحجم المستطيل
ITextFrame text = aShp.AddTextFrame(""); // إنشاء إطار نص فارغ
text.Paragraphs.Clear(); // إزالة أي فقرة افتراضية
```

**توضيح:** يُضيف هذا المقطع شكلًا مستطيلًا إلى الشريحة. ثم نُهيئ إطار النص لإضافة محتوى مُرَكَّز.

### إدارة تنسيق الفقرات باستخدام النقاط

بعد ذلك، نقوم بتنسيق الفقرات بمستويات مختلفة من النقاط:

```csharp
// إضافة الفقرة الأولى
IParagraph para1 = new Paragraph();
para1.Text = "Content";
para1.ParagraphFormat.Bullet.Type = BulletType.Symbol;
para1.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
para1.ParagraphFormat.DefaultPortionFormat.FillFormat.FillType = FillType.Solid;
para1.ParagraphFormat.DefaultPortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
para1.ParagraphFormat.Depth = 0;

// إضافة فقرات لاحقة بأنواع ومستويات مختلفة من النقاط
IParagraph para2 = new Paragraph();
para2.Text = "Second Level";
para2.ParagraphFormat.Bullet.Type = BulletType.Symbol;
para2.ParagraphFormat.Bullet.Char = '-';
para2.ParagraphFormat.DefaultPortionFormat.FillFormat.FillType = FillType.Solid;
para2.ParagraphFormat.DefaultPortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
para2.ParagraphFormat.Depth = 1;

// كرر الأمر على نحو مماثل بالنسبة للفقرة 3 والفقرة 4 مع الأحرف والمستويات ذات الصلة
```

**توضيح:** يتم تكوين كل فقرة باستخدام أنماط نقطية محددة وألوان ومستويات المسافة البادئة لإنشاء التسلسل الهرمي.

وأخيرًا نضيف هذه الفقرات إلى إطار النص:

```csharp
text.Paragraphs.Add(para1);
text.Paragraphs.Add(para2);
// كرر للفقرة 3 والفقرة 4
```

### حفظ العرض التقديمي

الآن بعد أن أصبح عرضنا التقديمي جاهزًا، فلنحفظه كملف PPTX:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/MultilevelBullet.pptx", SaveFormat.Pptx); // حدد دليل الإخراج الخاص بك
```

**توضيح:** ال `Save` تكتب الطريقة العرض التقديمي على القرص بالتنسيق المحدد.

## التطبيقات العملية

فيما يلي بعض السيناريوهات الواقعية حيث يمكنك استخدام هذه الوظيفة:
1. **إنشاء التقارير التلقائية:** إنشاء تقارير شهرية أو ربع سنوية تلقائيًا مع ملخصات نقطية.
2. **أجندات الاجتماعات الديناميكية:** إنشاء وتوزيع جداول الأعمال بشكل ديناميكي استنادًا إلى مدخلات الاجتماع.
3. **وحدات التدريب:** تطوير مواد تدريبية متسقة تتطلب تحديثات وتنسيقًا متكررًا.

## اعتبارات الأداء

- تقليل استخدام الموارد عن طريق التخلص من الكائنات بشكل صحيح باستخدام `using` تصريحات.
- اختر هياكل البيانات الفعالة عند التعامل مع العروض التقديمية الكبيرة.
- قم بتحديث مكتبة Aspose.Slides الخاصة بك بانتظام للاستفادة من تحسينات الأداء.

## خاتمة

لقد نجحت في تعلّم كيفية إنشاء عرض تقديمي في PowerPoint بنقاط متعددة المستويات باستخدام Aspose.Slides لـ .NET. يمكنك الآن أتمتة إنشاء المستندات المعقدة، مما يوفر الوقت ويضمن الاتساق بين العروض التقديمية. لمزيد من الاستكشاف، فكّر في دمج Aspose.Slides في أنظمتك الحالية أو استكشاف ميزاته الإضافية.

## قسم الأسئلة الشائعة

**1. ما هو Aspose.Slides لـ .NET؟**
   - مكتبة شاملة لإنشاء ملفات PowerPoint ومعالجتها برمجيًا باستخدام .NET.

**2. كيف أقوم بتثبيت Aspose.Slides في مشروعي؟**
   - استخدم .NET CLI أو Package Manager Console أو NuGet Package Manager UI كما هو موضح سابقًا.

**3. هل يمكنني استخدام Aspose.Slides بدون ترخيص؟**
   - يمكنك البدء بفترة تجريبية مجانية لتقييم ميزاته.

**4. هل هناك قيود على عدد الشرائح التي يمكنني إنشاؤها؟**
   - لا توجد حدود جوهرية داخل Aspose.Slides، ولكن يجب أن تضع في اعتبارك استخدام الذاكرة في العروض التقديمية الكبيرة للغاية.

**5. كيف أقوم بتنسيق النص بشكل مختلف عبر فقرات متعددة؟**
   - يستخدم `ParagraphFormat` خصائص لتخصيص أنواع النقاط وألوان التعبئة ومستويات المسافة البادئة.

## موارد

- **التوثيق:** [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/)
- **تنزيل المكتبة:** [إصدارات Aspose.Slides](https://releases.aspose.com/slides/net/)
- **رخصة الشراء:** [شراء Aspose.Slides](https://purchase.aspose.com/buy)
- **نسخة تجريبية مجانية:** [نسخة تجريبية مجانية من Aspose.Slides](https://releases.aspose.com/slides/net/)
- **رخصة مؤقتة:** [طلب ترخيص مؤقت](https://purchase.aspose.com/temporary-license/)
- **منتدى الدعم:** [منتدى دعم Aspose](https://forum.aspose.com/c/slides/11)

هل أنت مستعد للارتقاء بعروضك التقديمية إلى مستوى أعلى؟ انضم إلى Aspose.Slides لـ .NET وابدأ بالإبداع اليوم!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}