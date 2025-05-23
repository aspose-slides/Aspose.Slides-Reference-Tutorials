---
"date": "2025-04-23"
"description": "Aspose.Slides for Python을 사용하여 PowerPoint 프레젠테이션을 읽기 전용으로 설정하고 슬라이드 개수를 프로그래밍 방식으로 계산하는 방법을 알아보세요. 안전한 문서 공유 및 자동 보고에 적합합니다."
"title": "Aspose.Slides를 사용하여 Python으로 PowerPoint를 읽기 전용으로 설정하고 슬라이드 수 계산"
"url": "/ko/python-net/security-protection/powerpoint-read-only-python-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Python을 사용하여 PowerPoint를 읽기 전용으로 설정하고 슬라이드 수 계산하기

## 소개
프레젠테이션을 변경 없이 배포해야 하는 어려움을 겪어 본 적이 있으신가요? 아니면 프레젠테이션을 열지 않고도 슬라이드 수를 쉽게 확인할 수 있는 방법을 찾고 계셨나요? **Python용 Aspose.Slides**이러한 작업은 간단해집니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 읽기 전용으로 설정하고 슬라이드 수를 세는 방법을 안내합니다. Aspose.Slides는 PowerPoint 파일을 프로그래밍 방식으로 관리할 수 있는 강력한 솔루션을 제공합니다.

**배울 내용:**
- PowerPoint 프레젠테이션에 쓰기 보호를 설정하는 방법.
- 읽기 전용으로 제한하여 PowerPoint 파일을 저장하는 방법.
- 프레젠테이션을 로드하고 슬라이드 수를 효율적으로 세는 방법.

Python에서 이러한 작업을 원활하게 달성하는 방법을 알아보겠습니다.

## 필수 조건
시작하기 전에 다음 사항을 확인하세요.
- **파이썬 3.6 이상** 귀하의 시스템에 설치되었습니다.
- 패키지 설치를 위한 명령줄 인터페이스에 접근합니다.

Python용 Aspose.Slides도 설치해야 합니다. 이 강력한 라이브러리를 사용하면 Python 환경에서 바로 PowerPoint 파일을 고급 조작할 수 있습니다. 무료 버전은 제한된 기능만 제공하지만, 라이선스를 구매하면(무료 체험판 또는 구매) 기능을 크게 확장할 수 있습니다.

## Python용 Aspose.Slides 설정
Python에서 Aspose.Slides를 사용하려면 먼저 설치해야 합니다. 설치 방법은 다음과 같습니다.

### pip 설치
터미널이나 명령 프롬프트에서 다음 명령을 실행하세요.

```bash
pip install aspose.slides
```

이렇게 하면 Python용 Aspose.Slides의 최신 버전이 다운로드되어 설치됩니다.

### 라이센스 취득 단계
1. **무료 체험**: 무료 체험판을 통해 기본 기능을 탐색해 보세요.
2. **임시 면허**: 평가 기간 동안 모든 기능을 사용할 수 있는 임시 라이선스를 받으세요.
3. **구입**: 지속적인 액세스와 지원을 위해 라이선스 구매를 고려하세요.

라이선스 파일을 받으면 다음과 같이 스크립트에 로드합니다.

```python
class LicenseLoader:
    def __init__(self):
        self.license = aspose.slides.License()

    def set_license(self, path_to_license_file):
        self.license.set_license(path_to_license_file)
```

## 구현 가이드
이 섹션에서는 구현을 두 가지 주요 기능, 즉 프레젠테이션을 읽기 전용으로 설정하는 것과 슬라이드 계산으로 나누어 살펴보겠습니다.

### 기능 1: 프레젠테이션을 읽기 전용으로 저장
#### 개요
이 기능을 사용하면 PowerPoint 파일에 쓰기 보호를 설정하여 비밀번호를 입력하지 않으면 파일을 수정할 수 없도록 할 수 있습니다. 특히 수신자가 변경하지 않아야 하는 프레젠테이션을 배포할 때 유용합니다.

#### 단계
##### 1단계: 프레젠테이션 개체 인스턴스화
먼저 다음을 만들어 보세요. `Presentation` 객체입니다. 이는 Python으로 작성된 PPT 파일을 나타냅니다.

```python
import aspose.slides as slides

class ReadWriteProtection:
    def __init__(self, password):
        self.password = password

    def set_write_protection(self, presentation_path, output_directory):
        with slides.Presentation(presentation_path) as presentation:
            presentation.protection_manager.set_write_protection(self.password)
            presentation.save(f"{output_directory}/save_as_read_only_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}