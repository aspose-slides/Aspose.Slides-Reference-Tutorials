---
title: การสร้างเรขาคณิตที่กำหนดเองใน C # ด้วย Aspose.Slides สำหรับ .NET
linktitle: การสร้างรูปทรงเรขาคณิตที่กำหนดเองในรูปทรงเรขาคณิตโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างเรขาคณิตที่กำหนดเองใน Aspose.Slides สำหรับ .NET ยกระดับการนำเสนอของคุณด้วยรูปทรงที่เป็นเอกลักษณ์ คำแนะนำทีละขั้นตอนสำหรับนักพัฒนา C#
weight: 15
url: /th/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
ในโลกการนำเสนอแบบไดนามิก การเพิ่มรูปทรงและรูปทรงเรขาคณิตที่เป็นเอกลักษณ์สามารถยกระดับเนื้อหาของคุณ ทำให้น่าสนใจและดึงดูดสายตามากขึ้น Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังสำหรับการสร้างรูปทรงเรขาคณิตแบบกำหนดเองภายในรูปร่าง ซึ่งช่วยให้คุณหลุดพ้นจากการออกแบบทั่วไป บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการสร้างเรขาคณิตแบบกำหนดเองใน GeometryShape โดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
- ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- Aspose.Slides สำหรับไลบรารี .NET ที่ติดตั้งในสภาพแวดล้อมการพัฒนาของคุณ
- Visual Studio หรือสภาพแวดล้อมการพัฒนา C# ที่ต้องการ
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ C# ของคุณ:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ C# ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ ตรวจสอบให้แน่ใจว่า Aspose.Slides สำหรับ .NET ได้รับการติดตั้งอย่างถูกต้อง
## ขั้นตอนที่ 2: กำหนดไดเร็กทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## ขั้นตอนที่ 3: ตั้งค่ารัศมีดาวด้านนอกและด้านใน
```csharp
float R = 100, r = 50; // รัศมีดาวชั้นนอกและชั้นใน
```
## ขั้นตอนที่ 4: สร้างเส้นทางเรขาคณิตของดาว
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## ขั้นตอนที่ 5: สร้างงานนำเสนอ
```csharp
using (Presentation pres = new Presentation())
{
    // สร้างรูปทรงใหม่
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // กำหนดเส้นทางเรขาคณิตใหม่ให้กับรูปร่าง
    shape.SetGeometryPath(starPath);
    // บันทึกการนำเสนอ
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## ขั้นตอนที่ 6: กำหนดวิธี CreateStarGeometry
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
ยินดีด้วย! คุณได้เรียนรู้วิธีสร้างรูปทรงเรขาคณิตที่กำหนดเองใน GeometryShape โดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว นี่เป็นการเปิดโลกแห่งความเป็นไปได้ในการสร้างสรรค์งานนำเสนอที่มีเอกลักษณ์และสวยงามตระการตา
## คำถามที่พบบ่อย
### 1. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
ใช่ Aspose.Slides รองรับภาษาการเขียนโปรแกรมที่หลากหลาย แต่บทช่วยสอนนี้เน้นที่ C#
### 2. ฉันจะหาเอกสารสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 เยี่ยมชม[เอกสารประกอบ](https://reference.aspose.com/slides/net/) สำหรับข้อมูลโดยละเอียด
### 3. Aspose.Slides สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถสำรวจได้[ทดลองฟรี](https://releases.aspose.com/) เพื่อสัมผัสประสบการณ์คุณสมบัติต่างๆ
### 4. ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร
 ขอความช่วยเหลือและมีส่วนร่วมกับชุมชนที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 คุณสามารถซื้อ Aspose.Slides สำหรับ .NET[ที่นี่](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
