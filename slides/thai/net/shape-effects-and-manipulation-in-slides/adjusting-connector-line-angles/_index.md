---
title: ปรับมุมของเส้นเชื่อมต่อใน PowerPoint ด้วย Aspose.Slides
linktitle: การปรับมุมของเส้นเชื่อมต่อในสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับมุมของเส้นเชื่อมต่อในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณด้วยความแม่นยำและง่ายดาย
weight: 28
url: /th/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## การแนะนำ
การสร้างสไลด์การนำเสนอที่ดึงดูดสายตามักจะเกี่ยวข้องกับการปรับเส้นเชื่อมต่ออย่างแม่นยำ ในบทช่วยสอนนี้ เราจะสำรวจวิธีปรับมุมของเส้นเชื่อมต่อในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม โดยให้ความสามารถที่ครอบคลุมในการสร้าง ปรับเปลี่ยน และจัดการงานนำเสนอ
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- ติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ
-  Aspose.Slides สำหรับไลบรารี .NET คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).
- ไฟล์งานนำเสนอ PowerPoint ที่มีเส้นตัวเชื่อมต่อที่คุณต้องการปรับเปลี่ยน
## นำเข้าเนมสเปซ
ในการเริ่มต้น ตรวจสอบให้แน่ใจว่าได้รวมเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโครงการ C# ใหม่ใน Visual Studio และติดตั้งแพ็คเกจ Aspose.Slides NuGet ตั้งค่าโครงสร้างโปรเจ็กต์โดยอ้างอิงถึงไลบรารี Aspose.Slides
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 โหลดไฟล์งานนำเสนอ PowerPoint ของคุณลงในไฟล์`Presentation`วัตถุ. แทนที่ "Your Document Directory" ด้วยเส้นทางจริงไปยังไฟล์ของคุณ
## ขั้นตอนที่ 3: เข้าถึงสไลด์และรูปร่าง
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
เข้าถึงสไลด์แรกในงานนำเสนอและเริ่มต้นตัวแปรเพื่อแสดงรูปร่างบนสไลด์
## ขั้นตอนที่ 4: วนซ้ำผ่านรูปร่าง
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // รหัสสำหรับการจัดการสายเชื่อมต่อ
}
```
วนซ้ำแต่ละรูปร่างบนสไลด์เพื่อระบุและประมวลผลเส้นเชื่อมต่อ
## ขั้นตอนที่ 5: ปรับมุมของเส้นเชื่อมต่อ
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // รหัสสำหรับการจัดการรูปร่างอัตโนมัติ
}
else if (shape is Connector)
{
    // รหัสสำหรับการจัดการตัวเชื่อมต่อ
}
Console.WriteLine(dir);
```
 ระบุว่ารูปร่างนั้นเป็นรูปร่างอัตโนมัติหรือตัวเชื่อมต่อ และปรับมุมของเส้นตัวเชื่อมต่อโดยใช้สิ่งที่ให้มา`getDirection` วิธี.
##  ขั้นตอนที่ 6: กำหนด`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // รหัสสำหรับการคำนวณทิศทาง
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 ดำเนินการ`getDirection` วิธีการคำนวณมุมของเส้นเชื่อมต่อตามขนาดและการวางแนว
## บทสรุป
ด้วยขั้นตอนเหล่านี้ คุณสามารถปรับมุมของเส้นเชื่อมต่อในงานนำเสนอ PowerPoint ของคุณโดยใช้โปรแกรม Aspose.Slides สำหรับ .NET บทช่วยสอนนี้เป็นพื้นฐานในการปรับปรุงรูปลักษณ์ของสไลด์ของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides เหมาะสำหรับทั้ง Windows และเว็บแอปพลิเคชันหรือไม่
ใช่ Aspose.Slides สามารถใช้ได้ทั้งใน Windows และเว็บแอปพลิเคชัน
### ฉันสามารถดาวน์โหลด Aspose.Slides รุ่นทดลองใช้ฟรีก่อนซื้อได้หรือไม่
 ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะหาเอกสารที่ครอบคลุมสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 เอกสารก็มีให้[ที่นี่](https://reference.aspose.com/slides/net/).
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/).
### มีฟอรัมสนับสนุนสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณสามารถไปที่ฟอรั่มการสนับสนุนได้[ที่นี่](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
