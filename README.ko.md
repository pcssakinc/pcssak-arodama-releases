# PCssak AroDamA 릴리스

[English](README.md)

> 이 저장소는 PCssak AroDamA의 공개 릴리스·문서·검증·지원·사용자 의견을 위한 곳입니다.
> 자체 애플리케이션 소스는 별도 비공개 저장소에서 관리합니다.

PCssak AroDamA는 복사한 텍스트·서식 있는 글·이미지·실제 파일·제한된 가상 파일과 자주 쓰는
문구를 다시 찾고 안전하게 재사용하도록 돕는 Windows 로컬 우선 클립보드 도구입니다.
이 문서의 대상 버전은 **0.4.2 무료 Early Access**입니다. 복사와 자동 붙여넣기를 구분하고
태그·자료 모음의 사용법과 최초 동의 후 안내를 개선한 패치입니다. 0.4.1의 설치 언어 승계와
업데이트 개선은 유지합니다. 계정·광고·분석·결제·원격 라이선스 활성화·사용자에게 보이는
Pro 기능은 들어 있지 않습니다.

무료 Early Access는 이 버전의 성숙도와 현재 가격을 뜻합니다. 이후 모든 버전이나 기능도 계속
무료라는 약속은 아닙니다.

## 개발 배경과 책임

PCSSAK은 AI의 도움을 받아 개발하는 독립 프로젝트입니다. AroDamA는 전에 복사한 내용을 다시
찾고 현재 작업 흐름을 놓치지 않은 채 재사용하려는 불편에서 출발했습니다. 로컬 기록·명시적인
재사용·복구 제어는 그 목적을 위한 선택입니다. 클립보드 관리자는 이미 존재하는 제품 분야이며,
모든 기능을 처음 발명했거나 모든 구성 요소를 자체 작성했다고 주장하지 않습니다.
제3자 구성 요소의 출처와 권리는 별도 고지를 따릅니다.

AI 활용과 별개로 설계·검토·시험·배포 판단·유지보수의 책임은 PCSSAK에 있습니다. 확인한 결과와
남은 한계를 구분하며, 이 설명이 외부 보안 감사·출처 권리 검토의 완료나 무오류 동작을 뜻하지는
않습니다.

## 공식 다운로드와 업데이트 주소

아래 버전 고정 공식 릴리스나 PCSSAK 다운로드 페이지를 사용하십시오. 현재 안내 확인일은
2026-09-03입니다. 이전 공식 릴리스는 당시 문서·증거를 보존하며, 최신 버전이 바뀌었다고 과거
공식 릴리스가 비공식 자료가 되는 것은 아닙니다.

- GitHub 릴리스: `https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.2`
- 제품 페이지: `https://pcssak.com/arodama`
- 정적 업데이트 주소:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

이 문서는 초안·사전 출시가 아닌 공개 `v0.4.2` 릴리스와 아래 17개 자산을 대상으로 합니다.
버전 고정 릴리스의 정확한 파일명과 해시를 비교하고 GitHub 최신 릴리스는 별도로 확인하십시오.
문서 갱신 자체가 공개 배포·설치본 실행·서명 검증의 완료 근거는 아닙니다. 저장소 파일·PR 산출물·브랜치
미리보기·소스 태그·업무일지·공개되지 않은 초안 자산은 설치본이 아닙니다.

설치 파일명은 다음 둘로 고정합니다.

- `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x64-Setup.exe`
- `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x86-Setup.exe`

64비트 Windows에는 x64를 사용합니다. x86 설치본은 Windows 10 22H2 x86 제한적 호환 후보만
대상으로 합니다. 32비트 Windows 11은 존재하지 않으며 네이티브 ARM64는 지원하지 않습니다.

## 실행 전 무결성 확인

같은 버전 고정 릴리스의 `SHA256SUMS.txt`와 설치본 SHA-256을 비교하십시오.

```powershell
Get-FileHash -Algorithm SHA256 '.\PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x64-Setup.exe'
```

각 설치본에는 같은 이름의 `.sig`가 있습니다. AroDamA는 앱에 내장한 AroDamA 전용 Tauri
공개키로 업데이트 파일의 무결성을 확인합니다. 이 서명은 Windows 게시자 신원 서명이 아닙니다.

v0.4.2 설치본은 **Windows Authenticode 미서명**입니다. Windows가 알 수 없는 게시자,
Microsoft Defender SmartScreen, Smart App Control 또는 조직 정책 경고를 표시할 수 있습니다.
설치를 위해 Windows 보안·백신·방화벽·조직 정책을 끄지 마십시오. 파일명·바이트 크기·SHA-256·
서명·버전 고정 URL·자산 목록 중 하나라도 다르면 중단하십시오.

