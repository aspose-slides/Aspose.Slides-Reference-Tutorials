---
"date": "2025-04-24"
"description": "Python용 Aspose.Slides를 사용하여 글꼴 대체 규칙을 만들고 관리하는 방법을 알아보고, 다양한 시스템에서 프레젠테이션의 일관성을 유지하세요."
"title": "Python용 Aspose.Slides에서 글꼴 대체 기능 마스터하기 - 종합 가이드"
"url": "/ko/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python용 Aspose.Slides에서 글꼴 대체 기능 마스터하기: 종합 가이드

## 소개

프레젠테이션을 만들 때 글꼴 호환성 문제는 까다로울 수 있는데, 특히 기본 글꼴에서 유니코드 문자를 지원하지 않는 경우 더욱 그렇습니다. **Python용 Aspose.Slides** 다양한 시스템에서 프레젠테이션의 시각적 매력과 가독성을 보장하는 글꼴 대체 규칙을 통해 강력한 솔루션을 제공합니다.

이 가이드에서는 Python용 Aspose.Slides를 사용하여 글꼴 대체 규칙을 만들고 관리하는 방법을 살펴보겠습니다. 다음 내용을 배우게 됩니다.
- Aspose.Slides를 사용하여 환경 설정하기
- 글꼴 대체 규칙 모음 만들기
- 유니코드 범위에 따라 글꼴을 추가하거나 제거하여 이러한 규칙을 관리합니다.
- 프레젠테이션에 규칙 적용 및 슬라이드를 이미지로 렌더링

먼저, 주변 환경을 준비해보겠습니다.

## 필수 조건

이 작업을 수행할 환경이 준비되었는지 확인하세요. 필요한 사항은 다음과 같습니다.
1. **Python용 Aspose.Slides**: 이 라이브러리는 글꼴 대체 규칙을 관리합니다.
2. **파이썬 환경**: Python(버전 3.6 이상)이 설치되어 있는지 확인하세요.
3. **기본 파이썬 지식**: 코드 조각을 자세히 살펴볼 때 Python 구문과 개념에 익숙해지는 것이 도움이 됩니다.

## Python용 Aspose.Slides 설정

### 설치

시작하려면 pip를 사용하여 Aspose.Slides 라이브러리를 설치하세요.

```bash
pip install aspose.slides
```

### 라이센스 취득

Aspose는 제한 없이 기능을 체험해 볼 수 있는 무료 체험판 라이선스를 제공합니다. 라이선스를 받는 방법은 다음과 같습니다.
- 방문하다 [Aspose 구매 페이지](https://purchase.aspose.com/buy) 구매 옵션을 이용하거나 임시 라이센스에 액세스하세요.
- 또는 무료 평가판을 다운로드하세요. [다운로드 섹션](https://releases.aspose.com/slides/python-net/).

### 기본 초기화

설치가 완료되면 Python 스크립트에서 Aspose.Slides를 초기화합니다.

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## 구현 가이드

### 글꼴 대체 규칙 만들기 및 관리

#### 개요

글꼴 대체 규칙은 프레젠테이션의 모든 문자에 적절한 글꼴이 있는지 확인하여 고유한 문자 집합을 사용하는 언어의 가독성을 유지합니다.

#### 구현 단계

**1. 글꼴 대체 규칙 컬렉션 만들기**

대체 글꼴을 정의하기 위한 컬렉션을 만드는 것부터 시작하세요.

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. 글꼴 대체 규칙 추가**

유니코드 범위와 대체 글꼴을 지정하는 규칙을 정의합니다.

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **매개변수**: `0x400` 유니코드 범위의 시작입니다. `0x4FF` 끝이다, 그리고 `"Times New Roman"` 대체 글꼴입니다.

**3. 기존 규칙 관리**

필요에 따라 각 규칙을 반복하여 수정합니다.

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. 규칙 제거**

필요한 경우 컬렉션에서 첫 번째 규칙을 제거하세요.

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### 프레젠테이션에 글꼴 대체 규칙 적용 및 이미지 렌더링

#### 개요

글꼴 대체 규칙을 설정한 후에는 프레젠테이션에 적용하여 필요할 때 텍스트가 지정된 대체 글꼴을 사용하도록 합니다.

#### 구현 단계

**1. 환경 초기화**

입력 및 출력을 위한 디렉토리를 준비합니다.

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. 프레젠테이션에 대체 규칙 적용**

프레젠테이션 파일을 로드하고 글꼴 규칙을 적용합니다.

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}