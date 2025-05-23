---
"date": "2025-04-17"
"description": "เรียนรู้วิธีการสร้าง ปรับแต่ง และบันทึกแผนภูมิพร้อมป้ายกำกับเปอร์เซ็นต์ในงานนำเสนอ Java โดยใช้ Aspose.Slides พัฒนาทักษะการนำเสนอของคุณวันนี้!"
"title": "สร้างและปรับแต่งแผนภูมิในงานนำเสนอ Java โดยใช้ Aspose.Slides"
"url": "/th/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างและปรับแต่งแผนภูมิในงานนำเสนอ Java โดยใช้ Aspose.Slides

## การแนะนำ
การสร้างงานนำเสนอที่น่าสนใจมักเกี่ยวข้องกับมากกว่าแค่ข้อความ แต่ยังต้องใช้แผนภูมิแบบไดนามิกที่ถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ หากคุณต้องการปรับปรุงงานนำเสนอที่ใช้ Java ของคุณด้วยฟีเจอร์แผนภูมิที่ซับซ้อนโดยใช้ Aspose.Slides บทช่วยสอนนี้เหมาะสำหรับคุณ เราจะแนะนำคุณตลอดขั้นตอนการสร้างงานนำเสนอ การเพิ่มและกำหนดค่าแผนภูมิ การคำนวณผลรวม การแสดงป้ายเปอร์เซ็นต์ และการบันทึกงานของคุณ ซึ่งทั้งหมดนี้ทำได้ในไม่กี่ขั้นตอนง่ายๆ

**สิ่งที่คุณจะได้เรียนรู้:**
- วิธีการสร้างและปรับแต่งการนำเสนอด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java
- การคำนวณผลรวมหมวดหมู่ในแผนภูมิ
- การแสดงข้อมูลเป็นป้ายเปอร์เซ็นต์บนแผนภูมิ
- การบันทึกการนำเสนอด้วยคุณสมบัติแผนภูมิที่ได้รับการปรับปรุง

มาเจาะลึกข้อกำหนดเบื้องต้นที่คุณต้องมีก่อนที่จะเริ่มต้น

## ข้อกำหนดเบื้องต้น
หากต้องการทำตามบทช่วยสอนนี้ ให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- **ชุดพัฒนา Java (JDK)**: เวอร์ชัน 8 ขึ้นไป.
- **ไอดีอี**เช่น IntelliJ IDEA, Eclipse หรือ IDE ใดๆ ที่รองรับ Java
- **Aspose.Slides สำหรับไลบรารี Java**:สิ่งนี้มีความสำคัญต่อการจัดการคุณลักษณะการนำเสนอ

### ไลบรารีและเวอร์ชันที่จำเป็น
คุณจะต้องมี Aspose.Slides สำหรับ Java ต่อไปนี้เป็นวิธีรวมไว้ในโปรเจ็กต์ของคุณ:

**เมเวน:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**เกรเดิ้ล:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