## 정확한 공개 자산 17개

다음 파일은 버전 고정 GitHub Release에 첨부합니다. 설치본·서명·SBOM·MPL 소스 압축 파일·생성
출처·`latest.json`·체크섬은 Git 저장소 트리에 커밋하지 않습니다.

1. `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x64-Setup.exe`
2. `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x64-Setup.exe.sig`
3. `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x86-Setup.exe`
4. `PCSSAK-AroDamA-Free-Early-Access-v0.4.2-Windows-x86-Setup.exe.sig`
5. `BUILD-PROVENANCE.json`
6. `EULA.md`
7. `latest.json`
8. `LICENSE`
9. `PCSSAK-AroDamA_0.4.2_x64.cdx.json`
10. `PCSSAK-AroDamA_0.4.2_x86.cdx.json`
11. `PCSSAK-AroDamA_0.4.2_MPL-2.0-SOURCE.zip`
12. `PRIVACY.md`
13. `RELEASE-NOTES.md`
14. `SECURITY.md`
15. `SHA256SUMS.txt`
16. `SUPPORT.md`
17. `THIRD-PARTY-NOTICES.txt`

[릴리스 자산 정책](docs/RELEASE-ASSET-POLICY.md)과
[제3자 소스 안내](docs/THIRD-PARTY-SOURCE.md)를 함께 확인하십시오.

## AroDamA가 하는 일

AroDamA는 지원되는 텍스트·HTML·RTF·이미지·실제 파일·제한된 OLE 가상 파일을 기록할 수
있습니다. 날짜·종류 필터, 암호화 검색 후보, 고정 기록, 자주 쓰는 문구, 로컬 Windows OCR,
태그·자료 모음(기존 보드)·순차 붙여넣기 목록과 AroDamA가 관찰하거나 시작한 사건의 로컬 기억 일지를 제공합니다.

### 복사·붙여넣기·정리 구분

- **복사하기**는 지원되는 내용을 클립보드에 넣고 창을 유지합니다. 원하는 앱에서 `Ctrl+V`로
  붙여넣으십시오. 글에는 **서식 없이 복사하기**도 있으며 이미지의 글자 추출과는 다릅니다.
- **이전 앱에 붙여넣기**는 별도 자동 입력입니다. 대상 입력칸을 선택하고 설정한 단축키로
  AroDamA를 연 뒤 항목을 고르십시오. 서식 없는 자동 붙여넣기는 보조 옵션에 있습니다. 안전한
  대상이 없으면 복사 후 수동으로 붙여넣습니다.
- **태그**는 참고·다시 확인 등 기록의 성격을, **자료 모음**은 프로젝트처럼 목적별 묶음을
  나타냅니다. 한 기록을 여러 태그·모음에 연결할 수 있습니다. **모은 기록 보기**는 고정 탭에서
  눌러도 고정 여부와 무관한 전체 기록의 해당 모음을 엽니다.
- 체크 해제는 현재 기록의 연결만, 분류 이름 삭제는 모든 기록의 해당 연결만 없앱니다. 원문은
  삭제하지 않습니다. 자료 모음 개수에는 삭제 보관 중인 자료를 넣지 않습니다. 로컬 정리 기능이며
  클라우드 공유·협업 게시판이 아닙니다.
- 최초 동의 후에는 창이 유지되며 복사 시작·다시 여는 방법을 안내합니다. **안내 닫기**는 안내만
  닫습니다. 숨긴 창은 설정 단축키나 작업표시줄 오른쪽 AroDamA 아이콘으로 다시 열 수 있습니다.

사용자가 직접 삭제한 기록은 무료 버전에서 삭제 시점부터 정확히 24시간까지 복구할 수 있습니다.
암호화 데이터는 삭제 시점부터 최대 30일간 로컬에 남을 수 있지만 v0.4.2에서는 24시간 이후
복구할 수 없습니다. 영구 삭제는 언제나 가능합니다. 이 보관함은 Windows 휴지통과 별개입니다.

핵심 클립보드 내용은 사용자 PC에 머뭅니다. 제한된 네트워크 예외는 고정 GitHub 업데이트 확인과
사용자가 승인한 업데이트, 필요한 WebView2 전달, 사용자가 직접 연 링크·메시지입니다. 민감한
업무에 사용하기 전에 [개인정보 처리 안내](PRIVACY.md), [영문 참고본](PRIVACY.en.md),
[보안 정책](SECURITY.md)을 확인하십시오.

