---
title: จัดรูปแบบบรรทัดการนำเสนอด้วย Aspose.Slides .NET Tutorial
linktitle: การจัดรูปแบบเส้นในสไลด์การนำเสนอโดยใช้ Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: ปรับปรุงสไลด์การนำเสนอของคุณด้วย Aspose.Slides สำหรับ .NET ปฏิบัติตามคำแนะนำทีละขั้นตอนของเราเพื่อจัดรูปแบบบรรทัดได้อย่างง่ายดาย ดาวน์โหลดทดลองใช้ฟรีทันที!
weight: 10
url: /th/net/shape-geometry-and-positioning-in-slides/formatting-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# จัดรูปแบบบรรทัดการนำเสนอด้วย Aspose.Slides .NET Tutorial

## การแนะนำ
การสร้างสไลด์การนำเสนอที่ดึงดูดสายตาถือเป็นสิ่งสำคัญสำหรับการสื่อสารที่มีประสิทธิภาพ Aspose.Slides สำหรับ .NET มอบโซลูชันอันทรงพลังในการจัดการและจัดรูปแบบองค์ประกอบการนำเสนอโดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเน้นที่การจัดรูปแบบเส้นในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
-  Aspose.Slides สำหรับ .NET Library: ดาวน์โหลดและติดตั้งไลบรารีจาก[เอกสาร Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ด้วย Visual Studio หรือ IDE อื่น ๆ ที่เข้ากันได้
## นำเข้าเนมสเปซ
ในไฟล์โค้ด C# ของคุณ ให้รวมเนมสเปซที่จำเป็นสำหรับ Aspose.Slides เพื่อใช้ประโยชน์จากฟังก์ชันการทำงาน:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
สร้างโปรเจ็กต์ใหม่ในสภาพแวดล้อมการพัฒนาที่คุณต้องการ และเพิ่มการอ้างอิงไปยังไลบรารี Aspose.Slides
## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
```
## ขั้นตอนที่ 3: เข้าถึงสไลด์แรก
```csharp
ISlide sld = pres.Slides[0];
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างอัตโนมัติของสี่เหลี่ยมผืนผ้า
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 75);
```
## ขั้นตอนที่ 5: ตั้งค่าสีเติมสี่เหลี่ยมผืนผ้า
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.White;
```
## ขั้นตอนที่ 6: ใช้การจัดรูปแบบบนบรรทัด
```csharp
shp.LineFormat.Style = LineStyle.ThickThin;
shp.LineFormat.Width = 7;
shp.LineFormat.DashStyle = LineDashStyle.Dash;
```
## ขั้นตอนที่ 7: ตั้งค่าสีของเส้น
```csharp
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Blue;
```
## ขั้นตอนที่ 8: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "RectShpLn_out.pptx", SaveFormat.Pptx);
}
```
ตอนนี้ คุณได้จัดรูปแบบเส้นในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET เรียบร้อยแล้ว!
## บทสรุป
Aspose.Slides สำหรับ .NET ช่วยลดความยุ่งยากในการจัดการองค์ประกอบการนำเสนอโดยทางโปรแกรม ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถเพิ่มความดึงดูดสายตาให้กับสไลด์ของคุณได้อย่างง่ายดาย
## คำถามที่พบบ่อย
### คำถามที่ 1: ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
ใช่ Aspose.Slides รองรับภาษาการเขียนโปรแกรมที่หลากหลาย รวมถึง Java และ Python
### คำถามที่ 2: Aspose.Slides มีรุ่นทดลองใช้ฟรีหรือไม่
 ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จาก[Aspose.Slides ทดลองใช้ฟรี](https://releases.aspose.com/).
### คำถามที่ 3: ฉันจะรับการสนับสนุนเพิ่มเติมหรือถามคำถามได้ที่ไหน
 เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) เพื่อการสนับสนุนและช่วยเหลือชุมชน
### คำถามที่ 4: ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides ได้อย่างไร
 คุณสามารถรับใบอนุญาตชั่วคราวได้จาก[Aspose.Slides ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/).
### คำถามที่ 5: ฉันจะซื้อ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 ท่านสามารถซื้อสินค้าได้ที่[Aspose.Slides ซื้อ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
