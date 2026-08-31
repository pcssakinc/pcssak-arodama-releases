# 설치와 첫 실행

[English](INSTALLATION.md)

이 안내는 PCssak AroDamA 무료 Early Access `0.4.0`에 적용됩니다.

## 1. 공식 릴리스 확인

`v0.4.0`이 초안·Prerelease가 아닌 공개 GitHub Latest로 표시되고
[릴리스 자산 정책](RELEASE-ASSET-POLICY.md)의 정확한 17개 자산을 모두 갖춘 뒤에만 설치하십시오.
저장소 파일, Pull Request 산출물, 미리보기 배포, 소스 태그, 업무일지, 공개되지 않은 초안은 공식
설치본이 아닙니다.

- 공식 제품 페이지: `https://pcssak.com/arodama`
- 버전 고정 릴리스:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.0`
- 고정 업데이트 주소:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

## 2. 설치본 선택

| Windows 환경 | 설치본 | 상태 |
| --- | --- | --- |
| Windows 11 Home/Pro x64 | `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe` | 주 지원 후보 |
| Windows 10 22H2 Home/Pro x64 | x64 설치본 | 제한적 호환 후보 |
| Windows 10 22H2 Home/Pro x86 | `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x86-Setup.exe` | 제한적 호환 후보 |
| Windows 11 x86 | 없음 | Windows 11 x86은 존재하지 않음 |
| 네이티브 ARM64, S 모드, Server, macOS, Linux, Wine | 없음 | 미지원 |

Windows 10 호환 표기는 Microsoft의 Windows 10 지원을 연장하지 않습니다. 64비트 PC에서 x86
설치본이 있다는 이유만으로 32비트판을 설치하지 마십시오.

## 3. 실행 전 검증

같은 버전 고정 릴리스에서 설치본, 같은 이름의 `.sig`, `SHA256SUMS.txt`를 받습니다. 로컬에서
계산한 SHA-256과 공개 값을 비교하십시오.

```powershell
Get-FileHash -Algorithm SHA256 '.\PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe'
```

AroDamA 업데이트 서명은 앱에 내장된 AroDamA 전용 Tauri 공개키로 업데이트 파일 무결성을
검증합니다. Windows 게시자 신원을 증명하는 서명이 아닙니다.

`0.4.0` 설치본은 **Windows Authenticode 미서명**입니다. Windows가 알 수 없는 게시자,
Microsoft Defender SmartScreen, Smart App Control 또는 조직 정책 경고를 표시할 수 있습니다.
설치를 위해 Windows 보안·백신·방화벽·조직 정책을 끄지 마십시오. 파일명·바이트 크기·SHA-256·
서명·버전 고정 URL·자산 목록 중 하나라도 맞지 않으면 중단하십시오.

## 4. 설치

1. 실행 중인 이전 AroDamA 창이 있으면 닫습니다.
2. PC 아키텍처에 맞는 설치본을 실행합니다.
3. 설치기가 제공하는 여덟 언어 중 하나를 선택합니다.
4. EULA를 읽고 동의할 때만 수락합니다. 취소하면 설치가 완료되지 않아야 합니다.
5. Windows에 필요할 때만 Microsoft Edge WebView2 Runtime 설치 또는 전달을 허용합니다.
6. 시작 메뉴나 설치된 바로 가기에서 AroDamA를 실행합니다.

설치기 언어와 앱 안의 언어는 별개입니다. 앱은 한국어·영어·독일어·스페인어·브라질 포르투갈어·
일본어·프랑스어·중국어 간체를 지원합니다.

## 5. 첫 실행 동의

동의 전에는 클립보드 수집과 자동 업데이트 확인이 꺼진 상태여야 합니다. 로컬 데이터·보관·삭제·
백업·업데이트·네트워크 안내를 읽고 수집 시작 여부를 명시적으로 선택하십시오. 이후 설정에서
수집과 업데이트 확인을 바꿀 수 있습니다.

핵심 클립보드 내용은 로컬에 저장됩니다. 민감한 업무에 사용하기 전에
[개인정보 처리 안내](../PRIVACY.md)와 [알려진 한계](KNOWN-LIMITATIONS.ko.md)를 확인하십시오.

## 6. 기본 사용

- 수집이 켜진 동안 지원되는 내용을 평소처럼 복사하면 AroDamA가 기록합니다.
- 설정한 전역 단축키로 창을 열고 날짜·종류로 필터링하거나 검색합니다.
- 선택 항목은 `Enter`로 붙여넣고, 가능한 경우 `Shift+Enter`로 일반 텍스트 붙여넣기,
  `Ctrl+Enter`로 자동 입력 없이 복사할 수 있습니다.
- Windows 무결성 경계가 자동 입력을 막으면 AroDamA는 항목만 복사하고 `Ctrl+V`로 직접
  붙여넣으라고 안내할 수 있습니다. 이는 안전하게 실패한 정상 동작이며 대상 앱이 내용을
  받아 저장했다는 증거는 아닙니다.
- 삭제한 항목은 영구 삭제하지 않는 한 무료 버전에서 정확히 24시간 복구할 수 있습니다. 이 로컬
  복구 보관함은 Windows 휴지통과 별개입니다.

## 7. 업데이트

업데이트 확인은 고정 GitHub `latest.json` 주소에 보내는 읽기 전용 요청입니다. 다운로드와 설치는
사용자가 명시적으로 실행해야 하며 AroDamA는 몰래 업데이트하지 않습니다. 업데이트 메타데이터·
서명·아키텍처·공개 릴리스 근거가 서로 다르면 진행하지 마십시오.

## 8. 백업·제거·지원

백업 암호는 PCSSAK도 복구할 수 없습니다. 복원은 병합이 아니라 교체이며, 오래된 스냅샷에 있던
삭제 데이터를 다시 가져올 수 있습니다. 기록이 필요하면 복원이나 제거 전에 별도 안전 백업을
만드십시오.

일반 도움은 [SUPPORT.md](../SUPPORT.md)를 따릅니다. 보안 문제는
[SECURITY.md](../SECURITY.md)에 따라 비공개로 신고하십시오. 공개 Issue에 실제 클립보드 내용,
DB, 백업, 자격증명, 고객 자료나 기밀 파일을 첨부하지 마십시오.
