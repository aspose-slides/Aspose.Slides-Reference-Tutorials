---
title: ลบบันทึกย่อออกจากสไลด์ทั้งหมด
linktitle: ลบบันทึกย่อออกจากสไลด์ทั้งหมด
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีลบบันทึกย่อออกจากสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ทำให้การนำเสนอของคุณสะอาดตาและเป็นมืออาชีพมากขึ้น
weight: 13
url: /th/net/notes-slide-manipulation/remove-notes-from-all-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ลบบันทึกย่อออกจากสไลด์ทั้งหมด


หากคุณเป็นนักพัฒนา .NET ที่ทำงานกับงานนำเสนอ PowerPoint คุณอาจจำเป็นต้องลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอของคุณ สิ่งนี้มีประโยชน์เมื่อคุณต้องการล้างสไลด์ของคุณและกำจัดข้อมูลเพิ่มเติมที่ไม่ได้มีไว้สำหรับผู้ชมของคุณ ในคำแนะนำทีละขั้นตอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการใช้ Aspose.Slides สำหรับ .NET เพื่อให้งานนี้สำเร็จอย่างมีประสิทธิภาพ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้นบทช่วยสอนนี้ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. Visual Studio: คุณควรติดตั้ง Visual Studio บนเครื่องพัฒนาของคุณ

2.  Aspose.Slides สำหรับ .NET: คุณต้องติดตั้งไลบรารี Aspose.Slides สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์](https://releases.aspose.com/slides/net/).

3. การนำเสนอ PowerPoint: คุณควรมีงานนำเสนอ PowerPoint (PPTX) ที่มีบันทึกย่อบนสไลด์

## นำเข้าเนมสเปซ

ในโค้ด C# คุณจะต้องนำเข้าเนมสเปซที่จำเป็นเพื่อทำงานกับ Aspose.Slides ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

ตอนนี้คุณมีข้อกำหนดเบื้องต้นแล้ว เรามาแจกแจงขั้นตอนการลบบันทึกย่อออกจากสไลด์ทั้งหมดเป็นคำแนะนำทีละขั้นตอน

## ขั้นตอนที่ 1: โหลดงานนำเสนอ

```csharp
// เส้นทางไปยังไดเร็กทอรีเอกสาร
string dataDir = "Your Document Directory";

// สร้างอินสแตนซ์วัตถุการนำเสนอที่แสดงถึงไฟล์การนำเสนอ
Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx");
```

 ในขั้นตอนนี้ คุณจะต้องโหลดงานนำเสนอ PowerPoint ของคุณโดยใช้ Aspose.Slides สำหรับ .NET แทนที่`"Your Document Directory"` และ`"YourPresentation.pptx"` โดยมีพาธและชื่อไฟล์ที่เหมาะสม

## ขั้นตอนที่ 2: การลบบันทึกย่อ

ตอนนี้ เรามาทบทวนแต่ละสไลด์ในงานนำเสนอและลบบันทึกย่อออกจากสไลด์เหล่านั้น:

```csharp
INotesSlideManager mgr = null;
for (int i = 0; i < presentation.Slides.Count; i++)
{
    mgr = presentation.Slides[i].NotesSlideManager;
    mgr.RemoveNotesSlide();
}
```

วนซ้ำนี้จะผ่านสไลด์ทั้งหมดในงานนำเสนอของคุณ เข้าถึงตัวจัดการสไลด์โน้ตสำหรับแต่ละสไลด์ และเอาโน้ตออกจากสไลด์นั้น

## ขั้นตอนที่ 3: บันทึกการนำเสนอ

เมื่อคุณลบบันทึกย่อออกจากสไลด์ทั้งหมดแล้ว คุณสามารถบันทึกงานนำเสนอที่แก้ไขได้:

```csharp
presentation.Save(dataDir + "PresentationWithoutNotes.pptx", SaveFormat.Pptx);
```

 รหัสนี้จะบันทึกงานนำเสนอโดยไม่มีบันทึกย่อเป็นไฟล์ใหม่ที่มีชื่อว่า`"PresentationWithoutNotes.pptx"`คุณสามารถเปลี่ยนชื่อไฟล์เป็นเอาต์พุตที่คุณต้องการได้

แค่นั้นแหละ! คุณได้ลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอ PowerPoint ของคุณสำเร็จโดยใช้ Aspose.Slides สำหรับ .NET

 ในบทช่วยสอนนี้ เราได้กล่าวถึงขั้นตอนสำคัญเพื่อให้งานนี้สำเร็จอย่างมีประสิทธิภาพ หากคุณพบปัญหาใดๆ หรือมีคำถามเพิ่มเติม คุณสามารถดู Aspose.Slides สำหรับ .NET[เอกสารประกอบ](https://reference.aspose.com/slides/net/) หรือขอความช่วยเหลือได้ที่[กำหนดฟอรั่มการสนับสนุน](https://forum.aspose.com/).

## บทสรุป

การลบบันทึกย่อออกจากสไลด์ PowerPoint สามารถช่วยให้คุณนำเสนองานนำเสนอที่ดูสะอาดตาและดูเป็นมืออาชีพแก่ผู้ชมของคุณได้ Aspose.Slides สำหรับ .NET ทำให้งานนี้ตรงไปตรงมา ช่วยให้คุณสามารถจัดการงานนำเสนอ PowerPoint ได้อย่างง่ายดาย ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณสามารถลบบันทึกย่อออกจากสไลด์ทั้งหมดในงานนำเสนอของคุณได้อย่างรวดเร็ว ซึ่งช่วยเพิ่มความชัดเจนและรูปลักษณ์ที่น่าดึงดูด

## คำถามที่พบบ่อย (คำถามที่พบบ่อย)

### 1. ฉันสามารถใช้ Aspose.Slides สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่

ใช่ Aspose.Slides พร้อมใช้งานสำหรับ Java, C เช่นกัน- และภาษาโปรแกรมอื่นๆ อีกมากมาย

### 2. Aspose.Slides สำหรับ .NET เป็นไลบรารี่ฟรีหรือไม่

 Aspose.Slides สำหรับ .NET ไม่ใช่ไลบรารีฟรี คุณสามารถค้นหาข้อมูลราคาและใบอนุญาตได้ที่[เว็บไซต์](https://purchase.aspose.com/buy).

### 3. ฉันสามารถลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่

 ใช่ คุณสามารถขอรับ Aspose.Slides สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).

### 4. ฉันจะได้รับใบอนุญาตชั่วคราวสำหรับ Aspose.Slides สำหรับ .NET ได้อย่างไร

 คุณสามารถขอใบอนุญาตชั่วคราวเพื่อการทดสอบและพัฒนาได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).

### 5. Aspose.Slides สำหรับ .NET รองรับรูปแบบ PowerPoint ล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ .NET รองรับรูปแบบ PowerPoint ที่หลากหลาย รวมถึงเวอร์ชันล่าสุดด้วย คุณสามารถดูเอกสารประกอบเพื่อดูรายละเอียดได้
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