หรือคุณสามารถดาวน์โหลดเวอร์ชันล่าสุดโดยตรงจาก [Aspose.Slides สำหรับการเปิดตัว Java](https://releases-aspose.com/slides/java/).

### การตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมการพัฒนาของคุณได้รับการกำหนดค่าให้ใช้ JDK 8 หรือใหม่กว่า และ IDE ของคุณได้รับการตั้งค่าให้จัดการการอ้างอิงโดยใช้ Maven หรือ Gradle

**การได้มาซึ่งใบอนุญาต:**
- **ทดลองใช้งานฟรี**:เข้าถึงคุณลักษณะพื้นฐานเพื่อวัตถุประสงค์ในการทดสอบ
- **ใบอนุญาตชั่วคราว**:ทดสอบคุณสมบัติขั้นสูงโดยไม่มีข้อจำกัดในการประเมิน
- **ซื้อ**:หากต้องการใช้เชิงพาณิชย์ในระยะยาว ควรพิจารณาซื้อใบอนุญาต

## การตั้งค่า Aspose.Slides สำหรับ Java
เริ่มต้นด้วยการตั้งค่าไลบรารี Aspose.Slides ในโปรเจ็กต์ Java ของคุณ ต่อไปนี้เป็นวิธีการเริ่มต้นและกำหนดค่า:

1. เพิ่มการอ้างอิงผ่าน Maven หรือ Gradle ดังที่แสดงด้านบน
2. นำเข้าแพ็กเกจ Aspose.Slides ที่จำเป็น:
   ```java
   import com.aspose.slides.*;
   ```

3. เริ่มต้นใหม่ `Presentation` ตัวอย่าง:
   ```java
   Presentation presentation = new Presentation();
   ```

การตั้งค่านี้จะช่วยให้คุณเริ่มสร้างการนำเสนอผ่านโปรแกรมได้

## คู่มือการใช้งาน

### สร้างและปรับแต่งแผนภูมิในงานนำเสนอของคุณ

#### ภาพรวม
การสร้างแผนภูมิเกี่ยวข้องกับการเริ่มต้นการนำเสนอ การเข้าถึงสไลด์ และการเพิ่มแผนภูมิที่มีแอตทริบิวต์เฉพาะ เช่น ประเภท ตำแหน่ง และขนาด

**ขั้นตอน:**
1. **สร้างตัวอย่างการนำเสนอ**:เริ่มต้นด้วยการสร้างอินสแตนซ์ของ `Presentation` ระดับ.
2. **สไลด์การเข้าถึง**:ดึงสไลด์แรกโดยใช้ `get_Item(0)`-
3. **เพิ่มแผนภูมิ**: ใช้ `addChart()` เพื่อเพิ่มแผนภูมิคอลัมน์แบบซ้อนกันตามพิกัดที่ระบุพร้อมทั้งมีมิติที่กำหนด

```java
// คุณสมบัติ: สร้างการนำเสนอด้วยแผนภูมิ
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### คำนวณผลรวมสำหรับหมวดหมู่

#### ภาพรวม
การคำนวณผลรวมหมวดหมู่เกี่ยวข้องกับการวนซ้ำผ่านแต่ละชุดในแผนภูมิเพื่อสรุปค่าต่อหมวดหมู่

**ขั้นตอน:**
1. **การเริ่มต้นอาร์เรย์**: สร้างอาร์เรย์เพื่อเก็บค่ารวมทั้งหมด
2. **ทำซ้ำผ่านหมวดหมู่และซีรีส์**:ใช้ลูปซ้อนกันเพื่อสะสมผลรวมสำหรับแต่ละหมวดหมู่จากชุดทั้งหมด

```java
// คุณสมบัติ: คำนวณผลรวมสำหรับหมวดหมู่ในแผนภูมิ
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### แสดงข้อมูลเป็นป้ายเปอร์เซ็นต์บนแผนภูมิ

#### ภาพรวม
ฟีเจอร์นี้มุ่งเน้นที่การกำหนดค่าป้ายข้อมูลเพื่อแสดงค่าเป็นเปอร์เซ็นต์ ซึ่งจะทำให้เกิดความชัดเจนในการแสดงภาพ

**ขั้นตอน:**
1. **กำหนดค่าฉลากชุด**:ตั้งค่าคุณสมบัติของป้ายกำกับเช่นขนาดแบบอักษรและความสามารถในการมองเห็นของคีย์คำอธิบาย
2. **คำนวณเปอร์เซ็นต์**:คำนวณเปอร์เซ็นต์สำหรับแต่ละจุดข้อมูลตามค่าหมวดหมู่ทั้งหมด
3. **ตั้งค่าข้อความป้ายชื่อ**:จัดรูปแบบป้ายกำกับให้แสดงเปอร์เซ็นต์พร้อมจุดทศนิยมสองตำแหน่ง

```java
// คุณลักษณะ: แสดงข้อมูลเป็นป้ายเปอร์เซ็นต์บนแผนภูมิ
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### บันทึกการนำเสนอด้วยแผนภูมิ

#### ภาพรวม
สุดท้ายให้บันทึกการนำเสนอของคุณไปยังเส้นทางที่ระบุในรูปแบบ PPTX

**ขั้นตอน:**
1. **วิธีการบันทึก**: ใช้ `save()` วิธีการบน `Presentation` ตัวอย่าง.
2. **กำจัดทรัพยากร**:ให้แน่ใจว่าทรัพยากรจะได้รับการปล่อยหลังจากการบันทึก

```java
// คุณสมบัติ: บันทึกการนำเสนอด้วยแผนภูมิ
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## การประยุกต์ใช้งานจริง

1. **การรายงานทางการเงิน**:ใช้แผนภูมิเพื่อแสดงเปอร์เซ็นต์การเติบโตของรายได้ในแต่ละแผนก
2. **การวิเคราะห์ข้อมูลการขาย**:แสดงภาพข้อมูลการขายตามภูมิภาคพร้อมป้ายกำกับเปอร์เซ็นต์เพื่อให้มองเห็นข้อมูลเชิงลึกได้ชัดเจนยิ่งขึ้น
3. **การนำเสนอด้านการศึกษา**:ปรับปรุงการนำเสนอทางวิชาการด้วยสถิติภาพ
4. **แคมเปญการตลาด**:แสดงผลเมตริกประสิทธิภาพแคมเปญเป็นภาพที่น่าสนใจ
5. **การประชุมกลยุทธ์ทางธุรกิจ**:ใช้แผนภูมิเพื่อถ่ายทอดข้อมูลที่ซับซ้อนในการอภิปรายการวางแผนเชิงกลยุทธ์

## การพิจารณาประสิทธิภาพ
- **การจัดการหน่วยความจำ**: กำจัดทิ้ง `Presentation` วัตถุเพื่อปลดปล่อยทรัพยากรอย่างทันท่วงที
- **เพิ่มประสิทธิภาพการโหลดแผนภูมิ**โหลดเฉพาะองค์ประกอบแผนภูมิที่จำเป็นลงในหน่วยความจำหากเป็นไปได้
- **การประมวลผลแบบแบตช์**:เมื่อประมวลผลการนำเสนอหลายรายการ ควรพิจารณาจัดการเป็นชุดเพื่อจัดการการใช้ทรัพยากรอย่างมีประสิทธิภาพ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}