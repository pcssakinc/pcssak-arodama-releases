# PCSSAK AroDamA 0.4.0 Free Early Access

- Release channel: Free Early Access
- Release type: first public Windows release
- Architectures: Windows x64 and x86
- Paid features: not included or visible
- Windows Authenticode: not signed
- Tauri updater integrity signature: included with each update installer

## 한국어

AroDamA는 한 번 복사한 텍스트·이미지·파일을 날짜와 출처 흐름으로 다시 찾고 안전하게
재사용하는 로컬 우선 Windows 클립보드 도구입니다. 0.4.0은 첫 공개 무료 Early Access로,
계정·광고·분석·결제·원격 라이선스 활성화와 사용자에게 보이는 Pro 기능이 없습니다.

### 주요 기능

- 텍스트, HTML·RTF 서식, 이미지, 실제 파일과 제한된 OLE 가상 파일 기록
- 날짜·종류·출처·복사/붙여넣기 이용 여부·태그·보드 필터와 암호화 전체 본문 검색
- 고정 기록, 자주 쓰는 문구와 `{date}`, `{time}`, `{datetime}`, `{clipboard}` 자동 입력
- AroDamA가 관찰한 복사와 앱에서 수행한 복사·자동 붙여넣기 결과를 구분하는 기억 일지
- 로컬 Windows OCR, 태그·보드, 순차 붙여넣기 목록
- 개별·선택·전체·날짜 범위 삭제와 AroDamA 전용 삭제 기록 보관함
- 삭제 시점부터 24시간 무료 복구, 이후 현재 버전에서는 복구 불가, 최대 30일 로컬 암호화 보관
- 암호화 휴대용 백업과 검증 후 교체·실패 시 롤백
- 캡처 일시정지, 제외 앱, 일부 비밀번호 관리자 기본 보호와 선택형 민감 텍스트 차단
- 영어·한국어·일본어·독일어·스페인어·브라질 포르투갈어·튀르키예어·프랑스어 UI
- x64·x86 설치 파일, 설치 언어 선택, 설치 EULA, 서명 검증 GitHub 업데이트

### 설치 전 확인

현재 설치 파일은 Windows Authenticode 미서명입니다. Windows가 `알 수 없는 게시자` 또는
SmartScreen 경고를 표시할 수 있으며 기업 정책에서 실행을 막을 수 있습니다. 공식
PCSSAK 페이지의 고정 `v0.4.0` URL과 SHA-256을 확인하십시오. Tauri `.sig`는 앱 내부
업데이트 파일의 무결성을 검증하지만 Windows 게시자 신원을 증명하지 않습니다.

처음 실행하면 개인정보 안내를 확인하고 캡처 시작을 직접 선택하기 전까지 기록과 자동
업데이트 확인이 멈춰 있습니다. 비밀번호·인증 코드·금융·의료·신원·업무 기밀을 다룰 때는
일시정지와 제외 앱을 사용하십시오. 앱 제거만으로 로컬 데이터가 자동 삭제된다고 가정하지
마십시오.

### 알려진 한계

- 관리자 권한 앱에는 Windows UIPI 때문에 자동 붙여넣기가 실패할 수 있습니다.
- 클립보드 민감도 필터와 비밀번호 관리자 이름 필터는 모든 비밀을 탐지하지 못합니다.
- OCR은 설치된 Windows 언어 팩을 사용하며 정확성을 보장하지 않습니다.
- 기억 일지는 신뢰 시각원이나 변조 방지 서명을 사용하지 않아 감사 로그·법적 증거가 아닙니다.
- 실제 깨끗한 Windows 10/11 Home/Pro 전체 하드웨어 조합과 모든 백신·업무 앱 호환을 보증하지 않습니다.

지원: `support@pcssak.com`
개인정보: `privacy@pcssak.com`

## English

AroDamA is a local-first Windows clipboard tool that helps users find and safely reuse text, images,
and files they copied earlier, organized by time and source context. Version 0.4.0 is the first public
Free Early Access release. It has no account, ads, analytics, payment, remote license activation, or
user-visible Pro features.

### Highlights

- Records text, HTML or RTF, images, physical files, and constrained OLE virtual files.
- Filters by date, kind, source, copy or paste usage, tag, and board, with encrypted full-text candidate search.
- Includes pinned records, quick text, local Windows OCR, tags, boards, and an ordered paste queue.
- Distinguishes observed copies from AroDamA copy and automatic-paste attempts in a local memory timeline.
- Supports individual, selected, full, and date-range deletion in an AroDamA deleted-record store.
- Offers free restore for 24 hours from deletion; later restore is unavailable in this build, while encrypted
  data may remain locally for up to 30 days from deletion.
- Provides password-encrypted portable backup with validation and rollback.
- Includes capture pause, excluded apps, narrow password-manager protection, and an optional sensitive-text filter.
- Provides eight UI and installer languages and separate Windows x64 and x86 installers.
- Checks GitHub updates with mandatory Tauri integrity signatures after first-run consent.

### Before installation

The installers are not signed with Windows Authenticode. Windows may show Unknown Publisher or
SmartScreen warnings, and organization policy may block execution. Verify the fixed official `v0.4.0`
URL and SHA-256. A Tauri `.sig` protects in-app update integrity but does not authenticate the Windows
publisher.

Capture and automatic update checks remain paused until the user reviews the first-run privacy notice
and explicitly starts capture. Pause capture and exclude applications when handling credentials,
financial, medical, identity, or confidential work data. Uninstalling does not necessarily delete local data.

Support: `support@pcssak.com`
Privacy: `privacy@pcssak.com`
