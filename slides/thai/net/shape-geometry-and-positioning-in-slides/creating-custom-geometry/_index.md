---
"description": "เรียนรู้การสร้างรูปทรงเรขาคณิตแบบกำหนดเองใน Aspose.Slides สำหรับ .NET ยกระดับการนำเสนอของคุณด้วยรูปทรงที่ไม่ซ้ำใคร คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา C#"
"linktitle": "การสร้างรูปทรงเรขาคณิตแบบกำหนดเองในรูปทรงเรขาคณิตโดยใช้ Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การสร้างเรขาคณิตแบบกำหนดเองใน C# ด้วย Aspose.Slides สำหรับ .NET"
"url": "/th/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างเรขาคณิตแบบกำหนดเองใน C# ด้วย Aspose.Slides สำหรับ .NET

## การแนะนำ
ในโลกแห่งการนำเสนอที่เปลี่ยนแปลงตลอดเวลา การเพิ่มรูปทรงและเรขาคณิตที่ไม่ซ้ำใครสามารถยกระดับเนื้อหาของคุณ ทำให้ดึงดูดและดึงดูดสายตามากขึ้น Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการสร้างเรขาคณิตแบบกำหนดเองภายในรูปทรง ช่วยให้คุณหลีกหนีจากการออกแบบแบบเดิมๆ ได้ บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างเรขาคณิตแบบกำหนดเองใน GeometryShape โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนจะเริ่มบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- Aspose.Slides สำหรับไลบรารี .NET ติดตั้งอยู่ในสภาพแวดล้อมการพัฒนาของคุณ
- ตั้งค่า Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ ที่ต้องการ
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโครงการ C# ของคุณ:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่าได้ติดตั้ง Aspose.Slides สำหรับ .NET อย่างถูกต้อง
## ขั้นตอนที่ 2: กำหนดไดเรกทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 3: ตั้งค่ารัศมีดาวด้านนอกและด้านใน
```csharp
float R = 100, r = 50; // รัศมีดาวด้านนอกและด้านใน
```
## ขั้นตอนที่ 4: สร้างเส้นทางเรขาคณิตแบบดาว
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## ขั้นตอนที่ 5: สร้างงานนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // สร้างรูปร่างใหม่
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // ตั้งค่าเส้นทางเรขาคณิตใหม่ไปยังรูปร่าง
    shape.SetGeometryPath(starPath);
    // บันทึกการนำเสนอ
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## ขั้นตอนที่ 6: กำหนดวิธีการ CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## บทสรุป
ขอแสดงความยินดี! คุณได้เรียนรู้วิธีการสร้างรูปทรงเรขาคณิตแบบกำหนดเองใน GeometryShape โดยใช้ Aspose.Slides สำหรับ .NET สำเร็จแล้ว ซึ่งจะเปิดโอกาสให้คุณสร้างงานนำเสนอที่ไม่ซ้ำใครและสวยงามตระการตาได้
## คำถามที่พบบ่อย
### 1. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET ร่วมกับภาษาการเขียนโปรแกรมอื่น ๆ ได้หรือไม่
ใช่ Aspose.Slides รองรับภาษาการเขียนโปรแกรมต่างๆ แต่บทช่วยสอนนี้เน้นที่ C#
### 2. ฉันสามารถหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
เยี่ยมชม [เอกสารประกอบ](https://reference.aspose.com/slides/net/) เพื่อดูข้อมูลโดยละเอียด
### 3. มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Slides สำหรับ .NET หรือไม่
ใช่ คุณสามารถสำรวจได้ [ทดลองใช้งานฟรี](https://releases.aspose.com/) เพื่อสัมผัสคุณสมบัติต่างๆ
### 4. ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
ขอความช่วยเหลือและมีส่วนร่วมกับชุมชนที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### 5. ฉันสามารถซื้อ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
คุณสามารถซื้อ Aspose.Slides สำหรับ .NET ได้ [ที่นี่](https://purchase-aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}