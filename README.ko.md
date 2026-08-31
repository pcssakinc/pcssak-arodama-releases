# PCssak AroDamA 릴리스

[English](README.md)

> 이 저장소는 PCssak AroDamA의 공개 릴리스·문서·검증·지원·사용자 의견을 위한 곳입니다.
> 자체 애플리케이션 소스는 별도 비공개 저장소에서 관리합니다.

PCssak AroDamA는 복사한 텍스트·서식 있는 글·이미지·실제 파일·제한된 가상 파일과 자주 쓰는
문구를 다시 찾고 안전하게 재사용하도록 돕는 Windows 로컬 우선 클립보드 도구입니다.
`0.4.0`은 첫 **무료 Early Access**입니다. 계정·광고·분석·결제·원격 라이선스 활성화·사용자에게
보이는 Pro 기능은 들어 있지 않습니다.

무료 Early Access는 이 버전의 성숙도와 현재 가격을 뜻합니다. 이후 모든 버전이나 기능도 계속
무료라는 약속은 아닙니다.

## 공식 다운로드와 업데이트 주소

공개 관문이 열린 뒤에는 이 저장소의 버전 고정 릴리스나 PCSSAK 공식 다운로드 페이지만
사용하십시오.

- GitHub 릴리스: `https://github.com/pcssakinc/pcssak-arodama-releases/releases/tag/v0.4.0`
- 제품 페이지: `https://pcssak.com/arodama`
- 정적 업데이트 주소:
  `https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

`v0.4.0`이 초안·Prerelease가 아닌 공개 GitHub Latest로 게시되고, 아래 정확한 17개 자산의
익명 재다운로드 검증이 통과한 경우에만 공식 다운로드입니다. 저장소 파일·PR 산출물·브랜치
미리보기·소스 태그·업무일지·공개되지 않은 초안 자산은 설치본이 아닙니다.

설치 파일명은 다음 둘로 고정합니다.

- `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe`
- `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x86-Setup.exe`

64비트 Windows에는 x64를 사용합니다. x86 설치본은 Windows 10 22H2 x86 제한적 호환 후보만
대상으로 합니다. 32비트 Windows 11은 존재하지 않으며 네이티브 ARM64는 지원하지 않습니다.

## 실행 전 무결성 확인

같은 버전 고정 릴리스의 `SHA256SUMS.txt`와 설치본 SHA-256을 비교하십시오.

```powershell
Get-FileHash -Algorithm SHA256 '.\PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe'
```

각 설치본에는 같은 이름의 `.sig`가 있습니다. AroDamA는 앱에 내장한 AroDamA 전용 Tauri
공개키로 업데이트 파일의 무결성을 확인합니다. 이 서명은 Windows 게시자 신원 서명이 아닙니다.

v0.4.0 설치본은 **Windows Authenticode 미서명**입니다. Windows가 알 수 없는 게시자,
Microsoft Defender SmartScreen, Smart App Control 또는 조직 정책 경고를 표시할 수 있습니다.
설치를 위해 Windows 보안·백신·방화벽·조직 정책을 끄지 마십시오. 파일명·바이트 크기·SHA-256·
서명·버전 고정 URL·자산 목록 중 하나라도 다르면 중단하십시오.

## 정확한 공개 자산 17개

다음 파일은 버전 고정 GitHub Release에 첨부합니다. 설치본·서명·SBOM·MPL 소스 압축 파일·생성
출처·`latest.json`·체크섬은 Git 저장소 트리에 커밋하지 않습니다.

1. `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe`
2. `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x64-Setup.exe.sig`
3. `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x86-Setup.exe`
4. `PCSSAK-AroDamA-Free-Early-Access-v0.4.0-Windows-x86-Setup.exe.sig`
5. `BUILD-PROVENANCE.json`
6. `EULA.md`
7. `latest.json`
8. `LICENSE`
9. `PCSSAK-AroDamA_0.4.0_x64.cdx.json`
10. `PCSSAK-AroDamA_0.4.0_x86.cdx.json`
11. `PCSSAK-AroDamA_0.4.0_MPL-2.0-SOURCE.zip`
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
태그·보드·순차 붙여넣기 목록과 AroDamA가 관찰하거나 시작한 사건의 로컬 기억 일지를 제공합니다.

사용자가 직접 삭제한 기록은 무료 버전에서 삭제 시점부터 정확히 24시간까지 복구할 수 있습니다.
암호화 데이터는 삭제 시점부터 최대 30일간 로컬에 남을 수 있지만 v0.4.0에서는 24시간 이후
복구할 수 없습니다. 영구 삭제는 언제나 가능합니다. 이 보관함은 Windows 휴지통과 별개입니다.

핵심 클립보드 내용은 사용자 PC에 머뭅니다. 제한된 네트워크 예외는 고정 GitHub 업데이트 확인과
사용자가 승인한 업데이트, 필요한 WebView2 전달, 사용자가 직접 연 링크·메시지입니다. 민감한
업무에 사용하기 전에 [개인정보 처리 안내](PRIVACY.md), [영문 참고본](PRIVACY.en.md),
[보안 정책](SECURITY.md)을 확인하십시오.

## 지원 경계

Windows 11 Home/Pro x64는 주 지원 후보입니다. Windows 10 22H2 Home/Pro x64·x86은 제한적
호환 후보이며, Windows 10 호환 표기는 운영체제 자체의 지원을 연장하지 않습니다. Windows 11
x86, 네이티브 ARM64, Windows S 모드, Windows Server, macOS, Linux, Wine은 지원하지 않습니다.

자동 검증은 깨끗한 PC 설치·업그레이드·제거·절전 복귀, 실제 Office·브라우저·Explorer 작업,
접근성, 모든 백신, 원어민 번역 검토와 관할별 법률 검토를 대신하지 않습니다.
[설치 안내](docs/INSTALLATION.ko.md), [알려진 한계](docs/KNOWN-LIMITATIONS.ko.md),
[품질과 안전](docs/QUALITY-AND-SAFETY.ko.md)을 함께 확인하십시오.

## 보안·지원·법률 문서

- 일반 지원: `support@pcssak.com`
- 개인정보 문의: `privacy@pcssak.com`
- 보안 제보: [SECURITY.md](SECURITY.md)에 따라 GitHub 비공개 보안 신고를 사용합니다.
- 설치·사용 조건: [LICENSE](LICENSE), [EULA.md](EULA.md)
- 현재 릴리스 노트: [RELEASE-NOTES.md](RELEASE-NOTES.md)

공개 이슈에 클립보드 본문·DB·백업 파일이나 암호·자격증명·개인키·개인 경로·고객 자료·업무
기밀을 올리지 마십시오.
