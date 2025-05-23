---
"description": "تعرّف على كيفية إضافة روابط ماكرو في عروضك التقديمية باستخدام Aspose.Slides لـ .NET. حسّن التفاعلية وتفاعل مع جمهورك."
"linktitle": "إدارة الارتباط التشعبي باستخدام وحدات الماكرو"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "كيفية تعيين نقرة ارتباط تشعبي للماكرو في Aspose.Slides لـ .NET"
"url": "/ar/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# كيفية تعيين نقرة ارتباط تشعبي للماكرو في Aspose.Slides لـ .NET


في عالم تطوير البرمجيات الحديث، يُعد إنشاء عروض تقديمية ديناميكية وتفاعلية جانبًا أساسيًا. Aspose.Slides for .NET مكتبة فعّالة تتيح لك العمل مع العروض التقديمية بسلاسة. سواء كنت تُنشئ عرضًا تقديميًا تجاريًا أو عرض شرائح تعليميًا، فإن إمكانية ضبط نقرات روابط الماكرو تُحسّن تجربة المستخدم بشكل كبير. في هذا الدليل المُفصّل، سنشرح لك عملية ضبط نقرات روابط الماكرو باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نتعمق في البرنامج التعليمي خطوة بخطوة، هناك بعض المتطلبات الأساسية التي يجب أن تكون موجودة لديك:

1. Visual Studio: تأكد من تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك، حيث ستكون هذه بيئة التطوير الخاصة بنا.

2. Aspose.Slides لـ .NET: ستحتاج إلى تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

3. المعرفة الأساسية بلغة C#: المعرفة بلغة البرمجة C# ضرورية لمتابعة هذا البرنامج التعليمي.

## استيراد مساحات الأسماء

في الخطوة الأولى، دعنا نستورد مساحات الأسماء الضرورية للعمل مع Aspose.Slides:

### الخطوة 1: استيراد مساحات الأسماء

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

لقد قمنا باستيراد `Aspose.Slides` مساحة الاسم، وهي مساحة الاسم الأساسية للعمل مع العروض التقديمية، و `Aspose.Slides.Export` مساحة الاسم.

## إعداد النقر على رابط الماكرو التشعبي

الآن، دعنا ننتقل إلى الجزء الرئيسي من هذا البرنامج التعليمي - إعداد نقرة ارتباط تشعبي في العرض التقديمي الخاص بك.

### الخطوة 2: تهيئة العرض التقديمي

أولاً، نحتاج إلى تهيئة عرض تقديمي جديد.

```csharp
using (Presentation presentation = new Presentation())
{
    // سيتم وضع الكود الخاص بك هنا.
}
```

في بيان الاستخدام هذا، يمكنك إنشاء كائن عرض تقديمي جديد وتنفيذ جميع العمليات بداخله.

### الخطوة 3: إضافة شكل تلقائي

لتعيين نقرة على رابط ماكرو، ستحتاج إلى كائن يمكن للمستخدم النقر عليه. في هذا المثال، سنستخدم شكلاً تلقائياً كعنصر قابل للنقر.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

هنا، نُنشئ شكلاً تلقائيًا من نوع "BlankButton" بإحداثيات محددة (20، 20) وأبعاد 80×30. يمكنك تخصيص هذه القيم لتناسب تصميم عرضك التقديمي.

### الخطوة 4: تعيين نقرة الارتباط التشعبي للماكرو

الآن يأتي دور ضبط نقرة رابط الماكرو. ستحتاج إلى إدخال اسم الماكرو كمعامل.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

في هذا المثال، عيّننا نقرة رابط الماكرو إلى "TestMacro". عند نقر المستخدم على الشكل التلقائي، سيتم تشغيل هذا الماكرو.

### الخطوة 5: استرجاع المعلومات

يمكنك أيضًا استرداد المعلومات حول الارتباط التشعبي الذي قمت بتعيينه.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

تسمح لك أسطر التعليمات البرمجية هذه بطباعة عنوان URL الخارجي ونوع الإجراء الخاص بالارتباط التشعبي.

وهذا كل شيء! لقد نجحت في ضبط نقرة رابط الماكرو في عرضك التقديمي باستخدام Aspose.Slides لـ .NET.

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية ضبط نقرة رابط ماكرو في عرضك التقديمي باستخدام Aspose.Slides لـ .NET. تُعد هذه ميزة قيّمة لإنشاء عروض تقديمية تفاعلية وديناميكية تجذب جمهورك. مع Aspose.Slides لـ .NET، لديك أداة فعّالة للارتقاء بتطوير عرضك التقديمي إلى مستوى أعلى.

الآن، حان وقت تجربة وإنشاء عروض تقديمية آسرة باستخدام روابط ماكرو مخصصة. لا تتردد في استكشاف [توثيق Aspose.Slides لـ .NET](https://reference.aspose.com/slides/net/) لمزيد من المعلومات والإمكانيات المتعمقة.

## الأسئلة الشائعة

### هل يمكنني استخدام Aspose.Slides لـ .NET مع لغات برمجة أخرى؟
تم تصميم Aspose.Slides في المقام الأول لـ .NET، ولكن Aspose تقدم مكتبات مماثلة للغات البرمجة الأخرى، مثل Java.

### هل Aspose.Slides لـ .NET مكتبة مجانية؟
Aspose.Slides for .NET هي مكتبة تجارية متوفرة بنسخة تجريبية مجانية. يمكنك تنزيلها من [هنا](https://releases.aspose.com/).

### هل هناك أي قيود على استخدام وحدات الماكرو في العروض التقديمية التي تم إنشاؤها باستخدام Aspose.Slides لـ .NET؟
يتيح لك Aspose.Slides for .NET العمل باستخدام وحدات الماكرو، ولكن يجب أن تكون على دراية باعتبارات الأمان والتوافق عند استخدام وحدات الماكرو في العروض التقديمية.

### هل يمكنني تخصيص مظهر الشكل التلقائي المستخدم للارتباط التشعبي؟
نعم، يمكنك تخصيص مظهر الشكل التلقائي عن طريق ضبط خصائصه، مثل الحجم واللون والخط.

### أين يمكنني الحصول على المساعدة أو الدعم لـ Aspose.Slides لـ .NET؟
إذا واجهت مشكلات أو كانت لديك أسئلة، فيمكنك طلب المساعدة في منتدى دعم Aspose [هنا](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}