---
title: การเพิ่ม OLE Object Frames ให้กับการนำเสนอด้วย Aspose.Slides
linktitle: การเพิ่ม OLE Object Frames ให้กับการนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ด้วยเนื้อหาแบบไดนามิก! ทำตามคำแนะนำทีละขั้นตอนของเราโดยใช้ Aspose.Slides สำหรับ .NET เพิ่มการมีส่วนร่วมทันที!
weight: 15
url: /th/net/shape-effects-and-manipulation-in-slides/adding-ole-object-frames/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่ม OLE Object Frames ให้กับการนำเสนอด้วย Aspose.Slides

## การแนะนำ
ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเพิ่มเฟรมออบเจ็กต์ OLE (การเชื่อมโยงและการฝังวัตถุ) ลงในสไลด์การนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET Aspose.Slides เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับไฟล์ PowerPoint โดยทางโปรแกรม ทำตามคำแนะนำทีละขั้นตอนนี้เพื่อฝังวัตถุ OLE ลงในสไลด์การนำเสนอของคุณได้อย่างราบรื่น เพิ่มประสิทธิภาพไฟล์ PowerPoint ของคุณด้วยเนื้อหาแบบไดนามิกและโต้ตอบได้
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Slides สำหรับ .NET Library: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/).
2. ไดเร็กทอรีเอกสาร: สร้างไดเร็กทอรีบนระบบของคุณเพื่อจัดเก็บไฟล์ที่จำเป็น คุณสามารถกำหนดเส้นทางไปยังไดเร็กทอรีนี้ได้ในข้อมูลโค้ดที่ให้ไว้
## นำเข้าเนมสเปซ
ในการเริ่มต้น ให้นำเข้าเนมสเปซที่จำเป็นลงในโปรเจ็กต์ของคุณ:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using Aspose.Slides.Export;
```
## ขั้นตอนที่ 1: ตั้งค่าการนำเสนอ
```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึง PPTX
using (Presentation pres = new Presentation())
{
    // เข้าถึงสไลด์แรก
    ISlide sld = pres.Slides[0];
    
    // ทำตามขั้นตอนต่อไป...
}
```
## ขั้นตอนที่ 2: โหลดวัตถุ OLE (ไฟล์ Excel) เพื่อสตรีม
```csharp
// โหลดไฟล์ Excel เพื่อสตรีม
MemoryStream mstream = new MemoryStream();
using (FileStream fs = new FileStream(dataDir + "book1.xlsx", FileMode.Open, FileAccess.Read))
{
    byte[] buf = new byte[4096];
    while (true)
    {
        int bytesRead = fs.Read(buf, 0, buf.Length);
        if (bytesRead <= 0)
            break;
        mstream.Write(buf, 0, bytesRead);
    }
}
```
## ขั้นตอนที่ 3: สร้างวัตถุข้อมูลสำหรับการฝัง
```csharp
// สร้างวัตถุข้อมูลสำหรับการฝัง
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.ToArray(), "xlsx");
```
## ขั้นตอนที่ 4: เพิ่มรูปร่างกรอบวัตถุ OLE
```csharp
//เพิ่มรูปร่าง OLE Object Frame
IOleObjectFrame oleObjectFrame = sld.Shapes.AddOleObjectFrame(0, 0, pres.SlideSize.Size.Width,
    pres.SlideSize.Size.Height, dataInfo);
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
// เขียน PPTX ลงในดิสก์
pres.Save(dataDir + "OleEmbed_out.pptx", SaveFormat.Pptx);
```
ตอนนี้คุณได้เพิ่ม OLE Object Frame ลงในสไลด์การนำเสนอของคุณเรียบร้อยแล้วโดยใช้ Aspose.Slides สำหรับ .NET
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจการรวม OLE Object Frames เข้ากับสไลด์ PowerPoint อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET ฟังก์ชันนี้ช่วยปรับปรุงการนำเสนอของคุณโดยอนุญาตให้ฝังวัตถุต่างๆ แบบไดนามิก เช่น แผ่นงาน Excel เพื่อมอบประสบการณ์ผู้ใช้ที่มีการโต้ตอบมากขึ้น
## คำถามที่พบบ่อย
### ถาม: ฉันสามารถฝังวัตถุอื่นที่ไม่ใช่แผ่นงาน Excel โดยใช้ Aspose.Slides สำหรับ .NET ได้หรือไม่
ตอบ: ใช่ Aspose.Slides รองรับการฝังวัตถุ OLE ต่างๆ รวมถึงเอกสาร Word และไฟล์ PDF
### ถาม: ฉันจะจัดการกับข้อผิดพลาดระหว่างกระบวนการฝังวัตถุ OLE ได้อย่างไร
ตอบ: ตรวจสอบให้แน่ใจว่ามีการจัดการข้อยกเว้นที่เหมาะสมในโค้ดของคุณเพื่อแก้ไขปัญหาใดๆ ที่อาจเกิดขึ้นระหว่างขั้นตอนการฝัง
### ถาม: Aspose.Slides เข้ากันได้กับรูปแบบไฟล์ PowerPoint ล่าสุดหรือไม่
ตอบ: ใช่ Aspose.Slides รองรับรูปแบบไฟล์ PowerPoint ล่าสุด รวมถึง PPTX
### ถาม: ฉันสามารถปรับแต่งลักษณะที่ปรากฏของ OLE Object Frame ที่ฝังไว้ได้หรือไม่
ตอบ: แน่นอน คุณสามารถปรับขนาด ตำแหน่ง และคุณสมบัติอื่นๆ ของ OLE Object Frame ได้ตามความต้องการของคุณ
### ถาม: ฉันจะขอความช่วยเหลือได้ที่ไหนหากฉันเผชิญกับความท้าทายระหว่างการดำเนินการ
 ตอบ: เยี่ยมชม[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11) สำหรับการสนับสนุนและคำแนะนำจากชุมชน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
