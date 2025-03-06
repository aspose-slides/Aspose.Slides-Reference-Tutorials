---
title: การจัดการส่วนหัวและส่วนท้ายใน Notes ด้วย Aspose.Slides .NET
linktitle: จัดการส่วนหัวและส่วนท้ายใน Notes Slide
second_title: Aspose.Slides .NET PowerPoint การประมวลผล API
description: เรียนรู้วิธีจัดการส่วนหัวและส่วนท้ายในสไลด์บันทึกย่อของ PowerPoint โดยใช้ Aspose.Slides สำหรับ .NET ปรับปรุงการนำเสนอของคุณได้อย่างง่ายดาย
weight: 11
url: /th/net/notes-slide-manipulation/header-and-footer-in-notes-slide/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


ในยุคดิจิทัลปัจจุบัน การสร้างงานนำเสนอที่น่าดึงดูดและให้ข้อมูลเป็นทักษะที่สำคัญ ในกระบวนการนี้ คุณอาจจำเป็นต้องรวมส่วนหัวและส่วนท้ายไว้ในสไลด์บันทึกย่อของคุณเพื่อให้บริบทและข้อมูลเพิ่มเติม Aspose.Slides สำหรับ .NET เป็นเครื่องมืออันทรงพลังที่ช่วยให้คุณจัดการการตั้งค่าส่วนหัวและส่วนท้ายในสไลด์บันทึกย่อได้อย่างง่ายดาย ในคำแนะนำทีละขั้นตอนนี้ เราจะสำรวจวิธีการบรรลุเป้าหมายนี้โดยใช้ Aspose.Slides สำหรับ .NET

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกบทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1.  Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่า Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้[ที่นี่](https://releases.aspose.com/slides/net/).

2. งานนำเสนอ PowerPoint: คุณจะต้องมีงานนำเสนอ PowerPoint (ไฟล์ PPTX) ที่คุณต้องการใช้งาน

ตอนนี้เราได้ครอบคลุมข้อกำหนดเบื้องต้นแล้ว เรามาเริ่มจัดการส่วนหัวและส่วนท้ายในสไลด์บันทึกย่อโดยใช้ Aspose.Slides สำหรับ .NET กันดีกว่า

## ขั้นตอนที่ 1: นำเข้าเนมสเปซ

ในการเริ่มต้น คุณต้องนำเข้าเนมสเปซที่จำเป็นสำหรับโปรเจ็กต์ของคุณ รวมเนมสเปซต่อไปนี้:

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Export;
```

เนมสเปซเหล่านี้ให้การเข้าถึงคลาสและวิธีการที่จำเป็นในการจัดการส่วนหัวและส่วนท้ายในสไลด์บันทึกย่อ

## ขั้นตอนที่ 2: เปลี่ยนการตั้งค่าส่วนหัวและส่วนท้าย

ต่อไป เราจะเปลี่ยนการตั้งค่าส่วนหัวและส่วนท้ายสำหรับบันทึกย่อหลักและสไลด์บันทึกย่อทั้งหมดในงานนำเสนอของคุณ ต่อไปนี้เป็นวิธีดำเนินการ:

```csharp
using (Presentation presentation = new Presentation("presentation.pptx"))
{
    IMasterNotesSlide masterNotesSlide = presentation.MasterNotesSlideManager.MasterNotesSlide;

    if (masterNotesSlide != null)
    {
        IMasterNotesSlideHeaderFooterManager headerFooterManager = masterNotesSlide.HeaderFooterManager;

        headerFooterManager.SetHeaderAndChildHeadersVisibility(true);
        headerFooterManager.SetFooterAndChildFootersVisibility(true);
        headerFooterManager.SetSlideNumberAndChildSlideNumbersVisibility(true);
        headerFooterManager.SetDateTimeAndChildDateTimesVisibility(true);

        headerFooterManager.SetHeaderAndChildHeadersText("Header text");
        headerFooterManager.SetFooterAndChildFootersText("Footer text");
        headerFooterManager.SetDateTimeAndChildDateTimesText("Date and time text");
    }

    // บันทึกงานนำเสนอด้วยการตั้งค่าที่อัปเดต
    presentation.Save("testresult.pptx", SaveFormat.Pptx);
}
```

ในขั้นตอนนี้ เราจะเข้าถึงสไลด์บันทึกย่อหลัก และตั้งค่าการมองเห็นและข้อความสำหรับส่วนหัว ท้ายกระดาษ หมายเลขสไลด์ และตัวยึดตำแหน่งวันที่-เวลา

## ขั้นตอนที่ 3: เปลี่ยนการตั้งค่าส่วนหัวและส่วนท้ายสำหรับสไลด์บันทึกย่อเฉพาะ

ในตอนนี้ ถ้าคุณต้องการเปลี่ยนการตั้งค่าส่วนหัวและส่วนท้ายสำหรับสไลด์บันทึกย่อเฉพาะ ให้ทำตามขั้นตอนเหล่านี้:

```csharp
using (Presentation presentation = new Presentation("presentation.pptx"))
{
    INotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.NotesSlide;

    if (notesSlide != null)
    {
        INotesSlideHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

        if (!headerFooterManager.IsHeaderVisible)
            headerFooterManager.SetHeaderVisibility(true);

        if (!headerFooterManager.IsFooterVisible)
            headerFooterManager.SetFooterVisibility(true);

        if (!headerFooterManager.IsSlideNumberVisible)
            headerFooterManager.SetSlideNumberVisibility(true);

        if (!headerFooterManager.IsDateTimeVisible)
            headerFooterManager.SetDateTimeVisibility(true);

        headerFooterManager.SetHeaderText("New header text");
        headerFooterManager.SetFooterText("New footer text");
        headerFooterManager.SetDateTimeText("New date and time text");
    }

    // บันทึกงานนำเสนอด้วยการตั้งค่าที่อัปเดต
    presentation.Save("testresult.pptx", SaveFormat.Pptx);
}
```

ในขั้นตอนนี้ เราจะเข้าถึงสไลด์บันทึกย่อเฉพาะ และแก้ไขการมองเห็นและข้อความสำหรับส่วนหัว ส่วนท้าย หมายเลขสไลด์ และตัวยึดตำแหน่งวันที่-เวลา

## บทสรุป

การจัดการส่วนหัวและส่วนท้ายในสไลด์บันทึกย่ออย่างมีประสิทธิภาพถือเป็นสิ่งสำคัญในการปรับปรุงคุณภาพโดยรวมและความชัดเจนของงานนำเสนอของคุณ ด้วย Aspose.Slides สำหรับ .NET กระบวนการนี้จะตรงไปตรงมาและมีประสิทธิภาพ บทช่วยสอนนี้มีคำแนะนำที่ครอบคลุมเกี่ยวกับวิธีการบรรลุเป้าหมาย ตั้งแต่การนำเข้าเนมสเปซไปจนถึงการเปลี่ยนการตั้งค่าสำหรับทั้งสไลด์บันทึกย่อหลักและสไลด์บันทึกย่อแต่ละรายการ

 หากคุณยังไม่ได้ลองสำรวจดู[Aspose.Slides สำหรับเอกสาร .NET](https://reference.aspose.com/slides/net/) สำหรับข้อมูลเชิงลึกและตัวอย่างเพิ่มเติม

## คำถามที่พบบ่อย

### Aspose.Slides สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 ไม่ Aspose.Slides สำหรับ .NET เป็นผลิตภัณฑ์เชิงพาณิชย์ และคุณจะต้องซื้อใบอนุญาตเพื่อใช้ในโครงการของคุณ คุณสามารถขอรับใบอนุญาตชั่วคราวได้[ที่นี่](https://purchase.aspose.com/temporary-license/) สำหรับการทดสอบ

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของส่วนหัวและส่วนท้ายเพิ่มเติมได้หรือไม่
ใช่ Aspose.Slides สำหรับ .NET มีตัวเลือกมากมายสำหรับการปรับแต่งรูปลักษณ์ของส่วนหัวและส่วนท้าย ซึ่งช่วยให้คุณปรับแต่งให้ตรงกับความต้องการเฉพาะของคุณได้

### มีคุณสมบัติอื่นใดใน Aspose.Slides สำหรับ .NET สำหรับการจัดการการนำเสนอหรือไม่
ใช่ Aspose.Slides สำหรับ .NET นำเสนอคุณสมบัติที่หลากหลายสำหรับการสร้าง แก้ไข และจัดการงานนำเสนอ รวมถึงสไลด์ รูปร่าง และการเปลี่ยนผ่านสไลด์

### ฉันสามารถทำให้งานนำเสนอ PowerPoint เป็นแบบอัตโนมัติด้วย Aspose.Slides สำหรับ .NET ได้หรือไม่
แน่นอน Aspose.Slides สำหรับ .NET ช่วยให้คุณสามารถนำเสนอ PowerPoint ได้โดยอัตโนมัติ ทำให้เป็นเครื่องมือที่มีค่าสำหรับการสร้างสไลด์โชว์แบบไดนามิกและขับเคลื่อนด้วยข้อมูล

### มีการสนับสนุนทางเทคนิคสำหรับ Aspose.Slides สำหรับผู้ใช้ .NET หรือไม่
 ใช่ คุณสามารถค้นหาการสนับสนุนและความช่วยเหลือจากชุมชน Aspose และผู้เชี่ยวชาญได้ที่[กำหนดฟอรั่มการสนับสนุน](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