### 개인정보 제어 요약

승인된 [개인정보 처리 안내](PRIVACY.md)의 요약이며, 이번에 코드나 실제 데이터 흐름을 새로
감사한 결과가 아닙니다.

| 구분 | 현재 안내의 핵심 |
| --- | --- |
| 본문과 메타데이터 | 핵심 본문은 Windows 사용자별 DPAPI로 보호하지만 일부 운영 메타데이터는 평문일 수 있습니다. 같은 사용자 권한의 악성 프로그램이나 메모리 평문까지 막지는 못합니다. |
| 기록과 제외 | 민감한 앱은 기록을 일시정지하거나 제외하십시오. 민감 텍스트 차단은 기본 꺼짐이며 오탐·미탐이 있습니다. 제외 설정을 바꿔도 과거 기록은 자동 삭제되지 않습니다. |
| 복구와 보관 | 사용자가 삭제한 기록은 24시간 복구할 수 있지만 암호화된 삭제 자료는 최대 30일 로컬에 남을 수 있습니다. 30일 무료 복구나 모든 활성 기록의 30일 자동 삭제를 뜻하지 않습니다. 영구 삭제도 물리 디스크의 보안 삭제 보장은 아닙니다. |
| 백업 | 암호화 백업 복원은 병합이 아닌 현재 데이터 교체입니다. 과거 백업으로 삭제 자료가 다시 나타날 수 있으며 PCSSAK도 잃어버린 백업 암호를 복구할 수 없습니다. |
| 외부 연결 | AroDamA는 클립보드를 업로드하지 않습니다. 문서화된 업데이트·WebView2 연결과 사용자가 여는 링크는 별도 예외입니다. |

선택적인 대상 앱 기록, 저장 한도, 삭제와 백업의 전체 범위는 원문을 확인하십시오.

## 지원 경계

Windows 11 Home/Pro x64는 주 지원 후보입니다. Windows 10 22H2 Home/Pro x64·x86은 제한적
호환 후보이며, Windows 10 호환 표기는 운영체제 자체의 지원을 연장하지 않습니다. Windows 11
x86, 네이티브 ARM64, Windows S 모드, Windows Server, macOS, Linux, Wine은 지원하지 않습니다.

자동 검증은 깨끗한 PC 설치·업그레이드·제거·절전 복귀, 실제 Office·브라우저·Explorer 작업,
접근성, 모든 백신, 원어민 번역 검토와 관할별 법률 검토를 대신하지 않습니다.
[설치 안내](docs/INSTALLATION.ko.md), [알려진 한계](docs/KNOWN-LIMITATIONS.ko.md),
[품질과 안전](docs/QUALITY-AND-SAFETY.ko.md)을 함께 확인하십시오.

## 보안·지원·법률 문서

- 질문·사용 후기·아이디어: [공개 토론](https://github.com/pcssakinc/pcssak-arodama-releases/discussions)
- 재현 가능한 오류: [구조화된 이슈 양식](https://github.com/pcssakinc/pcssak-arodama-releases/issues/new/choose)
- GitHub 이용이 어려운 일반 지원: `support@pcssak.com`
- 개인정보 문의: `privacy@pcssak.com`
- 악용 가능한 취약점: [비공개 보안 신고](https://github.com/pcssakinc/pcssak-arodama-releases/security/advisories/new). [보안 정책](SECURITY.md)을 따르며 공개 게시물이나 일반 지원메일에 상세 내용을 보내지 않습니다.
- 설치·사용 조건: [LICENSE](LICENSE), [EULA.md](EULA.md)
- 현재 릴리스 노트: [RELEASE-NOTES.md](RELEASE-NOTES.md)
- 의견 처리·기여 권리·보상 경계: [기여 원칙](CONTRIBUTING.md)

최상위 EULA와 개인정보 문서는 0.4.1에 동봉된 2026-09-01 승인본을 0.4.2에서도 변경 없이
유지합니다. 이번 화면 개선만을 이유로 다시 동의를 요구하지 않습니다. 지원·기여 안내는 운영
중 갱신될 수 있지만 이미 공개한 릴리스 첨부 문서를 교체하지 않습니다. MPL 대응 소스 자산은
해당 제3자 구성 요소의 소스 제공이며, 비공개 애플리케이션 전체 소스 공개가 아닙니다.

공개 이슈에 클립보드 본문·DB·백업 파일이나 암호·자격증명·개인키·개인 경로·고객 자료·업무
기밀을 올리지 마십시오.
