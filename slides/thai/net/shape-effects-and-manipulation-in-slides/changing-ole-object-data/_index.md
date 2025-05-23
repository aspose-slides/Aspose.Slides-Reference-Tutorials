---
"description": "สำรวจพลังของ Aspose.Slides สำหรับ .NET ในการเปลี่ยนแปลงข้อมูลวัตถุ OLE ได้อย่างง่ายดาย เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยเนื้อหาแบบไดนามิก"
"linktitle": "การเปลี่ยนแปลงข้อมูลวัตถุ OLE ในการนำเสนอด้วย Aspose.Slides"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "การเปลี่ยนแปลงข้อมูลวัตถุ OLE ในการนำเสนอด้วย Aspose.Slides"
"url": "/th/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การเปลี่ยนแปลงข้อมูลวัตถุ OLE ในการนำเสนอด้วย Aspose.Slides

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint แบบไดนามิกและโต้ตอบได้เป็นข้อกำหนดทั่วไปในโลกดิจิทัลปัจจุบัน เครื่องมืออันทรงพลังอย่างหนึ่งในการบรรลุสิ่งนี้คือ Aspose.Slides สำหรับ .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถจัดการและปรับปรุงงานนำเสนอ PowerPoint ได้ด้วยโปรแกรม ในบทช่วยสอนนี้ เราจะเจาะลึกถึงกระบวนการเปลี่ยนแปลงข้อมูลวัตถุ OLE (Object Linking and Embedding) ภายในสไลด์งานนำเสนอโดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มทำงานกับ Aspose.Slides สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาโดยติดตั้ง .NET
2. ไลบรารี Aspose.Slides: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถค้นหาไลบรารีได้ [ที่นี่](https://releases-aspose.com/slides/net/).
3. ความเข้าใจพื้นฐาน: ทำความคุ้นเคยกับแนวคิดพื้นฐานของการเขียนโปรแกรม C# และการนำเสนอ PowerPoint
## นำเข้าเนมสเปซ
ในโครงการ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นสำหรับการใช้ฟังก์ชัน Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่และนำเข้าไลบรารี Aspose.Slides ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณได้รับการกำหนดค่าอย่างถูกต้อง และคุณมีการอ้างอิงที่จำเป็น
## ขั้นตอนที่ 2: เข้าถึงการนำเสนอและสไลด์
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## ขั้นตอนที่ 3: ค้นหาวัตถุ OLE
เดินไปตามรูปร่างทั้งหมดในสไลด์เพื่อค้นหาเฟรมวัตถุ OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## ขั้นตอนที่ 4: อ่านและแก้ไขข้อมูลสมุดงาน
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // การอ่านข้อมูลวัตถุในเวิร์กบุ๊ก
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // การแก้ไขข้อมูลสมุดงาน
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // การเปลี่ยนแปลงข้อมูลวัตถุ Ole frame
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## ขั้นตอนที่ 5: บันทึกการนำเสนอ
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## บทสรุป
หากทำตามขั้นตอนเหล่านี้ คุณจะสามารถเปลี่ยนแปลงข้อมูลวัตถุ OLE ภายในสไลด์การนำเสนอได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET ซึ่งจะเปิดโอกาสให้สร้างการนำเสนอแบบไดนามิกและปรับแต่งตามความต้องการเฉพาะของคุณได้
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET คืออะไร?
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับการนำเสนอ PowerPoint ผ่านโปรแกรม ช่วยให้ปรับเปลี่ยนและปรับปรุงได้อย่างง่ายดาย
### ฉันสามารถค้นหาเอกสาร Aspose.Slides ได้ที่ไหน
เอกสารประกอบสำหรับ Aspose.Slides สำหรับ .NET สามารถพบได้ [ที่นี่](https://reference-aspose.com/slides/net/).
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร?
คุณสามารถดาวน์โหลดไลบรารี่ได้จากหน้าเผยแพร่ [ที่นี่](https://releases-aspose.com/slides/net/).
### มีรุ่นทดลองใช้งานฟรีสำหรับ Aspose.Slides หรือไม่
ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้ [ที่นี่](https://releases-aspose.com/).
### ฉันจะได้รับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้จากที่ไหน
สำหรับการสนับสนุนและการหารือ โปรดไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}