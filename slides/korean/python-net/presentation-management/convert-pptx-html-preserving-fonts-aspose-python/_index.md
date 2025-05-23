---
"date": "2025-04-23"
"description": "Python에서 Aspose.Slides를 사용하여 글꼴을 유지하면서 PowerPoint 프레젠테이션(PPTX)을 HTML로 변환하는 방법을 알아보세요. 이 가이드에서는 글꼴 임베딩 최적화에 대한 단계별 지침과 팁을 제공합니다."
"title": "Python용 Aspose.Slides를 사용하여 글꼴을 보존하면서 PPTX를 HTML로 변환"
"url": "/ko/python-net/presentation-management/convert-pptx-html-preserving-fonts-aspose-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides를 사용하여 글꼴을 보존하면서 PPTX를 HTML로 변환

## 소개

PowerPoint 프레젠테이션(PPTX)을 원본 글꼴을 유지하면서 HTML 형식으로 변환하는 것은 어려울 수 있습니다. 특히 특정 기본 글꼴을 임베드에서 제외하려는 경우 더욱 그렇습니다. "Aspose.Slides for Python"을 사용하면 이 작업이 훨씬 수월해집니다. 이 튜토리얼에서는 Python에서 Aspose.Slides를 사용하여 PPTX 파일을 글꼴을 그대로 유지하면서 HTML로 변환하는 방법을 안내합니다.

**배울 내용:**
- Python용 Aspose.Slides를 설치하고 설정하는 방법
- 글꼴을 보존하면서 PowerPoint 프레젠테이션(PPTX)을 HTML로 변환
- 특정 기본 글꼴을 임베드에서 제외
- 변환 프로세스 중 성능 최적화

시작하기 전에 전제 조건을 살펴보겠습니다!

## 필수 조건

PPTX 파일을 변환하기 전에 다음 사항이 있는지 확인하세요.

### 필수 라이브러리 및 버전:
- **Python용 Aspose.Slides**: 이 튜토리얼에서 사용하는 기본 라이브러리입니다. 사용자 설정과의 호환성을 확인하세요.

### 환경 설정 요구 사항:
- 정상적으로 작동하는 Python 환경(Python 3.x 권장).
- 명령줄 인터페이스 또는 터미널에 접근합니다.

### 지식 전제 조건:
- Python 프로그래밍에 대한 기본적인 이해.
- 운영 체제에서 파일 경로와 디렉토리를 처리하는 방법에 익숙합니다.

## Python용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 먼저 설치해야 합니다. 설치 방법은 다음과 같습니다.

**Pip 설치:**

```bash
pip install aspose.slides
```

이 명령은 Python용 Aspose.Slides의 최신 버전을 설치하여 해당 기능에 대한 모든 액세스를 제공합니다.

