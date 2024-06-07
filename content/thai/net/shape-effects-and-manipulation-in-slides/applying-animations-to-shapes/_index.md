---
title: สร้างภาพเคลื่อนไหวให้เป็นเรื่องง่ายด้วย Aspose.Slides
linktitle: การใช้ภาพเคลื่อนไหวกับรูปร่างในสไลด์การนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สร้างงานนำเสนอที่น่าทึ่งด้วย Aspose.Slides สำหรับ .NET เรียนรู้วิธีนำภาพเคลื่อนไหวไปใช้กับรูปร่างในคำแนะนำทีละขั้นตอนนี้ ยกระดับสไลด์ของคุณตอนนี้!
type: docs
weight: 21
url: /th/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---
## การแนะนำ
ในโลกของการนำเสนอแบบไดนามิก การเพิ่มภาพเคลื่อนไหวให้กับรูปร่างสามารถเพิ่มความน่าดึงดูดและการมีส่วนร่วมของสไลด์ของคุณได้อย่างมาก Aspose.Slides สำหรับ .NET มอบชุดเครื่องมืออันทรงพลังเพื่อให้บรรลุเป้าหมายนี้ได้อย่างราบรื่น ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการนำภาพเคลื่อนไหวไปใช้กับรูปร่างโดยใช้ Aspose.Slides ซึ่งช่วยให้คุณสร้างงานนำเสนอที่น่าหลงใหลและสร้างความประทับใจไม่รู้ลืมได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี่และพร้อมใช้งาน คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาที่คุณต้องการด้วยการกำหนดค่าที่จำเป็น
3. ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีเพื่อจัดเก็บไฟล์งานนำเสนอของคุณ
## นำเข้าเนมสเปซ
ในแอปพลิเคชัน .NET ของคุณ ให้เริ่มด้วยการนำเข้าเนมสเปซที่จำเป็น:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## ขั้นตอนที่ 1: สร้างงานนำเสนอ
 เริ่มต้นด้วยการสร้างงานนำเสนอใหม่โดยใช้`Presentation` ระดับ:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    //รหัสของคุณสำหรับการสร้างงานนำเสนออยู่ที่นี่
}
```
## ขั้นตอนที่ 2: เพิ่มรูปร่างเคลื่อนไหว
ตอนนี้ มาเพิ่มรูปร่างแบบเคลื่อนไหวให้กับสไลด์แรกของงานนำเสนอของคุณ:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## ขั้นตอนที่ 3: ใช้เอฟเฟกต์ภาพเคลื่อนไหว
เพิ่มเอฟเฟกต์ภาพเคลื่อนไหว 'PathFootball' ให้กับรูปร่างที่สร้างขึ้น:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## ขั้นตอนที่ 4: สร้างปุ่มทริกเกอร์
สร้างปุ่มที่จะเรียกภาพเคลื่อนไหว:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## ขั้นตอนที่ 5: กำหนดเส้นทางผู้ใช้ที่กำหนดเอง
กำหนดเส้นทางผู้ใช้ที่กำหนดเองสำหรับภาพเคลื่อนไหว:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// บันทึกงานนำเสนอเป็น PPTX ลงในดิสก์
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
คำแนะนำทีละขั้นตอนสำหรับการนำภาพเคลื่อนไหวไปใช้กับรูปร่างโดยใช้ Aspose.Slides สำหรับ .NET เสร็จสมบูรณ์
## บทสรุป
การรวมภาพเคลื่อนไหวเข้ากับการนำเสนอของคุณจะเพิ่มองค์ประกอบแบบไดนามิกที่ดึงดูดความสนใจของผู้ชม ด้วย Aspose.Slides คุณมีเครื่องมือที่มีประสิทธิภาพในการผสานรวมเอฟเฟกต์เหล่านี้ได้อย่างราบรื่น และยกระดับการนำเสนอของคุณไปอีกระดับ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ภาพเคลื่อนไหวหลายรายการกับรูปร่างเดียวได้หรือไม่
ใช่ Aspose.Slides ช่วยให้คุณสามารถเพิ่มเอฟเฟ็กต์แอนิเมชันหลายรายการลงในรูปร่างเดียวได้ ซึ่งให้ความยืดหยุ่นในการสร้างแอนิเมชั่นที่ซับซ้อน
### Aspose.Slides เข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ หรือไม่
Aspose.Slides รับประกันความเข้ากันได้กับ PowerPoint เวอร์ชันต่างๆ ทำให้มั่นใจว่างานนำเสนอของคุณทำงานได้อย่างราบรื่นบนแพลตฟอร์มต่างๆ
### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Slides ได้ที่ไหน
 สำรวจ[เอกสารประกอบ](https://reference.aspose.com/slides/net/) และขอความช่วยเหลือในการ[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### ฉันต้องมีใบอนุญาตสำหรับ Aspose.Slides เพื่อใช้ไลบรารีหรือไม่
 ใช่ คุณสามารถได้รับใบอนุญาต[ที่นี่](https://purchase.aspose.com/buy) เพื่อปลดล็อกศักยภาพสูงสุดของ Aspose.Slides
### ฉันสามารถลองใช้ Aspose.Slides ก่อนซื้อได้หรือไม่
 แน่นอน! ใช้[ทดลองฟรี](https://releases.aspose.com/) เพื่อสัมผัสความสามารถของ Aspose.Slides ก่อนตัดสินใจ