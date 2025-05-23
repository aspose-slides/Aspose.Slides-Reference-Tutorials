---
"description": "เรียนรู้การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบแผนภูมิใน PowerPoint ด้วย Aspose.Slides สำหรับ .NET คำแนะนำทีละขั้นตอนสำหรับการนำเสนอที่น่าทึ่ง"
"linktitle": "การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่ในแผนภูมิ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "แอนิเมชั่นแผนภูมิอันทรงพลังด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/chart-formatting-and-animation/animating-categories-elements/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แอนิเมชั่นแผนภูมิอันทรงพลังด้วย Aspose.Slides สำหรับ .NET


ในโลกแห่งการนำเสนอ แอนิเมชั่นสามารถทำให้เนื้อหาของคุณมีชีวิตชีวาได้ โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับแผนภูมิ Aspose.Slides สำหรับ .NET นำเสนอฟีเจอร์อันทรงพลังมากมายที่ช่วยให้คุณสร้างแอนิเมชั่นอันน่าทึ่งสำหรับแผนภูมิของคุณได้ ในคู่มือทีละขั้นตอนนี้ เราจะแนะนำคุณเกี่ยวกับกระบวนการสร้างแอนิเมชั่นองค์ประกอบหมวดหมู่ในแผนภูมิโดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน คุณควรมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Slides สำหรับ .NET ไว้ในสภาพแวดล้อมการพัฒนาของคุณแล้ว หากคุณยังไม่ได้ติดตั้ง คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).

- งานนำเสนอที่มีอยู่: คุณควรมีงานนำเสนอ PowerPoint ที่มีแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว หากไม่มี ให้สร้างงานนำเสนอตัวอย่างที่มีแผนภูมิเพื่อวัตถุประสงค์ในการทดสอบ

ตอนนี้คุณเตรียมทุกอย่างลงตัวแล้ว มาเริ่มสร้างแอนิเมชั่นองค์ประกอบแผนภูมิกันเลย!

## นำเข้าเนมสเปซ

ขั้นตอนแรกคือการนำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานของ Aspose.Slides เพิ่มเนมสเปซต่อไปนี้ลงในโปรเจ็กต์ของคุณ:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```csharp
// เส้นทางไปยังไดเรกทอรีเอกสารของคุณ
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // รับการอ้างอิงของวัตถุแผนภูมิ
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

ในขั้นตอนนี้ เราจะโหลดงานนำเสนอ PowerPoint ที่มีอยู่ซึ่งมีแผนภูมิที่คุณต้องการสร้างภาพเคลื่อนไหว จากนั้นเราจะเข้าถึงวัตถุแผนภูมิภายในสไลด์แรก

## ขั้นตอนที่ 2: สร้างแอนิเมชั่นให้กับองค์ประกอบหมวดหมู่

```csharp
// สร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

ขั้นตอนนี้จะเพิ่มเอฟเฟ็กต์แอนิเมชัน "จางลง" ให้กับแผนภูมิทั้งหมด ทำให้ปรากฏหลังแอนิเมชันครั้งก่อน

ต่อไปเราจะเพิ่มแอนิเมชั่นให้กับองค์ประกอบแต่ละองค์ประกอบภายในแต่ละหมวดหมู่ของแผนภูมิ นี่คือจุดที่เวทมนตร์เกิดขึ้นจริง

## ขั้นตอนที่ 3: สร้างภาพเคลื่อนไหวให้กับองค์ประกอบแต่ละส่วน

เราจะแบ่งแอนิเมชั่นขององค์ประกอบแต่ละองค์ประกอบภายในแต่ละหมวดหมู่ออกเป็นขั้นตอนต่อไปนี้:

### ขั้นตอนที่ 3.1: การเคลื่อนไหวองค์ประกอบในหมวด 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

ที่นี่ เรากำลังสร้างภาพเคลื่อนไหวให้กับองค์ประกอบแต่ละองค์ประกอบภายในหมวด 0 ของแผนภูมิ โดยให้องค์ประกอบเหล่านั้นปรากฏขึ้นทีละองค์ประกอบ เอฟเฟกต์ "ปรากฏ" จะถูกใช้สำหรับภาพเคลื่อนไหวนี้

### ขั้นตอนที่ 3.2: การเคลื่อนไหวองค์ประกอบในหมวดที่ 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

กระบวนการนี้ทำซ้ำสำหรับหมวดที่ 1 โดยทำให้องค์ประกอบแต่ละองค์ประกอบเคลื่อนไหวโดยใช้เอฟเฟกต์ "ปรากฏ"

### ขั้นตอนที่ 3.3: การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบในหมวดที่ 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

กระบวนการเดียวกันนี้จะดำเนินต่อไปสำหรับหมวดที่ 2 โดยทำให้องค์ประกอบแต่ละส่วนเคลื่อนไหวทีละองค์ประกอบ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

```csharp
// เขียนไฟล์การนำเสนอลงดิสก์
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

ในขั้นตอนสุดท้าย เราจะบันทึกงานนำเสนอด้วยแอนิเมชั่นที่เพิ่มเข้ามาใหม่ ตอนนี้องค์ประกอบแผนภูมิของคุณจะเคลื่อนไหวอย่างสวยงามเมื่อคุณเปิดงานนำเสนอ

## บทสรุป

การสร้างภาพเคลื่อนไหวให้กับองค์ประกอบหมวดหมู่ในแผนภูมิสามารถเพิ่มความน่าสนใจให้กับงานนำเสนอของคุณได้ ด้วย Aspose.Slides สำหรับ .NET กระบวนการนี้จะง่ายขึ้นและมีประสิทธิภาพมากขึ้น คุณได้เรียนรู้วิธีการนำเข้าเนมสเปซ โหลดงานนำเสนอ และเพิ่มภาพเคลื่อนไหวให้กับทั้งแผนภูมิและองค์ประกอบแต่ละองค์ประกอบแล้ว ใช้ความคิดสร้างสรรค์และทำให้การนำเสนอของคุณน่าสนใจยิ่งขึ้นด้วย Aspose.Slides สำหรับ .NET

## คำถามที่พบบ่อย

### 1. ฉันสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร
คุณสามารถดาวน์โหลด Aspose.Slides สำหรับ .NET ได้จาก [ลิงค์นี้](https://releases-aspose.com/slides/net/).

### 2. ฉันจำเป็นต้องมีประสบการณ์การเขียนโค้ดเพื่อใช้ Aspose.Slides สำหรับ .NET หรือไม่?
แม้ว่าประสบการณ์การเขียนโค้ดจะมีประโยชน์ แต่ Aspose.Slides สำหรับ .NET มีเอกสารและตัวอย่างมากมายเพื่อช่วยเหลือผู้ใช้ในทุกระดับทักษะ

### 3. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับ PowerPoint ทุกเวอร์ชันได้หรือไม่
Aspose.Slides สำหรับ .NET ได้รับการออกแบบมาให้ทำงานกับ PowerPoint เวอร์ชันต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้

### 4. ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
คุณสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).

### 5. มีฟอรัมชุมชนสำหรับการรองรับ Aspose.Slides สำหรับการ .NET หรือไม่
ใช่ คุณสามารถค้นหาฟอรัมชุมชนที่ให้การสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ [ที่นี่](https://forum-aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}