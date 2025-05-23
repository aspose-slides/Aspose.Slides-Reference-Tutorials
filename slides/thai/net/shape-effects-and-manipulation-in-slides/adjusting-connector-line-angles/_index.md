---
"description": "เรียนรู้วิธีปรับมุมของเส้นเชื่อมต่อในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณด้วยความแม่นยำและง่ายดาย"
"linktitle": "การปรับมุมของเส้นเชื่อมต่อในสไลด์การนำเสนอโดยใช้ Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ปรับมุมของเส้นเชื่อมต่อใน PowerPoint ด้วย Aspose.Slides"
"url": "/th/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ปรับมุมของเส้นเชื่อมต่อใน PowerPoint ด้วย Aspose.Slides

## การแนะนำ
การสร้างสไลด์นำเสนอที่น่าสนใจมักเกี่ยวข้องกับการปรับแต่งเส้นเชื่อมต่ออย่างแม่นยำ ในบทช่วยสอนนี้ เราจะสำรวจวิธีการปรับมุมเส้นเชื่อมต่อในสไลด์นำเสนอโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้ผู้พัฒนาสามารถทำงานกับไฟล์ PowerPoint ได้ด้วยโปรแกรม ซึ่งให้ความสามารถมากมายสำหรับการสร้าง แก้ไข และจัดการงานนำเสนอ
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเริ่มลงลึกในบทช่วยสอน ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:
- ความรู้พื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C#
- มีการติดตั้ง Visual Studio หรือสภาพแวดล้อมการพัฒนา C# อื่น ๆ
- ไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้ [ที่นี่](https://releases-aspose.com/slides/net/).
- ไฟล์การนำเสนอ PowerPoint ที่มีเส้นเชื่อมต่อที่คุณต้องการปรับแต่ง
## นำเข้าเนมสเปซ
ในการเริ่มต้น โปรดแน่ใจว่าได้รวมเนมสเปซที่จำเป็นไว้ในโค้ด C# ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ C# ใหม่ใน Visual Studio และติดตั้งแพ็กเกจ Aspose.Slides NuGet ตั้งค่าโครงสร้างโปรเจ็กต์โดยอ้างอิงถึงไลบรารี Aspose.Slides
## ขั้นตอนที่ 2: โหลดงานนำเสนอ
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
โหลดไฟล์นำเสนอ PowerPoint ของคุณลงใน `Presentation` วัตถุ แทนที่ "ไดเรกทอรีเอกสารของคุณ" ด้วยเส้นทางจริงไปยังไฟล์ของคุณ
## ขั้นตอนที่ 3: เข้าถึงสไลด์และรูปทรง
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
เข้าถึงสไลด์แรกในการนำเสนอและเริ่มต้นตัวแปรเพื่อแสดงรูปร่างบนสไลด์
## ขั้นตอนที่ 4: ทำซ้ำผ่านรูปร่างต่างๆ
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // โค้ดสำหรับการจัดการสายเชื่อมต่อ
}
```
วนรอบแต่ละรูปร่างบนสไลด์เพื่อระบุและประมวลผลเส้นเชื่อมต่อ
## ขั้นตอนที่ 5: ปรับมุมของเส้นเชื่อมต่อ
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // โค้ดสำหรับการจัดการ AutoShapes
}
else if (shape is Connector)
{
    // โค้ดสำหรับการจัดการคอนเนคเตอร์
}
Console.WriteLine(dir);
```
ระบุว่ารูปร่างนั้นเป็น AutoShape หรือตัวเชื่อมต่อ และปรับมุมเส้นตัวเชื่อมต่อโดยใช้สิ่งที่ให้มา `getDirection` วิธี.
## ขั้นตอนที่ 6: กำหนด `getDirection` วิธี
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // โค้ดสำหรับการคำนวณทิศทาง
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
การดำเนินการตาม `getDirection` วิธีคำนวณมุมของเส้นเชื่อมต่อโดยพิจารณาจากขนาดและทิศทาง
## บทสรุป
ด้วยขั้นตอนเหล่านี้ คุณสามารถปรับมุมของเส้นเชื่อมต่อในงานนำเสนอ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET บทช่วยสอนนี้ให้พื้นฐานสำหรับการเพิ่มความน่าสนใจทางภาพของสไลด์ของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides เหมาะกับทั้งแอพพลิเคชัน Windows และเว็บหรือไม่
ใช่ Aspose.Slides สามารถใช้ได้ในทั้งแอพพลิเคชัน Windows และเว็บ
### ฉันสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีของ Aspose.Slides ก่อนซื้อได้หรือไม่
ใช่ คุณสามารถดาวน์โหลดรุ่นทดลองใช้งานฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันสามารถหาเอกสารประกอบโดยละเอียดเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้จากที่ใด
เอกสารประกอบมีให้ใช้งาน [ที่นี่](https://reference-aspose.com/slides/net/).
### ฉันจะขอใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
คุณสามารถรับใบอนุญาตชั่วคราวได้ [ที่นี่](https://purchase-aspose.com/temporary-license/).
### มีฟอรัมสนับสนุนสำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถเยี่ยมชมฟอรั่มสนับสนุนได้ [ที่นี่](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}