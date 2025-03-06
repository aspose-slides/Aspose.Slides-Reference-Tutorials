---
title: การเปลี่ยนข้อมูลวัตถุ OLE ในการนำเสนอด้วย Aspose.Slides
linktitle: การเปลี่ยนข้อมูลวัตถุ OLE ในการนำเสนอด้วย Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: สำรวจพลังของ Aspose.Slides สำหรับ .NET ในการเปลี่ยนแปลงข้อมูลอ็อบเจ็กต์ OLE ได้อย่างง่ายดาย ปรับปรุงการนำเสนอของคุณด้วยเนื้อหาแบบไดนามิก
weight: 25
url: /th/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## การแนะนำ
การสร้างงานนำเสนอ PowerPoint แบบไดนามิกและโต้ตอบได้เป็นข้อกำหนดทั่วไปในโลกดิจิทัลในปัจจุบัน เครื่องมืออันทรงพลังอย่างหนึ่งในการบรรลุเป้าหมายนี้คือ Aspose.Slides สำหรับ .NET ซึ่งเป็นไลบรารีที่มีประสิทธิภาพที่ช่วยให้นักพัฒนาสามารถจัดการและปรับปรุงงานนำเสนอ PowerPoint โดยทางโปรแกรม ในบทช่วยสอนนี้ เราจะเจาะลึกกระบวนการเปลี่ยนแปลงข้อมูลออบเจ็กต์ OLE (Object Linking and Embedding) ภายในสไลด์การนำเสนอโดยใช้ Aspose.Slides
## ข้อกำหนดเบื้องต้น
ก่อนที่คุณจะเริ่มทำงานกับ Aspose.Slides สำหรับ .NET ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาโดยติดตั้ง .NET
2.  ไลบรารี Aspose.Slides: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถค้นหาห้องสมุด[ที่นี่](https://releases.aspose.com/slides/net/).
3. ความเข้าใจพื้นฐาน: ทำความคุ้นเคยกับแนวคิดพื้นฐานของการเขียนโปรแกรม C# และการนำเสนอ PowerPoint
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อใช้ฟังก์ชัน Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ
เริ่มต้นด้วยการสร้างโปรเจ็กต์ C# ใหม่และนำเข้าไลบรารี Aspose.Slides ตรวจสอบให้แน่ใจว่าโปรเจ็กต์ของคุณได้รับการกำหนดค่าอย่างถูกต้อง และคุณมีการขึ้นต่อกันที่จำเป็น
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
สำรวจรูปร่างทั้งหมดในสไลด์เพื่อค้นหากรอบวัตถุ OLE:
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
        // การอ่านข้อมูลวัตถุในสมุดงาน
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // การปรับเปลี่ยนข้อมูลสมุดงาน
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // การเปลี่ยนข้อมูลวัตถุเฟรม Ole
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
ด้วยการทำตามขั้นตอนเหล่านี้ คุณสามารถเปลี่ยนข้อมูลวัตถุ OLE ภายในสไลด์การนำเสนอได้อย่างราบรื่นโดยใช้ Aspose.Slides สำหรับ .NET นี่เป็นการเปิดโลกแห่งความเป็นไปได้ในการสร้างงานนำเสนอแบบไดนามิกและปรับแต่งตามความต้องการเฉพาะของคุณ
## คำถามที่พบบ่อย
### Aspose.Slides สำหรับ .NET คืออะไร
Aspose.Slides สำหรับ .NET เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม ช่วยให้จัดการและเพิ่มประสิทธิภาพได้ง่าย
### ฉันจะหาเอกสารประกอบ Aspose.Slides ได้ที่ไหน
 สามารถดูเอกสารประกอบสำหรับ Aspose.Slides สำหรับ .NET ได้[ที่นี่](https://reference.aspose.com/slides/net/).
### ฉันจะดาวน์โหลด Aspose.Slides สำหรับ .NET ได้อย่างไร
 คุณสามารถดาวน์โหลดไลบรารีได้จากหน้าเผยแพร่[ที่นี่](https://releases.aspose.com/slides/net/).
### มีการทดลองใช้ฟรีสำหรับ Aspose.Slides หรือไม่
 ใช่ คุณสามารถเข้าถึงการทดลองใช้ฟรีได้[ที่นี่](https://releases.aspose.com/).
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Slides สำหรับ .NET ได้ที่ไหน
 สำหรับการสนับสนุนและการสนทนาโปรดไปที่[ฟอรั่ม Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