### 라이센스 취득 단계:
- **무료 체험**: 무료 체험판을 다운로드하여 시작하세요 [여기](https://releases.aspose.com/slides/python-net/).
- **임시 면허**: 임시면허 신청 [여기](https://purchase.aspose.com/temporary-license/) 시간이 더 필요하다면.
- **구입**: 정식 라이선스 구매를 고려하세요 [여기](https://purchase.aspose.com/buy) 장기간 사용을 위해.

### 기본 초기화 및 설정:

설치가 완료되면 다음과 같이 Python 스크립트에 라이브러리를 가져옵니다.

```python
import aspose.slides as slides
```

이 줄은 Aspose.Slides 기능에 액세스하는 데 중요합니다.

## 구현 가이드

이 섹션에서는 변환 과정을 관리 가능한 단계로 나누어 살펴보겠습니다.

### PPTX를 HTML로 변환하여 원본 글꼴 보존

#### 개요:
이 구현의 주요 기능은 PowerPoint 프레젠테이션을 변환할 때 원본 글꼴을 유지하고 특정 기본 글꼴을 임베드에서 제외하는 것입니다. 이는 특히 웹 프레젠테이션 전반에서 브랜드 일관성을 유지하는 데 유용할 수 있습니다.

#### 단계별 구현:

**1. 입력 및 출력 경로 정의**

입력 PPTX 파일이 있는 디렉토리와 출력 HTML 파일을 저장할 디렉토리를 설정합니다.

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. 프레젠테이션 파일을 엽니다.**

Aspose.Slides를 사용하세요 `Presentation` PPTX 파일을 로드하는 클래스:

```python
with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    # 변환 코드는 여기에 입력하세요.
```

이 컨텍스트 관리자는 작업 후에 리소스가 적절하게 해제되도록 보장합니다.

**3. 사용자 정의 글꼴 임베딩 컨트롤러 만들기**

다음을 사용하여 특정 글꼴을 임베드에서 제외합니다. `EmbedAllFontsHtmlController`:

```python
font_name_exclude_list = ["Calibri", "Arial"]
embed_fonts_controller = slides.export.EmbedAllFontsHtmlController(font_name_exclude_list)
```

여기서 "Calibri"와 "Arial"은 HTML 출력에 포함되지 않습니다.

**4. HTML 내보내기 옵션 구성**

설정 `HtmlOptions` 컨트롤러와 함께 사용자 정의 글꼴 포매터를 사용하려면:

```python
html_options_embed = slides.export.HtmlOptions()
html_options_embed.html_formatter = slides.export.HtmlFormatter.create_custom_formatter(embed_fonts_controller)
```

이 단계에서는 최종 출력물에 필요한 글꼴만 포함되도록 보장합니다.

**5. 프레젠테이션을 HTML로 저장**

마지막으로, 지정한 옵션을 사용하여 프레젠테이션을 HTML 파일로 저장합니다.

```python
pres.save(out_dir + "convert_to_html_with_preserving_original_fonts_out.html", 
          slides.export.SaveFormat.HTML, html_options_embed)
```

### 문제 해결 팁:
- 경로가 올바르게 설정되고 접근이 가능한지 확인하세요.
- 변환에 영향을 줄 수 있는 시스템에서 누락된 글꼴 파일이 있는지 확인하세요.

## 실제 응용 프로그램

이 기능이 매우 유용할 수 있는 실제 시나리오는 다음과 같습니다.

1. **웹 포털**: 브랜드 글꼴을 잃지 않고 웹 애플리케이션에 원활하게 통합할 수 있도록 프레젠테이션을 HTML로 변환합니다.
2. **문서 관리 시스템**: 문서의 충실성을 유지하면서 내부 포털에 프레젠테이션을 포함합니다.
3. **이러닝 플랫폼**: 일관된 모양과 느낌을 유지하면서 변환된 HTML 파일을 온라인 과정의 일부로 사용할 수 있습니다.

## 성능 고려 사항

변환 중 최적의 성능을 보장하려면:
- **메모리 사용 최적화**: 사용되지 않는 리소스를 즉시 닫아 리소스 할당을 관리합니다.
- **일괄 처리**: 여러 프레젠테이션을 일괄적으로 변환하여 오버헤드를 줄입니다.
- **최신 라이브러리 버전 사용**: 향상된 기능과 버그 수정을 위해 항상 최신 버전의 Aspose.Slides를 사용하세요.

## 결론

축하합니다! Aspose.Slides for Python을 사용하여 PPTX 파일을 원본 글꼴을 유지하면서 HTML로 변환하는 방법을 배웠습니다. 이 방법을 사용하면 다양한 플랫폼에서 프레젠테이션이 의도한 대로 표시되도록 할 수 있습니다.

**다음 단계:**
- PDF 변환이나 이미지 추출 등 다른 Aspose.Slides 기능을 살펴보세요.
- 다양한 사용 사례에 맞춰 다양한 글꼴 내장 옵션을 실험해 보세요.

사용해 볼 준비가 되셨나요? 이 솔루션을 여러분의 프로젝트에 구현하고 그 차이를 직접 확인해 보세요!

## FAQ 섹션

1. **Aspose.Slides Python을 사용하기 위한 시스템 요구 사항은 무엇입니까?**
   - 라이브러리 설치를 위해 pip와 함께 Python 3.x의 호환 버전이 필요합니다.

2. **두 개 이상의 글꼴을 임베드에서 제외할 수 있나요?**
   - 네, 수정할 수 있습니다 `font_name_exclude_list` 원하는 수의 글꼴을 제외할 수 있습니다.

3. **변환하는 동안 큰 PPTX 파일을 어떻게 처리합니까?**
   - 성능 고려 사항에서 설명한 대로 세그먼트로 처리하거나 리소스 사용을 최적화하는 것을 고려하세요.

4. **Aspose.Slides 기능에 대한 자세한 정보는 어디에서 찾을 수 있나요?**
   - 그만큼 [공식 문서](https://reference.aspose.com/slides/python-net/) 포괄적인 가이드와 예시를 제공합니다.

5. **문제가 발생하면 어떤 지원 옵션을 이용할 수 있나요?**
   - 참여하세요 [Aspose 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 중심 솔루션을 찾거나 해당 채널을 통해 공식 지원을 받으세요.

## 자원
- **선적 서류 비치**: [Aspose.Slides 문서](https://reference.aspose.com/slides/python-net/)
- **다운로드**: [Aspose.Slides Python 릴리스](https://releases.aspose.com/slides/python-net/)
- **구입**: [Aspose.Slides 라이선스 구매](https://purchase.aspose.com/buy)
- **무료 체험**: [Aspose.Slides 무료 체험판](https://releases.aspose.com/slides/python-net/)
- **임시 면허**: [임시 면허 신청](https://purchase.aspose.com/temporary-license/)
- **지원하다**: [Aspose 지원 포럼](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}