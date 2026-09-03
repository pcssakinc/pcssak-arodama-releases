# PCSSAK AroDamA Free Early Access 개인정보 처리 안내

- 문서 버전: 1.0
- 최종 수정일: 2026-09-01
- 적용 대상: PCSSAK AroDamA Free Early Access for Windows
- 운영자 표시명: PCSSAK
- 개인정보 문의: `privacy@pcssak.com`
- 일반 지원: `support@pcssak.com`

> 이 문서는 국문 기준본이며 현재 소스 코드에서 확인할 수 있는 데이터 처리만 설명합니다.
> 다른 언어 번역본과 해석이 다를 경우 적용 법률이 허용하는 범위에서 이 국문을 기준으로
> 합니다. 사용자의 상시 거주지에서 강행되는 개인정보 보호법·소비자 보호법과 그 밖의
> 포기할 수 없는 법정 권리는 이 안내보다 우선합니다. 이 국문 기준본과 번역본은 아직
> 관할별 전문 법률 검토를 완료하지 않은 보수적 운영 초안이며 법률 자문을 대신하지 않습니다.
> 번역본은 사용자의 이해를 돕기 위한 참고 자료입니다.

## 1. 처리 원칙과 첫 실행 동의

PCSSAK AroDamA는 로컬 우선 Windows 앱입니다. 현재 무료 Early Access에는 계정, 광고,
사용 분석, 클라우드 동기화, 원격 충돌 보고, 결제 또는 원격 라이선스 검증 기능이 없습니다.
앱이 처리하는 클립보드 기록과 설정은 사용자의 PC 안에서 관리됩니다. 다만 아래 6절처럼
업데이트 확인·사용자가 승인한 다운로드와 WebView2 준비에는 제한된 네트워크 연결이 있습니다.

첫 실행에서는 EULA와 이 안내를 확인하기 전까지 클립보드 캡처와 자동 업데이트 확인이
일시정지됩니다. 사용자가 두 원문을 앱 안에서 열어보고, 문서 확인란과 시작 버튼을 명시적으로
선택하면 안내 완료와 캡처 재개를 함께 저장합니다. 현재 설정에는 동의한 EULA·개인정보 안내
버전, 문서 묶음의 지문과 로컬 확인 시각을 저장하며, 원격 계정이나 서버로 동의 기록을 보내지
않습니다. 중요한 사용권 또는 데이터 처리 변경은 문서 버전을 올리고 다시 확인하기 전까지
캡처를 멈춥니다. 설치기에도 같은 EULA가 표시됩니다.

## 2. 기능 사용 시 처리되는 정보

| 범주 | 예시 | 목적 |
|---|---|---|
| 클립보드 콘텐츠 | 텍스트, HTML·RTF 서식, 이미지, 실제 파일 경로 목록, 앱이 메모리로 제공한 가상 파일 이름·본문 | 기록, 검색, 미리보기, 다시 붙여넣기 |
| 출처·대상 정보 | 클립보드 소유 프로세스 이름, 사용자가 선택적으로 허용한 자동 붙여넣기 대상 실행 파일 이름 | 검색, 출처 표시, 제외 앱 적용, 날짜별 기억 일지 |
| 자주 쓰는 문구 | 사용자가 작성한 이름과 본문 | 반복 문구 재사용 |
| 기억 정리 데이터 | 사용자가 추출·저장한 OCR 글자, 태그·보드 이름과 소속, 이미지 썸네일, 순차 붙여넣기 순서 | 이미지 글자 검색, 분류, 순서대로 재사용 |
| 휴대용 백업 | 내보내기 시점의 활성 기록·삭제 기록 보관함·문구·기억 사건·OCR·정리 데이터가 포함될 수 있는 암호화 파일 | 같은 PC 복구 또는 다른 PC로 데이터 이전 |
| 설정 | 단축키, 테마, 언어, 보관 한도, 제외 앱, 캡처 일시정지, 이미지·파일 캡처, 초기 안내 완료 여부 | 사용자 환경 유지 |
| 운영 메타데이터 | 항목·사건 식별자, 종류, 시작·완료 시각, 결과, 횟수, 출처 구분, 붙여넣기 방식, 크기, 핀 여부, 중복 판별값 | 정렬, 기억 일지, 실패·중단 구분, 보관 한도, 무결성과 중복 방지 |

자주 쓰는 문구의 `{clipboard}` 자동 입력은 미리보기 또는 붙여넣기 시점의 현재 Windows
텍스트만 읽습니다. 이 명시적 읽기 자체로 기록 DB에 추가하지 않으며, 설정된 텍스트 크기
한도를 넘으면 처리를 거부합니다.

`붙여넣기 대상 앱 기억`은 기본적으로 꺼져 있습니다. 사용자가 켜면 자동 붙여넣기 대상의
실행 파일 기본 이름(예: `notepad.exe`)만 사건에 저장하고 문서·창 제목, 전체 경로, PID 또는
HWND는 저장하지 않습니다. 설정을 끄면 이후 사건부터 기록하지 않지만 이미 저장된 이름을
자동 삭제하지는 않습니다. 사용자는 두 단계 확인을 거쳐 현재 DB에서 과거 대상 앱 이름만
즉시 영구 삭제할 수 있습니다. 사건의 날짜·종류·결과·횟수 등 나머지 일지는 유지되며 삭제한
이름은 앱에서 복구할 수 없습니다. 이 기능은 복사 출처 앱 기록을 지우지 않습니다. 복사 출처를
저장하지 않으려면 앱을 제외 목록에 추가하거나 캡처를 일시정지해야 합니다. 제외 앱과 활성화된
대표 비밀번호 관리자 보호 대상은 이후 자동 붙여넣기 대상 이름에도 적용되지만, 설정 변경이
이미 저장된 기록을 자동 검사하거나 삭제하지는 않습니다.

기본적으로 꺼져 있는 `민감할 가능성이 있는 텍스트 차단`을 켜면 개인 키 블록, 인식 가능한
접근 토큰과 일반 결제 카드 형식 중 Luhn 검사를 통과한 번호를 이 PC에서만 좁게 검사해 저장 전에
건너뜁니다. 오탐과 미탐이 가능하고 기존 기록을 검사하거나 삭제하지 않으므로 비밀번호, 일회용
인증 코드, 주민등록·신원, 금융, 의료 또는 업무상 기밀이 기록될 가능성은 여전히 있습니다.

## 3. 저장, 암호화와 복구 보호

새 데이터는 `%LOCALAPPDATA%\PCssak\AroDamA`에 저장됩니다. 새 경로가 비어 있을 때만 기존
`%APPDATA%\ClipDeck`의 설정과 DB를 복사하며 기존 파일은 보존합니다.

- 활성 기록과 삭제 기록 보관함의 클립보드 본문·미리보기·HTML·RTF·이미지·실제/가상 파일 목록,
  자주 쓰는 문구 본문, OCR 결과, 태그·보드 이름과 이미지 썸네일은 Windows DPAPI의 현재 사용자
  범위로 보호됩니다. 원칙적으로 같은 Windows 사용자 문맥에서만 복호화됩니다.
- 검색·미리보기·붙여넣기와 백업 내보내기를 위해 복호화된 내용이 앱 실행 중 프로세스 메모리에
  존재할 수 있습니다. 사용이 끝난 소유 버퍼는 가능한 범위에서 덮어씁니다.
- 중복 판별값은 설치마다 생성한 비밀키로 HMAC-SHA-256을 계산합니다. 이 키는
  `dedup-key.bin`에 DPAPI로 보호해 저장하지만 HMAC은 콘텐츠 암호화를 대신하지 않습니다.
- 전체 본문 검색 후보 필터는 별도의 설치별 DPAPI 보호 키로 HMAC을 계산합니다. 평문 단어나 본문은
  저장하지 않지만 길이·접근 패턴 같은 모든 부가정보 노출을 없애는 암호화 검색은 아닙니다. 실제
  일치 여부는 후보 항목을 메모리에서 개별 복호화해 확인합니다.
- 현재 항목의 출처 앱, 설정 파일, DB 구조, 자주 쓰는 문구 이름과 항목·사건의 식별자, 종류, 시각,
  결과, 횟수, 출처 구분, 붙여넣기 방식, 보관 시각, 크기, 핀과 정리 관계 같은 운영 메타데이터는
  평문일 수 있습니다. 사건 안의 복사 출처 또는 선택적으로 저장한 대상 실행 파일 이름은 DPAPI로
  보호됩니다.
- DPAPI는 PC가 잠금 해제된 상태에서 같은 사용자 권한으로 실행되는 악성 프로그램, 화면·키 입력
  가로채기, 메모리 공격, 사용자가 허용한 원격 제어 또는 잠금 해제된 장치의 물리적 접근을 방어하지
  않습니다.

기존 DB는 쓰기 전에 SQLite 무결성 검사로 확인합니다. 스키마 또는 HMAC 전환이 필요하면 DB 내부의
무작위 전환 표식과 스냅샷 SHA-256으로 정확히 연결한 일관 복구본을 `recovery` 하위에 만듭니다.
전환 도중 종료되면 다음 시작에서 상태를 이어가고, 현재 DB·스키마·필수 열과 표·키 표식 및 WAL
반영이 모두 검증된 경우에만 연결된 복구본을 삭제합니다. 표식과 연결되지 않았거나 출처를 확정할
수 없는 복구본은 자동 삭제하지 않습니다. 이는 충돌 복구 장치이지 외부 백업 서비스가 아닙니다.
실제 사용자 데이터와 실패·복구 시나리오를 최종 시험하기 전에는 두 데이터 폴더를 직접 이동하거나
삭제하지 마십시오.

스키마 v5에는 사건별 과거 기록이 없었습니다. v6 전환은 당시 마지막 복사 시각과, 기존 자동
붙여넣기 누계가 있으면 마지막 붙여넣기 시각의 요약 사건만 만듭니다. 과거 개별 시각, 대상 앱,
붙여넣기 방식과 결과를 추정하지 않습니다. 스키마 v8은 RTF, 등록 이미지, 가상 파일, 원본의
`CanUploadToCloudClipboard` 상태, 검색 후보 필터, OCR, 태그·보드와 순차 붙여넣기 목록을 같은
`memory_id` 수명주기에 연결합니다.

OCR은 설치된 Windows OCR 언어 팩으로 이 PC에서만 실행하며 이미지를 네트워크로 보내지 않습니다.
결과는 부정확할 수 있고 사용자가 삭제할 수 있으며, 원본 문서의 공식 전사본으로 간주해서는 안 됩니다.

휴대용 백업은 SQLite 일관 스냅샷의 논리 레코드를 현재 Windows 사용자 문맥에서 복호화하고,
사용자가 입력한 암호로 Argon2id와 XChaCha20-Poly1305를 사용해 즉시 다시 암호화합니다. 백업 암호와
파생 키는 저장하거나 서버로 보내지 않고 작업 뒤 가능한 범위에서 메모리를 덮어씁니다. 암호를 잊거나
파일을 잃으면 PCSSAK도 복구할 수 없습니다. 백업에는 내보낸 시점의 활성·삭제 기록, 문구, 사건,
OCR과 정리 데이터가 포함될 수 있으므로 저장 위치·외장 장치·동기화 서비스의 보안과 보유 기간은
사용자가 관리해야 합니다. 가져오기는 격리 후보를 검증한 뒤 현재 DB에 병합하지 않고 교체하며,
과거 백업을 복원하면 현재 앱에서 삭제했던 데이터가 백업 시점 상태에 따라 다시 나타날 수 있습니다.

## 4. 보관, 삭제와 복구 기간

사용자가 정한 보관 개수 한도는 정리하지 않은 일반 기록에 적용됩니다. 핀, OCR, 태그, 보드 또는
순차 붙여넣기 목록에 연결된 기록은 자동 개수 정리에서 보호되므로 실제 기록 수가 설정값보다 많을
수 있습니다. 보호 여부와 관계없이 모든 데이터는 별도의 512MB 논리 저장량 한도에 포함됩니다.
보호되지 않은 오래된 기록의 자동 개수 정리는 수동 삭제용 보관함을 거치지 않고 연결 사건도 제거합니다.

사용자가 기록을 개별 삭제하거나 기록 비우기를 실행하면 해당 기록과 연결된 사건은 Windows 휴지통이
아닌 AroDamA의 로컬 삭제 기록 보관함 수명주기로 이동합니다. 날짜 범위 삭제는 기록의 현지 복사 날짜를
기준으로 시작일과 종료일을 모두 포함하며 고정 기록을 보호합니다. 미래 날짜는 예약 삭제가 아닙니다.

- 삭제 시점부터 정확히 24시간까지 무료로 복구할 수 있습니다.
- 24시간이 지나면 현재 무료 Early Access에서는 복구할 수 없지만, 콘텐츠와 사건은 같은 PC의 같은
  Windows 사용자 문맥에서 삭제 시점부터 최대 30일 동안 로컬 암호화 상태로 남을 수 있습니다. 현재
  제품에는 이를 다시 여는 Pro·결제·판매·원격 라이선스 활성화 기능이나 UI가 없습니다.
- 삭제 보관함과 사건도 기록·핀·문구와 같은 512MB 논리 저장량 한도에 포함됩니다.
- 사용자는 언제든 더 일찍 영구 삭제할 수 있습니다. 정확히 30일이 된 항목은 다음 보관함 정리 때 앱
  DB에서 제거되며 앱에서 복구할 수 없습니다.

만료 또는 영구 삭제는 현재 DB의 콘텐츠와 연결 사건을 제거하는 앱 수준 동작이지 물리 디스크의 보안
삭제가 아닙니다. SQLite 빈 페이지·WAL, 마이그레이션 실패 시 보존한 복구본, Windows·기업 백업,
디스크 복구 영역이나 제3자 동기화 사본에는 흔적이 남을 수 있습니다. 저장된 대상 앱 이름 삭제도
현재 DB의 해당 암호문만 영구 삭제하며 별도 사본을 덮어쓰지 않습니다.

24시간 복구와 30일 만료, 사건 시각은 로컬 Windows 시스템 시각을 기준으로 합니다. 시스템 시각을
크게 바꾸면 표시·복구·만료 경계에 영향을 줄 수 있습니다. 기억 일지는 신뢰 시각원으로 서명된 변조
방지 감사 로그나 법적 증거가 아닙니다. 삭제 보관함과 휴대용 백업은 서로 별개이며, 분실한 DB나
백업 파일·암호를 AroDamA가 대신 복구할 수 없습니다.

일반 제거는 `%LOCALAPPDATA%\PCssak\AroDamA`의 기록과 설정을 보존합니다. 제거기에서 사용자가
`앱 데이터 삭제`를 명시적으로 선택한 경우에만 AroDamA가 관리하는 설정, 데이터베이스, 보호 키,
마이그레이션 복구본과 검증된 복원 후보를 정확히 제한된 목록에 따라 삭제합니다. 이 경우에도
공유 `PCssak\AroDamA` 루트를 재귀 삭제하지 않으며, 사용자가 내보낸 `.arodama-backup` 파일,
다른 위치의 백업·롤백 사본, 동기화 사본 또는 회사·기관의 보존 사본은 삭제하지 않습니다.
원하는 경우 이러한 사본은 별도로 확인하고 삭제해야 합니다.

## 5. 민감정보 기록 최소화와 사용자 통제

AroDamA는 `Clipboard Viewer Ignore`, `ExcludeClipboardContentFromMonitorProcessing`,
`CanIncludeInClipboardHistory=0`처럼 Windows 클립보드에 게시된 확인 가능한 제외 의사를 존중합니다.
모든 비밀번호 관리자와 업무 앱이 이 표식을 제공하는 것은 아니므로 민감정보 미수집을 절대 보장하지
않습니다.

Windows 등록 형식 `CanUploadToCloudClipboard`의 없음, DWORD 1(허용), DWORD 0(금지) 세 상태를
보존합니다. 저장한 항목을 다시 복사하거나 붙여넣을 때 원래 상태를 먼저 재게시해 원본 앱의 클라우드
업로드 금지 의사를 없애지 않습니다. 이 표식 보존과 관계없이 AroDamA 자체는 콘텐츠를 업로드하지 않고,
다른 앱이나 Windows 전체의 동기화 설정을 변경하지 않습니다. 비정상 길이 또는 0·1 이외 값은 허용으로
추정하지 않고 캡처를 거부합니다.

대표 비밀번호 관리자 기본 보호는 `1password.exe`, `bitwarden.exe`, `keepass.exe`,
`keepassxc.exe`와 정확히 일치하는 일부 Windows 실행 파일 기본 이름만 새 payload를 읽기 전에
건너뛰는 편의 필터입니다. 모든 버전, 확장 프로그램, 중개 프로세스나 관리자 권한 앱을 식별하는 보안
경계가 아닙니다. 민감 텍스트 차단도 좁은 로컬 규칙이며 원문이나 차단 해시를 로그, DB 또는 네트워크로
보내지 않습니다. 두 기능 모두 이미 저장된 기록을 자동 삭제하지 않습니다.

사용자는 캡처를 일시정지하고, 앱을 제외하고, 이미지·파일 캡처를 끄고, 대상 앱 기억을 꺼 둔 채 사용할
수 있습니다. 저장된 대상 이름과 기록을 삭제하고, 삭제 보관함을 비우고, 한도를 낮추고, 로컬 데이터를
직접 제거할 수도 있습니다. 특히 비밀번호·인증 코드·개인정보를 다룰 때는 캡처를 멈추고, 기본 목록에
없는 보안 앱을 제외하며, 공유 PC에서는 별도 Windows 계정을 사용하고 자리를 비울 때 화면을 잠그며,
기록을 주기적으로 검토·삭제하는 것을 권장합니다.

## 6. 네트워크 연결과 제3자 처리

AroDamA는 클립보드 콘텐츠, 로컬 파일 이름·경로, 자주 쓰는 문구, OCR 이미지·결과, 기억 일지 또는
휴대용 백업을 PCSSAK이나 업데이트 서버로 업로드하지 않습니다. 첫 실행 안내에 동의한 뒤 다음 공식
GitHub Release 메타데이터 주소에 HTTPS로 연결해 새 버전을 확인할 수 있습니다.

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

업데이트 확인은 현재 앱 버전과 서버가 제공하는 버전, 릴리스 안내, 다운로드 URL과 무결성 서명을
비교합니다. 설치 파일은 사용자가 업데이트 설치를 명시적으로 선택한 경우에만 내려받습니다. GitHub는
IP 주소, 접속 시각, 사용자 에이전트 같은 표준 요청 정보를 자체 개인정보 정책에 따라 처리할 수 있으며,
AroDamA는 요청에 클립보드 콘텐츠나 사용 이력을 추가하지 않습니다. GitHub의 처리 지역과 보유 기간은
GitHub의 정책을 따릅니다.

대상 PC에 Microsoft Edge WebView2 Runtime이 없으면 Tauri NSIS 설치 과정이 Microsoft에서 WebView2
부트스트래퍼를 내려받을 수 있습니다. 이는 앱의 클립보드 데이터 전송 기능이 아니며 Microsoft의 정책이
적용됩니다. 사용자가 OneDrive 등 제3자 동기화 앱이 관리하는 폴더에 암호화 백업을 저장하면 해당 앱이
자체 설정과 개인정보 정책에 따라 파일을 업로드할 수 있습니다.

향후 계정, 결제, 원격 지원, 분석 또는 충돌 보고를 도입하면 실제 전송 항목, 목적, 보유 기간, 서비스
제공자와 국제 전송 가능성을 먼저 이 문서에 반영하고 적용 법률상 필요한 동의를 받습니다.

## 7. 사용자 권리, 문의와 방침 변경

PCSSAK 계정이나 중앙 클립보드 DB가 없으므로 PCSSAK은 사용자를 대신해 로컬 클립보드 콘텐츠를 원격으로
조회, 내보내기, 수정 또는 삭제할 수 없습니다. 사용자는 5절에 설명한 앱 기능과 공식 삭제 안내를 사용해
자신의 로컬 데이터를 직접 통제합니다.

개인정보 문의: `privacy@pcssak.com`

일반 지원: `support@pcssak.com`

보안 취약점, 클립보드 내용, DB, 자격 증명 또는 신원을 식별할 수 있는 로그를 공개 Issue에 게시하지
마십시오. 공식 공개 배포 저장소의 GitHub 비공개 취약점 신고 기능을 사용하십시오.

PCSSAK은 현재 제품과 웹사이트의 운영 표시명이며 이 표기만으로 특정 국가의 법인 또는 등록 상호가 있음을
주장하지 않습니다. 등록 판매자 정보나 별도 판매 조건이 필요한 유료 판매는 그 정보와 조건을 확정·공개한
뒤에만 시작합니다.

방침이 변경되면 문서 상단의 날짜와 버전을 변경합니다. 데이터 처리 범위가 실질적으로 확대되는 경우 적용
전에 사용자에게 알리고 필요한 경우 다시 동의받습니다.

---

# PCSSAK AroDamA Free Early Access Privacy Notice

- Document version: 1.0
- Last updated: 2026-09-01
- Applies to: PCSSAK AroDamA Free Early Access for Windows
- Operator display name: PCSSAK
- Privacy contact: `privacy@pcssak.com`
- General support: `support@pcssak.com`

> This is an English reference translation of the Korean controlling text. If translations differ,
> the Korean text controls only to the extent permitted by applicable law. Mandatory privacy and
> consumer-protection laws, and other non-waivable rights in the user's place of residence, prevail.
> This notice has not yet received professional legal review for every jurisdiction, is a conservative
> operational draft, and is not legal advice.

## 1. Processing principles and first-run consent

PCSSAK AroDamA is a local-first Windows application. The current Free Early Access has no account,
advertising, usage analytics, cloud synchronization, remote crash reporting, payment, or remote license
validation. Clipboard records and settings are managed on the user's PC. Limited network access for
update checks, user-approved downloads, and WebView2 preparation is described in Section 6.

On first launch, clipboard capture and automatic update checks remain paused until the user can open
and review the EULA and this notice in the app, select the document-confirmation checkbox, and explicitly
press the start button. The app then stores completion and capture resumption together. Local settings
record the accepted EULA and privacy-notice versions, the document-set fingerprint, and local acceptance
time; no acceptance record is sent to an account or server. A material change to license or processing
raises the document version and pauses capture pending renewed review. The installer presents the same
EULA.

## 2. Data processed when features are used

| Category | Examples | Purpose |
|---|---|---|
| Clipboard content | Text, HTML/RTF formatting, images, physical-file path lists, and virtual-file names and bytes supplied in memory | History, search, preview, and reuse |
| Source and target | Clipboard-owner process name and, only after opt-in, the automatic-paste target executable name | Search, source display, exclusions, and dated memory timeline |
| Quick text | User-created name and body | Reuse of repeated text |
| Memory organization | User-requested OCR text, tags, board names and membership, image thumbnails, and paste-queue order | Image-text search, classification, and ordered reuse |
| Portable backup | Encrypted file that may contain active and deleted records, quick text, events, OCR, and organization data as of export | Recovery or transfer to another PC |
| Settings | Hotkeys, theme, language, retention limits, excluded apps, pause state, image/file capture, and first-run completion | Preserve user preferences |
| Operational metadata | Item/event identifiers, type, start/completion times, result, count, provenance, paste method, size, pin state, and deduplication value | Sorting, timeline, integrity, retention, and deduplication |

The `{clipboard}` quick-text variable reads current Windows text only when previewed or used. That
explicit read does not by itself add a history record and is refused above the configured text limit.

Remembering automatic-paste target apps is off by default. If enabled, AroDamA stores only the executable
base name (for example, `notepad.exe`), not a document or window title, full path, PID, or HWND. Turning
the setting off affects future events and does not delete prior names. A two-step command permanently
removes only prior target-app names from the current database while retaining dates, event types, results,
and counts; the removed name cannot be restored in the app. This does not remove clipboard source-app
names. To avoid recording a source, add the app to Excluded apps or pause capture. Exclusions and enabled
default password-manager protection also apply to future paste-target names, but changing settings does
not retrospectively inspect or delete stored data.

The optional sensitive-text blocker is off by default. If enabled, narrow local rules skip recognized
private-key blocks, recognizable access-token formats, and ordinary payment-card formats that pass a Luhn
check before storage. False positives and false negatives are possible, and existing records are neither
scanned nor deleted. Passwords, one-time codes, identity, financial, medical, or confidential work data
may therefore still be captured.

## 3. Storage, encryption, and recovery protection

New data is stored under `%LOCALAPPDATA%\PCssak\AroDamA`. Only when that location is empty may AroDamA
copy the older `%APPDATA%\ClipDeck` settings and database, without deleting the old files.

- Clipboard bodies, previews, HTML, RTF, images, physical/virtual file lists, quick-text bodies, OCR,
  tag and board names, and thumbnails in active and deleted records are protected with Windows DPAPI
  in the current-user scope and are normally decryptable only in that Windows-user context.
- Selected data must be decrypted in process memory for search, preview, paste, and backup export.
  Owned buffers are overwritten where reasonably possible after use.
- Deduplication values use HMAC-SHA-256 with a per-installation secret protected by DPAPI in
  `dedup-key.bin`. HMAC is not a substitute for content encryption.
- Full-text-search candidate filters use a separate per-installation DPAPI-protected HMAC key. They do
  not store plaintext words or bodies, but this is not fully encrypted search that hides every length
  or access pattern. Actual matches are checked by individually decrypting candidates in memory.
- Some operational metadata may remain plaintext: the current item's source app, settings and database
  structure, quick-text name, identifiers, types, times, results, counts, provenance, paste method,
  retention time, size, pin state, and organization relationships. Source or opt-in target executable
  names inside events are DPAPI-protected.
- DPAPI does not defend against malware already running as the same unlocked Windows user, screen or
  keyboard capture, memory attacks, user-authorized remote control, or physical access to an unlocked PC.

Before migration, SQLite integrity controls check the existing database. A required schema or HMAC
transition creates a consistent recovery snapshot linked by a random in-database marker and snapshot
SHA-256. An interrupted transition resumes on the next launch. A linked snapshot is deleted only after
the current database, schema, required tables and columns, key marker, and WAL state pass verification;
unlinked or unproven snapshots are not automatically removed. This is crash recovery, not an external
backup service. Do not manually move or delete either data folder before final testing with real user
data and failure/recovery scenarios.

Schema v5 had no per-event history. Migration to v6 creates only a summary at the then-last copy time
and, if an automatic-paste aggregate exists, one summary at its then-last paste time; it does not infer
past individual times, targets, methods, or results. Schema v8 links RTF, registered images, virtual files,
the source `CanUploadToCloudClipboard` state, search filters, OCR, tags, boards, and paste queues to the
same `memory_id` lifecycle.

OCR runs locally with installed Windows OCR language packs and does not upload images. Results may be
inaccurate, can be deleted by the user, and are not an official transcription.

A portable backup decrypts logical records from a consistent SQLite snapshot in the current Windows-user
context and immediately re-encrypts them with the user-entered password using Argon2id and
XChaCha20-Poly1305. The password and derived key are neither stored nor sent to a server, and memory is
overwritten where reasonably possible after the operation. PCSSAK cannot recover a forgotten password or
missing file. A backup may contain active and deleted records, quick text, events, OCR, and organization
data as of export; the user controls the security and retention of its folder, external device, or sync
service. Import validates an isolated candidate and replaces rather than merges the current database.
Restoring an older backup can reintroduce data already deleted from the current app.

## 4. Retention, deletion, and restore periods

The user-defined item-count limit applies to unorganized ordinary records. Pinned records and records
linked to OCR, tags, boards, or a paste queue are protected from count-based pruning, so the actual count
may be higher. Protected and unprotected data are all subject to a separate 512 MB logical-storage cap.
Automatic count pruning bypasses the manual deleted-record store and removes linked events.

Individual deletion or Clear history moves the record and its linked events into AroDamA's local
deleted-record lifecycle, not the Windows Recycle Bin. Date-range deletion includes both endpoints based
on the record's local copy date and protects pinned records. A future date does not schedule deletion.

- Free restore is available until exactly 24 hours after deletion.
- After 24 hours, the current Free Early Access cannot restore the record, although its encrypted content
  and events may remain under the same Windows user on the same PC for up to 30 days from deletion. The
  current product has no Pro, payment, sale, remote-license activation, or UI that unlocks this data.
- Deleted records and events count toward the same 512 MB logical cap as records, pins, and quick text.
- The user may permanently erase deleted data earlier. Data reaching exactly 30 days is removed from the
  app database at the next deleted-store cleanup and cannot be restored by the app.

Expiry or permanent deletion removes content and linked events from the current database at application
level; it is not secure physical-media erasure. Traces may remain in SQLite free pages or WAL, retained
migration-recovery files, Windows or organization backups, disk-recovery areas, or third-party synchronized
copies. Deleting a stored target-app name likewise removes the ciphertext only from the current database
and does not overwrite separate copies.

The 24-hour restore boundary, 30-day expiry, and event times use local Windows system time. Large clock
changes may affect display, restore, and expiry decisions. The timeline is not signed by a trusted time
source and is not a tamper-proof audit log or legal evidence. The deleted-record store and portable backups
are separate; AroDamA cannot recover a lost database, backup file, or password.

A normal uninstall preserves the history and settings in `%LOCALAPPDATA%\PCssak\AroDamA`. Only if the
user explicitly selects `Delete app data` in the uninstaller does it delete AroDamA-managed settings, the
database, protection keys, migration-recovery snapshots, and verified restore candidates according to an
exact allowlist. Even then, it does not recursively delete the shared `PCssak\AroDamA` root or delete
user-exported `.arodama-backup` files, backups or rollback copies in another location, synchronized copies,
or organization-retention copies. Review and remove those copies separately if desired.

## 5. Sensitive-data minimization and user controls

AroDamA honors recognized Windows clipboard exclusions including `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing`, and `CanIncludeInClipboardHistory=0`. Not every password
manager or business app publishes these markers, so non-collection of sensitive data cannot be guaranteed.

The app preserves all three states of the Windows registered format `CanUploadToCloudClipboard`: absent,
DWORD 1 (allowed), and DWORD 0 (blocked). When republishing a stored item, AroDamA first republishes the
original state so it does not erase the source app's no-cloud-upload intent. AroDamA itself does not upload
the content and does not change synchronization settings for Windows or other apps. An abnormal length or
a value other than 0 or 1 is not assumed allowed; the capture is rejected.

Default password-manager protection is only a convenience filter that skips a new payload before reading
it when the Windows executable base name exactly matches `1password.exe`, `bitwarden.exe`, `keepass.exe`,
or `keepassxc.exe`. It is not a complete security boundary for every version, extension, broker process,
or elevated app. The sensitive-text blocker also uses narrow local rules and sends neither source text nor
blocked hashes to logs, the database, or the network. Neither control deletes prior records.

Users can pause capture, exclude apps, disable image/file capture, leave target-app memory off, delete
stored target names and records, empty the deleted-record store, lower limits, and remove local data.
When handling passwords, one-time codes, or personal data, pause capture; exclude security apps not in the
default list; use a separate Windows account and lock the screen on shared PCs; and review and delete
history regularly.

## 6. Network access and third-party processing

AroDamA does not upload clipboard content, local file names or paths, quick text, OCR images or results,
memory timelines, or portable backups to PCSSAK or the update server. After first-run consent, it may use
HTTPS to check the following official GitHub Release metadata address:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

The app compares its current version with the response's version, release notes, download URL, and integrity
signature. It downloads an installer only after the user explicitly chooses to install an offered update.
GitHub may process standard request data such as IP address, access time, and user agent under GitHub's
privacy terms. AroDamA adds no clipboard content or usage history to the request; GitHub's policy governs
its processing location and retention.

If Microsoft Edge WebView2 Runtime is missing, the Tauri NSIS installation may download Microsoft's
WebView2 bootstrapper. This is not an AroDamA clipboard-data transfer, and Microsoft's policy applies.
If the user stores an encrypted backup in a folder managed by OneDrive or another third-party synchronization
app, that app may upload the file under its own settings and privacy policy.

Before any future account, payment, remote support, analytics, or crash-reporting feature is activated,
this notice will be updated with the actual transmitted data, purpose, retention, providers, and possible
international transfer, and consent required by applicable law will be obtained.

## 7. User rights, contact, and notice changes

Because there is no PCSSAK account or central clipboard database, PCSSAK cannot remotely retrieve, export,
correct, or delete local clipboard content for the user. Users control local data through the features in
Section 5 and the official deletion guidance.

Privacy questions: `privacy@pcssak.com`

General support: `support@pcssak.com`

Do not post vulnerability details, clipboard content, databases, credentials, or identifying logs in a
public issue. Use GitHub Private vulnerability reporting in the official public release repository.

PCSSAK is the current product and website operator display name; that label alone does not claim an
incorporated or registered business in any country. Paid sales requiring registered-seller disclosures or
separate sales terms will begin only after those details and terms are finalized and published.

When this notice changes, its date and version will change. Users will be notified before a material
expansion of data processing takes effect and will be asked for renewed consent where required.

---

# PCSSAK AroDamA Free Early Access プライバシー通知

- 文書バージョン: 1.0
- 最終更新日: 2026-09-01
- 対象: PCSSAK AroDamA Free Early Access for Windows
- 運営者表示名: PCSSAK
- プライバシーに関するお問い合わせ: `privacy@pcssak.com`
- 一般サポート: `support@pcssak.com`

> 本書は、韓国語の正文を理解するための日本語参考訳です。各言語版の解釈が異なる場合、
> 適用法令で認められる範囲に限り韓国語版を優先します。利用者の居住地で強行的に適用される
> 個人情報保護法、消費者保護法その他放棄できない権利が本書に優先します。本書は各法域の
> 法律専門家による最終審査前の保守的な運用案であり、法律上の助言ではありません。

## 1. 処理方針と初回起動時の同意

PCSSAK AroDamAは、ローカル処理を基本とするWindowsアプリです。現在のFree Early Accessには、
アカウント、広告、利用状況分析、クラウド同期、リモートでのクラッシュ報告、決済、リモートでの
ライセンス検証はありません。クリップボード履歴と設定は利用者のPC内で管理されます。ただし、
更新の確認、利用者が承認したダウンロード、WebView2の準備には、第6項の限定的な通信があります。

初回起動時は、利用者がアプリ内でEULAと本通知を開いて確認し、文書確認チェックボックスと開始
ボタンを明示的に選ぶまで、クリップボードの取得と自動更新確認を一時停止します。完了状態と取得
再開は一緒に保存されます。ローカル設定には、同意したEULA・本通知の版、文書一式のフィンガー
プリント、端末の確認時刻を保存しますが、同意記録をアカウントやサーバーへ送信しません。使用許諾
またはデータ処理に重要な変更がある場合は文書の版を更新し、再確認まで取得を停止します。
インストーラーにも同じEULAを表示します。

## 2. 機能利用時に処理するデータ

| 分類 | 例 | 目的 |
|---|---|---|
| クリップボード内容 | テキスト、HTML・RTF、画像、実ファイルのパス一覧、メモリ上で提供された仮想ファイルの名前と内容 | 履歴、検索、プレビュー、再利用 |
| コピー元・貼り付け先 | クリップボード所有プロセス名、利用者が許可した場合の自動貼り付け先実行ファイル名 | 検索、コピー元表示、除外、日付別の記憶タイムライン |
| 定型文 | 利用者が作成した名前と本文 | 繰り返し使う文章の再利用 |
| 記憶の整理 | 利用者が抽出・保存したOCR文字、タグ、ボード名と所属、画像サムネイル、連続貼り付け順 | 画像内文字検索、分類、順次再利用 |
| ポータブルバックアップ | 出力時点の有効・削除済み履歴、定型文、イベント、OCR、整理データを含む場合がある暗号化ファイル | 復旧または別PCへの移行 |
| 設定 | ショートカット、テーマ、言語、保存上限、除外アプリ、一時停止、画像・ファイル取得、初回案内完了 | 利用環境の保持 |
| 運用メタデータ | 項目・イベントID、種類、開始・完了時刻、結果、回数、出所区分、貼り付け方法、容量、ピン、重複判定値 | 並べ替え、タイムライン、整合性、保存上限、重複防止 |

定型文の`{clipboard}`変数は、プレビューまたは使用時に現在のWindowsテキストだけを読みます。
この明示的な読み取り自体は履歴を追加せず、設定された文字数上限を超えると処理を拒否します。

自動貼り付け先アプリの記憶は初期状態でオフです。有効にすると、実行ファイルのベース名
（例: `notepad.exe`）だけを保存し、文書・ウィンドウのタイトル、フルパス、PID、HWNDは保存しません。
オフにしても過去の名前は自動削除されません。二段階確認により、現在のDBから過去の貼り付け先名
だけを完全に削除できますが、日付・種類・結果・回数などのイベントは残り、削除した名前をアプリで
復元できません。コピー元アプリ名はこの操作では削除されません。コピー元を保存したくない場合は
除外アプリに追加するか取得を一時停止してください。除外設定と有効な既定のパスワードマネージャー
保護は将来の貼り付け先名にも適用されますが、設定変更は保存済みデータを遡って検査・削除しません。

「機密性の可能性があるテキストをブロック」は初期状態でオフです。有効にすると、秘密鍵ブロック、
識別可能なアクセストークン形式、Luhn検査に合格した一般的な決済カード番号形式を端末内の限定的な
規則で判定し、保存前に除外します。誤検知・見逃しがあり、既存履歴は検査・削除しません。そのため、
パスワード、ワンタイムコード、本人確認・金融・医療情報、業務機密が取得される可能性は残ります。

## 3. 保存、暗号化、復旧保護

新しいデータは`%LOCALAPPDATA%\PCssak\AroDamA`に保存します。この場所が空の場合に限り、従来の
`%APPDATA%\ClipDeck`の設定とDBをコピーすることがあり、元のファイルは削除しません。

- 有効・削除済み履歴の本文、プレビュー、HTML、RTF、画像、実/仮想ファイル一覧、定型文本文、OCR、
  タグ・ボード名、サムネイルは、Windows DPAPIの現在の利用者スコープで保護され、原則として同じ
  Windows利用者のコンテキストでのみ復号できます。
- 検索、プレビュー、貼り付け、バックアップ出力中は選択したデータがプロセスメモリ内で復号されます。
  所有するバッファは、利用後に可能な範囲で上書きします。
- 重複判定はインストールごとの秘密鍵でHMAC-SHA-256を計算します。鍵は`dedup-key.bin`にDPAPIで
  保護して保存しますが、HMACは内容の暗号化を代替しません。
- 全文検索の候補フィルターは別のインストール別DPAPI保護HMAC鍵を使います。平文の単語や本文は
  保存しませんが、長さやアクセスパターンなど全ての付随情報を隠す完全暗号化検索ではありません。
  実際の一致は候補をメモリ内で個別に復号して確認します。
- 現在項目のコピー元アプリ、設定とDB構造、定型文名、ID、種類、時刻、結果、回数、出所区分、
  貼り付け方法、保存時刻、容量、ピン、整理関係などの運用メタデータは平文の場合があります。
  イベント内のコピー元または任意保存した貼り付け先実行ファイル名はDPAPIで保護します。
- DPAPIは、ロック解除中に同じ利用者権限で動作するマルウェア、画面・キー入力の取得、メモリ攻撃、
  利用者が許可した遠隔操作、ロック解除済みPCへの物理アクセスを防ぐものではありません。

移行前にSQLiteの整合性を確認します。スキーマまたはHMACの移行時は、DB内のランダムな移行印と
スナップショットのSHA-256で正確に結び付けた一貫性のある復旧コピーを作ります。中断時は次回起動で
再開し、現在のDB、スキーマ、必須テーブル・列、鍵の印、WAL状態が全て検証された場合のみ関連コピーを
削除します。関連付けや出所を証明できないコピーは自動削除しません。これはクラッシュ復旧であり外部
バックアップサービスではありません。実データと失敗・復旧シナリオの最終試験前にデータフォルダーを
手動で移動・削除しないでください。

スキーマv5にはイベントごとの過去履歴がありません。v6移行では当時の最終コピー時刻の要約と、
自動貼り付け累計があれば当時の最終貼り付け時刻の要約だけを作り、過去の個別時刻、対象、方法、結果を
推定しません。v8ではRTF、登録画像、仮想ファイル、元の`CanUploadToCloudClipboard`状態、検索候補、
OCR、タグ、ボード、連続貼り付けを同じ`memory_id`のライフサイクルに結び付けます。

OCRはインストール済みのWindows OCR言語パックを使いPC内でのみ動作し、画像を送信しません。結果は
不正確な場合があり、利用者が削除でき、原本の公式な文字起こしではありません。

ポータブルバックアップは一貫したSQLiteスナップショットの論理レコードを現在のWindows利用者
コンテキストで復号し、利用者のパスワードを用いてArgon2idとXChaCha20-Poly1305で直ちに再暗号化します。
パスワードと派生鍵は保存・送信せず、処理後は可能な範囲でメモリを上書きします。忘れたパスワードや
失ったファイルをPCSSAKは復旧できません。バックアップには出力時点の有効・削除済み履歴、定型文、
イベント、OCR、整理データが含まれる場合があり、保存先、外部媒体、同期サービスの安全性と保存期間は
利用者が管理します。インポートは隔離した候補を検証し、現DBへ結合せず置換します。古いバックアップを
復元すると、現在のアプリで既に削除したデータが再び現れることがあります。

## 4. 保存、削除、復元期間

設定した件数上限は整理されていない通常履歴に適用します。ピン、OCR、タグ、ボード、連続貼り付けに
関連付けた履歴は件数による自動整理から保護され、実際の件数が上限を超える場合があります。全データは
保護の有無にかかわらず、別途512 MBの論理保存容量上限に含まれます。件数による自動整理は手動削除用の
保管庫を経由せず、関連イベントも削除します。

個別削除または履歴消去を実行すると、履歴と関連イベントはWindowsのごみ箱ではなく、AroDamAのローカル
削除履歴ライフサイクルへ移ります。期間指定削除は現地のコピー日付について開始日・終了日の両方を含み、
ピン留めを保護します。未来の日付を指定しても予約削除にはなりません。

- 削除から正確に24時間までは無料で復元できます。
- 24時間後は現在のFree Early Accessで復元できませんが、暗号化された内容とイベントが、同じPCの
  同じWindows利用者の下で削除時から最大30日間残る場合があります。現在はこれを解除するPro、決済、
  販売、リモートライセンス有効化の機能またはUIはありません。
- 削除済み履歴とイベントも履歴、ピン、定型文と同じ512 MB論理上限に含まれます。
- 利用者は早期に完全削除できます。正確に30日となったデータは次回の保管庫整理でアプリDBから削除され、
  アプリでは復元できません。

期限切れ・完全削除は現在のDBから内容と関連イベントをアプリレベルで除くもので、物理媒体の安全な消去
ではありません。SQLiteの未使用ページやWAL、保存された移行復旧ファイル、Windows・組織のバックアップ、
ディスク復旧領域、第三者同期コピーに痕跡が残る場合があります。保存した貼り付け先名の削除も現在DB内の
暗号文だけを除き、別のコピーを上書きしません。

24時間の復元、30日の期限、イベント時刻はローカルのWindowsシステム時刻を使用します。時刻の大幅な
変更は表示・復元・期限判定に影響します。タイムラインは信頼できる時刻源で署名された改ざん防止監査ログ
または法的証拠ではありません。削除履歴保管庫とポータブルバックアップは別であり、失ったDB、バックアップ、
パスワードをAroDamAは復旧できません。

通常のアンインストールでは、`%LOCALAPPDATA%\PCssak\AroDamA` 内の履歴と設定は保持されます。
アンインストーラーでユーザーが `アプリデータを削除` を明示的に選択した場合に限り、AroDamA が管理する
設定、データベース、保護キー、移行用復旧スナップショットおよび検証済みの復元候補を、厳密な許可リストに
従って削除します。その場合でも、共有の `PCssak\AroDamA` ルートを再帰的に削除することはなく、ユーザーが
書き出した `.arodama-backup` ファイル、別の場所にあるバックアップやロールバック用コピー、同期コピー、
または組織が保管するコピーは削除しません。必要に応じて、それらのコピーを別途確認して削除してください。

## 5. 機密データの最小化と利用者による管理

AroDamAは`Clipboard Viewer Ignore`、`ExcludeClipboardContentFromMonitorProcessing`、
`CanIncludeInClipboardHistory=0`など、認識可能なWindowsクリップボード除外指定を尊重します。ただし、
全てのパスワードマネージャーや業務アプリがこれらを公開するわけではなく、機密データを取得しないことを
絶対には保証できません。

Windows登録形式`CanUploadToCloudClipboard`の「なし」、DWORD 1（許可）、DWORD 0（禁止）の三状態を
保存します。保存項目を再公開するときは元の状態を先に公開し、元アプリのクラウドアップロード禁止の意思を
消しません。AroDamA自身は内容をアップロードせず、Windows全体や他アプリの同期設定も変更しません。
異常な長さまたは0・1以外の値を許可と推定せず、その取得を拒否します。

既定のパスワードマネージャー保護は、Windows実行ファイルのベース名が`1password.exe`、
`bitwarden.exe`、`keepass.exe`、`keepassxc.exe`のいずれかと完全一致した場合に、新しい内容を読む前に
除外する便宜的なフィルターにすぎません。全バージョン、拡張機能、中継プロセス、管理者権限アプリを扱う
完全なセキュリティ境界ではありません。機密テキストブロックも限定的なローカル規則だけを使い、原文や
ブロックしたハッシュをログ、DB、ネットワークへ送りません。どちらも過去の履歴を削除しません。

利用者は取得の一時停止、アプリ除外、画像・ファイル取得の無効化、貼り付け先記憶のオフ、保存した対象名と
履歴の削除、削除保管庫の消去、上限の縮小、ローカルデータの削除ができます。パスワード、認証コード、
個人情報を扱うときは取得を止め、既定リスト外のセキュリティアプリを除外し、共有PCでは別のWindows
アカウントを使って画面をロックし、履歴を定期的に確認・削除してください。

## 6. ネットワーク接続と第三者による処理

AroDamAは、クリップボード内容、ローカルのファイル名・パス、定型文、OCR画像・結果、記憶タイムライン、
ポータブルバックアップをPCSSAKまたは更新サーバーへアップロードしません。初回案内への同意後、次の公式
GitHub ReleaseメタデータへHTTPSで接続して更新を確認する場合があります。

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

現在のアプリ版と、応答内の版、リリースノート、ダウンロードURL、整合性署名を比較します。インストーラーは
利用者が更新の導入を明示的に選んだ場合のみダウンロードします。GitHubはIPアドレス、接続時刻、ユーザー
エージェントなどの標準リクエスト情報を同社のプライバシー条件に従って処理する場合があります。AroDamAは
クリップボード内容や利用履歴をリクエストに加えず、GitHubの処理地域と保存期間には同社の方針が適用されます。

Microsoft Edge WebView2 Runtimeがない場合、Tauri NSISインストール時にMicrosoftからWebView2
ブートストラッパーをダウンロードする場合があります。これはAroDamAのクリップボードデータ送信ではなく、
Microsoftの方針が適用されます。暗号化バックアップをOneDriveなど第三者の同期アプリが管理するフォルダーに
保存した場合、そのアプリが自身の設定・プライバシー方針に従ってファイルをアップロードすることがあります。

将来、アカウント、決済、リモートサポート、分析、クラッシュ報告を有効にする場合は、実際の送信データ、目的、
保存期間、提供事業者、国際移転の可能性を先に本通知へ反映し、適用法令上必要な同意を得ます。

## 7. 利用者の権利、お問い合わせ、通知の変更

PCSSAKアカウントや中央クリップボードDBがないため、PCSSAKは利用者に代わってローカル内容を遠隔で取得、
出力、訂正、削除できません。利用者は第5項の機能と公式削除案内でローカルデータを管理します。

プライバシーに関するお問い合わせ: `privacy@pcssak.com`

一般サポート: `support@pcssak.com`

脆弱性の詳細、クリップボード内容、DB、認証情報、個人を識別できるログを公開Issueへ投稿しないでください。
公式公開リリースリポジトリのGitHub非公開脆弱性報告機能を利用してください。

PCSSAKは現在の製品・ウェブサイト上の運営者表示名であり、それだけで特定国の法人または登録商号があることを
示しません。登録販売者情報または別の販売条件が必要な有料販売は、それらを確定・公開した後にのみ開始します。

本通知を変更するときは日付と版を更新します。データ処理範囲を実質的に拡大する場合は適用前に案内し、必要に
応じて改めて同意を得ます。

---

# PCSSAK AroDamA Free Early Access – Datenschutzhinweis

- Dokumentversion: 1.0
- Letzte Aktualisierung: 2026-09-01
- Gilt für: PCSSAK AroDamA Free Early Access for Windows
- Angezeigter Betreibername: PCSSAK
- Datenschutzanfragen: `privacy@pcssak.com`
- Allgemeiner Support: `support@pcssak.com`

> Diese deutsche Fassung ist eine unverbindliche Übersetzung des maßgeblichen koreanischen Textes.
> Bei Abweichungen ist der koreanische Text nur insoweit maßgeblich, wie das anwendbare Recht dies zulässt.
> Zwingende Datenschutz- und Verbraucherschutzvorschriften sowie sonstige nicht abdingbare Rechte am Wohnort
> des Nutzers gehen vor. Der Text ist ein vorsichtiger Betriebsentwurf vor einer fachanwaltlichen Prüfung
> in allen Rechtsordnungen und stellt keine Rechtsberatung dar.

## 1. Verarbeitungsgrundsätze und Einwilligung beim ersten Start

PCSSAK AroDamA ist eine lokal arbeitende Windows-Anwendung. Die derzeitige Free-Early-Access-Version
enthält kein Konto, keine Werbung, Nutzungsanalyse, Cloud-Synchronisierung, entfernte Absturzübermittlung,
Zahlung oder entfernte Lizenzprüfung. Zwischenablageverlauf und Einstellungen werden auf dem PC des Nutzers
verwaltet. Begrenzte Netzwerkzugriffe für Update-Prüfungen, vom Nutzer bestätigte Downloads und die
WebView2-Bereitstellung werden in Abschnitt 6 beschrieben.

Beim ersten Start bleiben Zwischenablageerfassung und automatische Update-Prüfung angehalten, bis der Nutzer
EULA und diesen Hinweis in der App öffnen und prüfen, das Bestätigungsfeld markieren und ausdrücklich die
Startschaltfläche betätigen kann. Abschluss und Wiederaufnahme der Erfassung werden gemeinsam gespeichert.
Lokal gespeichert werden die akzeptierten Fassungen von EULA und Datenschutzhinweis, ein Fingerabdruck des
Dokumentsatzes und der lokale Bestätigungszeitpunkt; ein Einwilligungsnachweis wird nicht an ein Konto oder
einen Server gesendet. Wesentliche Änderungen der Lizenz oder Verarbeitung erhöhen die Dokumentversion und
halten die Erfassung bis zur erneuten Prüfung an. Das Installationsprogramm zeigt dieselbe EULA an.

## 2. Bei Nutzung der Funktionen verarbeitete Daten

| Kategorie | Beispiele | Zweck |
|---|---|---|
| Zwischenablageinhalt | Text, HTML-/RTF-Formatierung, Bilder, Pfadlisten realer Dateien sowie Namen und Bytes virtueller Dateien | Verlauf, Suche, Vorschau und Wiederverwendung |
| Quelle und Ziel | Prozessname des Zwischenablageeigentümers und nur nach Aktivierung der Name der Zielprogrammdatei beim automatischen Einfügen | Suche, Quellenanzeige, Ausschlüsse und datierte Gedächtniszeitleiste |
| Textbausteine | Vom Nutzer erstellter Name und Inhalt | Wiederverwendung häufig benötigter Texte |
| Gedächtnisorganisation | Angeforderter OCR-Text, Tags, Namen und Zuordnungen von Boards, Bildminiaturen und Reihenfolge der Einfügewarteschlange | Bildtextsuche, Einordnung und geordnete Wiederverwendung |
| Portables Backup | Verschlüsselte Datei, die aktive und gelöschte Datensätze, Textbausteine, Ereignisse, OCR- und Ordnungsdaten enthalten kann | Wiederherstellung oder Übertragung auf einen anderen PC |
| Einstellungen | Tastenkürzel, Design, Sprache, Aufbewahrungsgrenzen, ausgeschlossene Apps, Pausenstatus, Bild-/Dateierfassung und Abschluss des Ersthinweises | Nutzerumgebung erhalten |
| Betriebsmetadaten | Element-/Ereignis-ID, Typ, Start-/Endzeit, Ergebnis, Anzahl, Herkunft, Einfügemethode, Größe, Fixierung und Duplikatwert | Sortierung, Zeitleiste, Integrität, Aufbewahrung und Duplikatvermeidung |

Die Textbausteinvariable `{clipboard}` liest den aktuellen Windows-Text nur bei Vorschau oder Verwendung.
Dieser ausdrückliche Lesevorgang erzeugt für sich keinen neuen Verlaufseintrag und wird oberhalb der
eingestellten Textgrenze abgelehnt.

Das Merken der Ziel-App für automatisches Einfügen ist standardmäßig aus. Nach Aktivierung wird nur der
Basisname der ausführbaren Datei (z. B. `notepad.exe`) gespeichert, nicht Dokument- oder Fenstertitel,
vollständiger Pfad, PID oder HWND. Das Abschalten wirkt nur für künftige Ereignisse. Ein gesonderter Befehl
mit zweistufiger Bestätigung löscht frühere Zielnamen dauerhaft aus der aktuellen Datenbank, während Datum,
Typ, Ergebnis und Anzahl des Ereignisses erhalten bleiben; der Name kann in der App nicht wiederhergestellt
werden. Quell-App-Namen werden dabei nicht gelöscht. Um eine Quelle nicht zu speichern, ist die App
auszuschließen oder die Erfassung anzuhalten. Ausschlüsse und aktivierter Standardschutz für Passwortmanager
gelten auch für künftige Zielnamen; Einstellungsänderungen prüfen oder löschen bestehende Daten nicht rückwirkend.

Der optionale Filter für möglicherweise sensible Texte ist standardmäßig aus. Aktiviert überspringen enge
lokale Regeln erkannte private Schlüsselblöcke, erkennbare Zugriffstokenformate und übliche Kartennummernformate,
die die Luhn-Prüfung bestehen, bevor sie gespeichert werden. Fehlalarme und übersehene Inhalte sind möglich;
bestehende Einträge werden weder geprüft noch gelöscht. Passwörter, Einmalcodes, Identitäts-, Finanz-, Gesundheits-
oder vertrauliche Unternehmensdaten können daher weiterhin erfasst werden.

## 3. Speicherung, Verschlüsselung und Wiederherstellungsschutz

Neue Daten werden unter `%LOCALAPPDATA%\PCssak\AroDamA` gespeichert. Nur wenn dieser Ort leer ist, können
ältere Einstellungen und die Datenbank aus `%APPDATA%\ClipDeck` kopiert werden; die alten Dateien bleiben erhalten.

- Inhalte, Vorschauen, HTML, RTF, Bilder, reale/virtuelle Dateilisten, Textbausteininhalte, OCR, Tag-/Boardnamen
  und Miniaturen aktiver und gelöschter Datensätze werden mit Windows DPAPI im Bereich des aktuellen Nutzers
  geschützt und grundsätzlich nur in demselben Windows-Nutzerkontext entschlüsselt.
- Für Suche, Vorschau, Einfügen und Backup-Export müssen ausgewählte Daten im Prozessspeicher entschlüsselt
  vorliegen. Eigene Puffer werden nach Gebrauch soweit vernünftig möglich überschrieben.
- Duplikatwerte werden per HMAC-SHA-256 mit einem installationsbezogenen Geheimnis gebildet. Der Schlüssel
  liegt DPAPI-geschützt in `dedup-key.bin`; HMAC ersetzt keine Inhaltsverschlüsselung.
- Kandidatenfilter der Volltextsuche verwenden einen separaten installationsbezogenen DPAPI-geschützten
  HMAC-Schlüssel. Sie speichern keine Klartextwörter oder -inhalte, sind aber keine vollständig verschlüsselte
  Suche, die sämtliche Längen- oder Zugriffsmuster verbirgt. Treffer werden durch einzelne Entschlüsselung
  der Kandidaten im Speicher bestätigt.
- Einige Betriebsmetadaten können Klartext sein: Quell-App des aktuellen Elements, Einstellungen und
  Datenbankstruktur, Textbausteinname, IDs, Typen, Zeiten, Ergebnisse, Anzahlen, Herkunft, Einfügemethode,
  Aufbewahrungszeit, Größe, Fixierung und Ordnungsbeziehungen. Quell- oder freiwillig gespeicherte
  Zielprogrammnamen in Ereignissen sind DPAPI-geschützt.
- DPAPI schützt nicht vor Schadsoftware mit Rechten desselben entsperrten Windows-Nutzers, Bildschirm-
  oder Tastaturaufzeichnung, Speicherangriffen, vom Nutzer erlaubter Fernsteuerung oder physischem Zugriff
  auf einen entsperrten PC.

Vor einer Migration wird die SQLite-Integrität geprüft. Ein erforderlicher Schema- oder HMAC-Wechsel erstellt
eine konsistente Wiederherstellungskopie, die durch eine zufällige Datenbankmarke und den SHA-256-Wert des
Snapshots eindeutig verbunden ist. Unterbrochene Wechsel werden beim nächsten Start fortgesetzt. Eine
verbundene Kopie wird erst gelöscht, wenn aktuelle Datenbank, Schema, erforderliche Tabellen und Spalten,
Schlüsselmarke und WAL-Zustand geprüft wurden; unverbundene oder nicht belegbare Kopien werden nicht automatisch
gelöscht. Dies ist Absturzwiederherstellung, kein externer Backupdienst. Vor abschließenden Tests mit echten
Nutzerdaten und Fehler-/Wiederherstellungsfällen sollen die Datenordner nicht manuell verschoben oder gelöscht werden.

Schema v5 enthielt keinen ereignisweisen Altverlauf. Die Migration auf v6 erzeugt nur eine Zusammenfassung zum
damals letzten Kopierzeitpunkt und, falls eine Summe automatischer Einfügungen existiert, eine Zusammenfassung
zum damals letzten Einfügezeitpunkt; einzelne frühere Zeiten, Ziele, Methoden oder Ergebnisse werden nicht
geschätzt. Schema v8 verbindet RTF, registrierte Bilder, virtuelle Dateien, den ursprünglichen Zustand von
`CanUploadToCloudClipboard`, Suchfilter, OCR, Tags, Boards und Einfügewarteschlangen mit demselben
`memory_id`-Lebenszyklus.

OCR läuft lokal mit installierten Windows-OCR-Sprachpaketen und lädt Bilder nicht hoch. Ergebnisse können
ungenau sein, sind löschbar und keine amtliche Transkription des Originals.

Ein portables Backup entschlüsselt logische Datensätze eines konsistenten SQLite-Snapshots im aktuellen
Windows-Nutzerkontext und verschlüsselt sie sofort mit dem eingegebenen Kennwort mittels Argon2id und
XChaCha20-Poly1305 neu. Kennwort und abgeleiteter Schlüssel werden weder gespeichert noch übertragen;
Speicher wird danach soweit vernünftig möglich überschrieben. PCSSAK kann ein vergessenes Kennwort oder eine
verlorene Datei nicht wiederherstellen. Das Backup kann aktive und gelöschte Datensätze, Textbausteine,
Ereignisse, OCR- und Ordnungsdaten zum Exportzeitpunkt enthalten. Der Nutzer verwaltet Sicherheit und
Aufbewahrung am Speicherort, auf externen Medien oder in Synchronisierungsdiensten. Der Import prüft einen
isolierten Kandidaten und ersetzt die aktuelle Datenbank, statt sie zusammenzuführen. Ein altes Backup kann
bereits in der aktuellen App gelöschte Daten wieder erscheinen lassen.

## 4. Aufbewahrungs-, Lösch- und Wiederherstellungsfristen

Die eingestellte Anzahlgrenze gilt für nicht organisierte normale Datensätze. Fixierte oder mit OCR, Tags,
Boards oder einer Einfügewarteschlange verknüpfte Datensätze sind vor anzahlbasierter Bereinigung geschützt,
sodass die tatsächliche Anzahl höher sein kann. Alle Daten unterliegen unabhängig davon einer separaten
logischen Speichergrenze von 512 MB. Automatische Anzahlbereinigung umgeht den manuellen Löschspeicher und
entfernt verknüpfte Ereignisse.

Einzellöschung oder „Verlauf leeren“ verschiebt Datensatz und Ereignisse in AroDamAs lokalen Lebenszyklus für
gelöschte Datensätze, nicht in den Windows-Papierkorb. Eine Datumsbereichslöschung umfasst anhand des lokalen
Kopierdatums beide Grenzen und schützt fixierte Datensätze. Ein zukünftiges Datum plant keine spätere Löschung.

- Bis genau 24 Stunden nach der Löschung ist eine kostenlose Wiederherstellung möglich.
- Danach kann die aktuelle Free-Early-Access-Version nicht wiederherstellen; verschlüsselte Inhalte und
  Ereignisse können jedoch ab Löschung bis zu 30 Tage unter demselben Windows-Nutzer auf demselben PC verbleiben.
  Es gibt derzeit keine Pro-, Zahlungs-, Verkaufs-, entfernte Lizenzaktivierungsfunktion oder UI zum Entsperren.
- Gelöschte Datensätze und Ereignisse zählen zusammen mit Verlauf, Fixierungen und Textbausteinen zur selben
  logischen Grenze von 512 MB.
- Der Nutzer kann früher dauerhaft löschen. Genau 30 Tage alte Daten werden bei der nächsten Bereinigung aus
  der App-Datenbank entfernt und können durch die App nicht wiederhergestellt werden.

Ablauf oder dauerhaftes Löschen entfernt Inhalt und verknüpfte Ereignisse auf Anwendungsebene aus der aktuellen
Datenbank; es ist keine sichere physische Datenträgerlöschung. Spuren können in freien SQLite-Seiten oder WAL,
aufbewahrten Migrationskopien, Windows-/Unternehmensbackups, Wiederherstellungsbereichen oder synchronisierten
Drittkopien bleiben. Auch das Löschen gespeicherter Ziel-App-Namen entfernt nur den Chiffretext aus der aktuellen
Datenbank und überschreibt keine getrennten Kopien.

24-Stunden-Wiederherstellung, 30-Tage-Ablauf und Ereigniszeiten beruhen auf der lokalen Windows-Systemzeit.
Große Zeitänderungen können Anzeige, Wiederherstellung und Ablauf beeinflussen. Die Zeitleiste ist nicht durch
eine vertrauenswürdige Zeitquelle signiert und weder manipulationssicheres Auditprotokoll noch Rechtsbeweis.
Löschspeicher und portables Backup sind getrennt; AroDamA kann verlorene Datenbanken, Backups oder Kennwörter
nicht wiederherstellen.

Bei einer normalen Deinstallation bleiben Verlauf und Einstellungen unter
`%LOCALAPPDATA%\PCssak\AroDamA` erhalten. Nur wenn der Nutzer im Deinstallationsprogramm ausdrücklich
`App-Daten löschen` auswählt, werden die von AroDamA verwalteten Einstellungen, die Datenbank,
Schutzschlüssel, Wiederherstellungsabbilder für Migrationen und geprüften Wiederherstellungskandidaten nach
einer genau festgelegten Positivliste gelöscht. Auch dann wird das gemeinsam genutzte Stammverzeichnis
`PCssak\AroDamA` nicht rekursiv gelöscht. Vom Nutzer exportierte `.arodama-backup`-Dateien, Sicherungen oder
Rollback-Kopien an einem anderen Ort, synchronisierte Kopien und Aufbewahrungskopien einer Organisation
werden nicht gelöscht. Solche Kopien sind bei Bedarf separat zu prüfen und zu entfernen.

## 5. Minimierung sensibler Daten und Nutzerkontrollen

AroDamA beachtet erkennbare Windows-Zwischenablageausschlüsse wie `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing` und `CanIncludeInClipboardHistory=0`. Nicht jeder
Passwortmanager oder jede Unternehmens-App veröffentlicht diese Kennzeichen; die Nichterfassung sensibler
Daten kann daher nicht garantiert werden.

Die drei Zustände des registrierten Windows-Formats `CanUploadToCloudClipboard` – nicht vorhanden, DWORD 1
(erlaubt), DWORD 0 (verboten) – werden bewahrt. Beim erneuten Veröffentlichen eines gespeicherten Elements wird
der ursprüngliche Zustand zuerst veröffentlicht, damit ein Cloud-Upload-Verbot der Quell-App nicht aufgehoben
wird. AroDamA selbst lädt den Inhalt nicht hoch und ändert keine Synchronisierungseinstellung von Windows oder
anderen Apps. Ungewöhnliche Länge oder Werte außer 0 und 1 werden nicht als Erlaubnis ausgelegt; die Erfassung
wird abgelehnt.

Der Standard-Passwortmanagerschutz ist nur ein Komfortfilter, der neue Inhalte vor dem Lesen überspringt, wenn
der Basisname exakt `1password.exe`, `bitwarden.exe`, `keepass.exe` oder `keepassxc.exe` lautet. Er ist keine
vollständige Sicherheitsgrenze für alle Versionen, Erweiterungen, Vermittlungsprozesse oder erhöhten Apps.
Der sensible Textfilter verwendet ebenfalls nur enge lokale Regeln und sendet weder Originaltext noch
Blockier-Hashes an Protokoll, Datenbank oder Netzwerk. Beide Funktionen löschen keine früheren Einträge.

Nutzer können die Erfassung pausieren, Apps ausschließen, Bild-/Dateierfassung abschalten, das Merken der
Ziel-App deaktiviert lassen, gespeicherte Zielnamen und Einträge löschen, den Löschspeicher leeren, Grenzen
senken und lokale Daten entfernen. Bei Passwörtern, Einmalcodes oder personenbezogenen Daten sollte die
Erfassung pausieren; weitere Sicherheits-Apps sollten ausgeschlossen, auf gemeinsam genutzten PCs getrennte
Windows-Konten und Bildschirmsperre verwendet und der Verlauf regelmäßig geprüft und gelöscht werden.

## 6. Netzwerkzugriff und Verarbeitung durch Dritte

AroDamA lädt Zwischenablageinhalte, lokale Datei- oder Pfadnamen, Textbausteine, OCR-Bilder oder -Ergebnisse,
Gedächtniszeitleisten und portable Backups weder zu PCSSAK noch zum Update-Server hoch. Nach der Zustimmung beim
ersten Start kann die App per HTTPS folgende offizielle GitHub-Release-Metadaten auf Updates prüfen:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

Die App vergleicht ihre Version mit Version, Veröffentlichungshinweisen, Download-URL und Integritätssignatur
der Antwort. Ein Installationsprogramm wird nur geladen, wenn der Nutzer die angebotene Installation ausdrücklich
wählt. GitHub kann Standard-Anfragedaten wie IP-Adresse, Zugriffszeit und User-Agent gemäß eigenen
Datenschutzbedingungen verarbeiten. AroDamA fügt weder Zwischenablageinhalt noch Nutzungsverlauf hinzu; Ort und
Dauer der Verarbeitung richten sich nach GitHubs Richtlinie.

Fehlt Microsoft Edge WebView2 Runtime, kann die Tauri-NSIS-Installation den WebView2-Bootstrapper von Microsoft
laden. Dies ist keine Übertragung von AroDamA-Zwischenablagedaten; Microsofts Richtlinie gilt. Speichert der Nutzer
ein verschlüsseltes Backup in einem von OneDrive oder einer anderen Drittanbieter-Synchronisierungs-App verwalteten
Ordner, kann diese die Datei nach eigenen Einstellungen und Datenschutzregeln hochladen.

Bevor künftig Konto-, Zahlungs-, Fernsupport-, Analyse- oder Absturzberichtsfunktionen aktiviert werden, wird
dieser Hinweis um tatsächlich übertragene Daten, Zweck, Aufbewahrung, Anbieter und mögliche internationale
Übertragung ergänzt und jede gesetzlich erforderliche Einwilligung eingeholt.

## 7. Nutzerrechte, Kontakt und Änderungen

Da es kein PCSSAK-Konto und keine zentrale Zwischenablagedatenbank gibt, kann PCSSAK lokale Inhalte nicht für
den Nutzer aus der Ferne abrufen, exportieren, berichtigen oder löschen. Nutzer steuern lokale Daten über die
Funktionen aus Abschnitt 5 und die offiziellen Löschhinweise.

Datenschutzanfragen: `privacy@pcssak.com`

Allgemeiner Support: `support@pcssak.com`

Details zu Schwachstellen, Zwischenablageinhalte, Datenbanken, Zugangsdaten oder identifizierende Protokolle
nicht in öffentlichen Issues veröffentlichen. Die private Schwachstellenmeldung von GitHub im offiziellen
öffentlichen Release-Repository verwenden.

PCSSAK ist derzeit der angezeigte Betreibername von Produkt und Website; dies allein behauptet keine Gesellschaft
oder eingetragene Firma in einem bestimmten Staat. Ein kostenpflichtiger Verkauf, der Angaben zum registrierten
Verkäufer oder gesonderte Verkaufsbedingungen erfordert, beginnt erst nach deren Festlegung und Veröffentlichung.

Bei Änderungen werden Datum und Version dieses Hinweises angepasst. Vor einer wesentlichen Erweiterung der
Datenverarbeitung werden Nutzer informiert und, soweit erforderlich, erneut um Einwilligung gebeten.

---

# Aviso de privacidad de PCSSAK AroDamA Free Early Access

- Versión del documento: 1.0
- Última actualización: 2026-09-01
- Aplicable a: PCSSAK AroDamA Free Early Access for Windows
- Nombre mostrado del operador: PCSSAK
- Consultas de privacidad: `privacy@pcssak.com`
- Asistencia general: `support@pcssak.com`

> Este texto en español es una traducción de referencia del texto rector en coreano. Si existen
> diferencias, el texto coreano prevalecerá únicamente en la medida permitida por la legislación
> aplicable. Prevalecen las normas imperativas de privacidad y protección del consumidor y los demás
> derechos irrenunciables del lugar de residencia del usuario. Este documento es un borrador operativo
> prudente, aún no revisado por profesionales jurídicos en cada jurisdicción, y no constituye asesoría legal.

## 1. Principios de tratamiento y consentimiento en el primer inicio

PCSSAK AroDamA es una aplicación de Windows que prioriza el tratamiento local. La versión Free Early
Access actual no incluye cuenta, publicidad, analítica de uso, sincronización en la nube, envío remoto
de informes de fallos, pagos ni validación remota de licencias. El historial del portapapeles y los ajustes
se administran en el PC del usuario. En la sección 6 se describe el acceso limitado a la red para comprobar
actualizaciones, realizar descargas aprobadas por el usuario y preparar WebView2.

En el primer inicio, la captura del portapapeles y la comprobación automática de actualizaciones permanecen
en pausa hasta que el usuario pueda abrir y revisar el EULA y este aviso en la aplicación, marque la casilla
de confirmación de los documentos y pulse expresamente el botón de inicio. La finalización y la reanudación
de la captura se guardan juntas. Los ajustes locales conservan las versiones aceptadas del EULA y de este
aviso, la huella del conjunto de documentos y la hora local de aceptación; el registro de aceptación no se
envía a una cuenta ni a un servidor. Un cambio sustancial de licencia o tratamiento incrementará la versión
del documento y pausará la captura hasta una nueva revisión. El instalador muestra el mismo EULA.

## 2. Datos tratados al utilizar las funciones

| Categoría | Ejemplos | Finalidad |
|---|---|---|
| Contenido del portapapeles | Texto, formato HTML/RTF, imágenes, listas de rutas de archivos físicos y nombres y bytes de archivos virtuales ofrecidos en memoria | Historial, búsqueda, vista previa y reutilización |
| Origen y destino | Nombre del proceso propietario del portapapeles y, solo si el usuario lo autoriza, nombre del ejecutable de destino del pegado automático | Búsqueda, indicación del origen, exclusiones y cronología fechada |
| Textos rápidos | Nombre y contenido creados por el usuario | Reutilización de textos frecuentes |
| Organización de recuerdos | Texto OCR solicitado, etiquetas, nombres y pertenencia a tableros, miniaturas de imágenes y orden de la cola de pegado | Búsqueda de texto en imágenes, clasificación y reutilización ordenada |
| Copia de seguridad portátil | Archivo cifrado que puede incluir registros activos y eliminados, textos rápidos, eventos, OCR y datos de organización al exportar | Recuperación o traslado a otro PC |
| Ajustes | Atajos, tema, idioma, límites, aplicaciones excluidas, pausa, captura de imágenes/archivos y finalización del aviso inicial | Conservar las preferencias |
| Metadatos operativos | Identificadores de elementos/eventos, tipo, horas de inicio/fin, resultado, cantidad, procedencia, método de pegado, tamaño, fijación y valor de duplicado | Ordenación, cronología, integridad, conservación y deduplicación |

La variable `{clipboard}` de los textos rápidos lee el texto actual de Windows solo al previsualizarlo o
utilizarlo. Esa lectura expresa no crea por sí sola un registro del historial y se rechaza si supera el
límite de texto configurado.

Recordar la aplicación de destino del pegado automático está desactivado de forma predeterminada. Si se
activa, solo se guarda el nombre base del ejecutable (por ejemplo, `notepad.exe`), no el título del documento
o de la ventana, la ruta completa, el PID ni el HWND. Desactivarlo solo afecta a eventos futuros. Una orden
independiente con confirmación en dos pasos elimina permanentemente de la base de datos actual únicamente los
nombres de destino anteriores, manteniendo fecha, tipo, resultado y cantidad del evento; el nombre eliminado
no puede recuperarse en la aplicación. No elimina los nombres de las aplicaciones de origen. Para no guardar
un origen, añada la aplicación a Aplicaciones excluidas o pause la captura. Las exclusiones y la protección
predeterminada de gestores de contraseñas, si está activa, se aplican también a futuros nombres de destino;
los cambios de ajustes no revisan ni eliminan retroactivamente datos ya guardados.

El bloqueo opcional de texto posiblemente sensible está desactivado de forma predeterminada. Al activarlo,
unas reglas locales limitadas omiten antes de guardar bloques de claves privadas reconocibles, formatos de
tokens de acceso identificables y formatos ordinarios de tarjetas que superen la validación de Luhn. Puede
haber falsos positivos y negativos, y los registros anteriores no se revisan ni eliminan. Por tanto, aún
pueden capturarse contraseñas, códigos de un solo uso y datos de identidad, financieros, médicos o laborales
confidenciales.

## 3. Almacenamiento, cifrado y protección de recuperación

Los datos nuevos se guardan en `%LOCALAPPDATA%\PCssak\AroDamA`. Solo si esa ubicación está vacía, la
aplicación puede copiar los ajustes y la base de datos antiguos de `%APPDATA%\ClipDeck`, sin borrar los archivos originales.

- El contenido, las vistas previas, HTML, RTF, imágenes, listas de archivos físicos/virtuales, contenido de
  textos rápidos, OCR, nombres de etiquetas y tableros y miniaturas de los registros activos y eliminados se
  protegen con Windows DPAPI en el ámbito del usuario actual y, en principio, solo se descifran en el mismo
  contexto de usuario de Windows.
- Para buscar, previsualizar, pegar y exportar copias, determinados datos deben estar descifrados en la memoria
  del proceso. Los búferes propios se sobrescriben después de usarlos cuando sea razonablemente posible.
- Los valores de deduplicación se calculan con HMAC-SHA-256 y un secreto por instalación. La clave se almacena
  protegida por DPAPI en `dedup-key.bin`; HMAC no sustituye al cifrado del contenido.
- Los filtros de candidatos de búsqueda de texto completo usan otra clave HMAC por instalación protegida por
  DPAPI. No guardan palabras ni contenidos en claro, pero no constituyen una búsqueda totalmente cifrada que
  oculte todos los patrones de longitud o acceso. Las coincidencias se confirman descifrando cada candidato en memoria.
- Algunos metadatos operativos pueden estar en claro: aplicación de origen del elemento actual, ajustes y
  estructura de la base de datos, nombre del texto rápido, identificadores, tipos, horas, resultados, cantidades,
  procedencia, método de pegado, hora de conservación, tamaño, fijación y relaciones organizativas. Los nombres
  de ejecutables de origen o destino opcional dentro de eventos se protegen mediante DPAPI.
- DPAPI no protege frente a software malicioso que ya se ejecute como el mismo usuario de Windows desbloqueado,
  captura de pantalla o teclado, ataques a memoria, control remoto autorizado por el usuario ni acceso físico a un PC desbloqueado.

Antes de migrar se verifica la integridad de SQLite. Un cambio necesario de esquema o HMAC crea una copia de
recuperación coherente, enlazada de forma inequívoca mediante una marca aleatoria dentro de la base de datos y
el SHA-256 de la instantánea. Un cambio interrumpido continúa en el siguiente inicio. La copia enlazada solo se
elimina cuando se verifican la base actual, el esquema, las tablas y columnas obligatorias, la marca de clave y
el estado WAL; las copias no enlazadas o de procedencia no demostrada no se borran automáticamente. Se trata de
recuperación ante fallos, no de un servicio externo de copias. No mueva ni borre manualmente las carpetas de datos
antes de las pruebas finales con datos reales y escenarios de fallo y recuperación.

El esquema v5 no contenía un historial por evento. La migración a v6 crea únicamente un resumen en la última
hora de copia conocida y, si existe un total de pegados automáticos, un resumen en su última hora de pegado;
no estima horas, destinos, métodos ni resultados individuales anteriores. El esquema v8 vincula RTF, imágenes
registradas, archivos virtuales, el estado original de `CanUploadToCloudClipboard`, filtros de búsqueda, OCR,
etiquetas, tableros y colas de pegado al mismo ciclo de vida `memory_id`.

El OCR se ejecuta localmente con los paquetes de idioma OCR de Windows instalados y no sube las imágenes. Los
resultados pueden ser inexactos, el usuario puede borrarlos y no deben considerarse una transcripción oficial.

Una copia portátil descifra los registros lógicos de una instantánea SQLite coherente en el contexto del usuario
actual de Windows y los vuelve a cifrar inmediatamente con la contraseña introducida mediante Argon2id y
XChaCha20-Poly1305. La contraseña y la clave derivada no se guardan ni envían, y la memoria se sobrescribe después
cuando sea razonablemente posible. PCSSAK no puede recuperar una contraseña olvidada ni un archivo perdido. La
copia puede contener registros activos y eliminados, textos rápidos, eventos, OCR y organización en el momento
de exportar; el usuario controla la seguridad y conservación de la ubicación, dispositivo externo o servicio de
sincronización. La importación valida un candidato aislado y sustituye la base actual en vez de combinarla. Una
copia antigua puede hacer reaparecer datos ya eliminados de la aplicación actual.

## 4. Plazos de conservación, eliminación y restauración

El límite de cantidad elegido se aplica a registros ordinarios no organizados. Los registros fijados o vinculados
a OCR, etiquetas, tableros o una cola de pegado quedan protegidos de la limpieza por cantidad, por lo que el total
real puede ser mayor. Todos los datos, protegidos o no, cuentan además para un límite lógico independiente de
512 MB. La limpieza automática por cantidad no pasa por el almacén de eliminados manual y también elimina los eventos vinculados.

La eliminación individual o «Vaciar historial» mueve el registro y sus eventos al ciclo de registros eliminados
local de AroDamA, no a la Papelera de reciclaje de Windows. La eliminación por intervalo incluye ambas fechas según
la fecha local de copia y protege los registros fijados. Una fecha futura no programa una eliminación.

- La restauración gratuita está disponible hasta exactamente 24 horas después de la eliminación.
- Transcurridas 24 horas, la versión Free Early Access actual no puede restaurar el registro, aunque el contenido
  y los eventos cifrados pueden permanecer en el mismo PC y para el mismo usuario de Windows hasta 30 días desde
  la eliminación. El producto actual no incluye función ni interfaz Pro, de pago, venta o activación remota de
  licencia que permita abrirlos.
- Los registros eliminados y sus eventos cuentan para el mismo límite lógico de 512 MB que el historial, las fijaciones y los textos rápidos.
- El usuario puede borrarlos permanentemente antes. Los datos que cumplen exactamente 30 días se eliminan de la
  base de la aplicación en la siguiente limpieza y ya no pueden restaurarse en la aplicación.

La caducidad o eliminación permanente retira contenido y eventos vinculados de la base actual a nivel de la
aplicación; no es un borrado seguro del soporte físico. Pueden quedar rastros en páginas libres o WAL de SQLite,
copias de recuperación de migración conservadas, copias de Windows o de la organización, zonas de recuperación
de disco o copias sincronizadas por terceros. El borrado de un nombre de aplicación de destino también retira
solo el texto cifrado de la base actual y no sobrescribe copias separadas.

El límite de restauración de 24 horas, la caducidad de 30 días y las horas de eventos usan el reloj local de
Windows. Cambios importantes del reloj pueden afectar a la visualización, restauración y caducidad. La cronología
no está firmada por una fuente horaria fiable y no es un registro de auditoría inalterable ni una prueba jurídica.
El almacén de eliminados y las copias portátiles son independientes; AroDamA no puede recuperar una base, archivo
de copia o contraseña perdidos.

Una desinstalación normal conserva el historial y los ajustes de
`%LOCALAPPDATA%\PCssak\AroDamA`. Solo si el usuario selecciona expresamente
`Eliminar datos de la aplicación` en el desinstalador se eliminan, conforme a una lista de permitidos exacta,
los ajustes, la base de datos, las claves de protección, las instantáneas de recuperación de migraciones y los
candidatos de restauración verificados que administra AroDamA. Aun así, no se elimina de forma recursiva la
raíz compartida `PCssak\AroDamA`, ni se borran los archivos `.arodama-backup` exportados por el usuario, las
copias de seguridad o de reversión guardadas en otra ubicación, las copias sincronizadas ni las copias de
conservación de una organización. Revise y elimine esas copias por separado si lo desea.

## 5. Minimización de datos sensibles y controles del usuario

AroDamA respeta exclusiones reconocibles del portapapeles de Windows como `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing` y `CanIncludeInClipboardHistory=0`. No todos los gestores de
contraseñas o programas empresariales publican estas marcas, por lo que no puede garantizarse la no captura de datos sensibles.

La aplicación conserva los tres estados del formato registrado de Windows `CanUploadToCloudClipboard`: ausente,
DWORD 1 (permitido) y DWORD 0 (bloqueado). Al volver a publicar un elemento, publica primero el estado original
para no anular la intención de la aplicación de origen de impedir la subida a la nube. AroDamA no sube el contenido
ni cambia los ajustes de sincronización de Windows u otros programas. Una longitud anómala o un valor distinto de
0 o 1 no se interpreta como permiso; la captura se rechaza.

La protección predeterminada de gestores de contraseñas es solo un filtro práctico que omite el contenido antes
de leerlo cuando el nombre base del ejecutable coincide exactamente con `1password.exe`, `bitwarden.exe`,
`keepass.exe` o `keepassxc.exe`. No es una barrera de seguridad completa para todas las versiones, extensiones,
procesos intermediarios o programas elevados. El filtro sensible también utiliza reglas locales limitadas y no
envía el texto original ni hashes bloqueados a registros, base de datos o red. Ninguno elimina registros anteriores.

El usuario puede pausar la captura, excluir aplicaciones, desactivar la captura de imágenes/archivos, mantener
desactivada la memoria del destino, borrar nombres y registros, vaciar el almacén de eliminados, reducir límites y
quitar datos locales. Al manejar contraseñas, códigos de un solo uso o datos personales, pause la captura; excluya
programas de seguridad que no estén en la lista; use una cuenta de Windows separada y bloquee la pantalla en equipos
compartidos; y revise y elimine el historial periódicamente.

## 6. Acceso a la red y tratamiento por terceros

AroDamA no sube a PCSSAK ni al servidor de actualizaciones el contenido del portapapeles, nombres o rutas de archivos
locales, textos rápidos, imágenes o resultados OCR, cronologías ni copias portátiles. Tras el consentimiento inicial,
puede comprobar mediante HTTPS los metadatos oficiales de GitHub Release en:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

La aplicación compara su versión con la versión, notas de publicación, URL de descarga y firma de integridad de la
respuesta. Solo descarga el instalador si el usuario elige expresamente instalar la actualización ofrecida. GitHub
puede tratar datos estándar de la solicitud, como dirección IP, hora de acceso y agente de usuario, conforme a sus
propias condiciones de privacidad. AroDamA no añade contenido del portapapeles ni historial de uso; la política de
GitHub rige el lugar y el plazo de su tratamiento.

Si falta Microsoft Edge WebView2 Runtime, la instalación Tauri NSIS puede descargar el instalador inicial de
WebView2 desde Microsoft. No es una transferencia de datos del portapapeles de AroDamA y se aplica la política de
Microsoft. Si el usuario guarda una copia cifrada en una carpeta gestionada por OneDrive u otra aplicación de
sincronización de terceros, esta puede subir el archivo conforme a sus propios ajustes y política de privacidad.

Antes de activar en el futuro cuentas, pagos, asistencia remota, analítica o informes de fallos, este aviso se
actualizará con los datos realmente transmitidos, finalidad, conservación, proveedores y posible transferencia
internacional, y se obtendrá el consentimiento exigido por la legislación aplicable.

## 7. Derechos del usuario, contacto y cambios del aviso

Al no existir una cuenta PCSSAK ni una base central del portapapeles, PCSSAK no puede recuperar, exportar, rectificar
ni borrar remotamente el contenido local en nombre del usuario. El usuario controla sus datos mediante las funciones
de la sección 5 y las instrucciones oficiales de eliminación.

Consultas de privacidad: `privacy@pcssak.com`

Asistencia general: `support@pcssak.com`

No publique en una incidencia pública detalles de vulnerabilidades, contenido del portapapeles, bases de datos,
credenciales ni registros identificativos. Utilice el sistema privado de notificación de vulnerabilidades de GitHub
del repositorio público oficial de versiones.

PCSSAK es el nombre de operador mostrado actualmente en el producto y el sitio web; ese nombre por sí solo no afirma
la existencia de una sociedad o nombre comercial registrado en un país concreto. Cualquier venta de pago que exija
identificación del vendedor registrado o condiciones de venta separadas solo comenzará cuando se definan y publiquen.

Cuando cambie este aviso se actualizarán su fecha y versión. Se informará al usuario antes de que entre en vigor una
ampliación sustancial del tratamiento y se solicitará de nuevo su consentimiento cuando corresponda.

---

# Aviso de Privacidade do PCSSAK AroDamA Free Early Access

- Versão do documento: 1.0
- Última atualização: 2026-09-01
- Aplicável a: PCSSAK AroDamA Free Early Access for Windows
- Nome de exibição do operador: PCSSAK
- Dúvidas sobre privacidade: `privacy@pcssak.com`
- Suporte geral: `support@pcssak.com`

> Este texto em português do Brasil é uma tradução de referência do texto oficial em coreano. Em caso
> de divergência, o texto coreano prevalecerá somente na medida permitida pela legislação aplicável.
> Prevalecem as normas obrigatórias de privacidade e proteção do consumidor e os demais direitos
> irrenunciáveis do local de residência do usuário. Este aviso é uma minuta operacional conservadora,
> ainda não revisada por profissionais jurídicos em todas as jurisdições, e não constitui aconselhamento jurídico.

## 1. Princípios de tratamento e consentimento no primeiro uso

O PCSSAK AroDamA é um aplicativo Windows que prioriza o processamento local. A versão Free Early Access
atual não possui conta, publicidade, análise de uso, sincronização em nuvem, envio remoto de falhas, pagamento
nem validação remota de licença. O histórico da área de transferência e as configurações são gerenciados no PC
do usuário. O acesso limitado à rede para verificar atualizações, fazer downloads aprovados pelo usuário e
preparar o WebView2 está descrito na Seção 6.

Na primeira inicialização, a captura da área de transferência e a verificação automática de atualizações ficam
pausadas até que o usuário possa abrir e analisar o EULA e este aviso no aplicativo, marque a caixa de confirmação
dos documentos e pressione explicitamente o botão de iniciar. A conclusão e a retomada da captura são salvas em
conjunto. As configurações locais registram as versões aceitas do EULA e deste aviso, a impressão digital do conjunto
de documentos e o horário local de aceitação; esse registro não é enviado a uma conta nem a um servidor. Alterações
substanciais na licença ou no tratamento elevam a versão do documento e pausam a captura até uma nova análise.
O instalador apresenta o mesmo EULA.

## 2. Dados tratados durante o uso dos recursos

| Categoria | Exemplos | Finalidade |
|---|---|---|
| Conteúdo da área de transferência | Texto, formatação HTML/RTF, imagens, listas de caminhos de arquivos físicos e nomes e bytes de arquivos virtuais fornecidos na memória | Histórico, pesquisa, visualização e reutilização |
| Origem e destino | Nome do processo proprietário da área de transferência e, somente com adesão, nome do executável de destino da colagem automática | Pesquisa, exibição de origem, exclusões e linha do tempo datada |
| Textos rápidos | Nome e conteúdo criados pelo usuário | Reutilização de textos frequentes |
| Organização de memórias | Texto OCR solicitado, etiquetas, nomes e associações de quadros, miniaturas e ordem da fila de colagem | Pesquisa em imagens, classificação e reutilização ordenada |
| Backup portátil | Arquivo criptografado que pode conter registros ativos e excluídos, textos rápidos, eventos, OCR e organização na data da exportação | Recuperação ou transferência para outro PC |
| Configurações | Atalhos, tema, idioma, limites, aplicativos excluídos, pausa, captura de imagens/arquivos e conclusão da orientação inicial | Manter as preferências |
| Metadados operacionais | Identificadores de item/evento, tipo, horários de início/fim, resultado, contagem, procedência, método de colagem, tamanho, fixação e valor de duplicidade | Ordenação, linha do tempo, integridade, retenção e deduplicação |

A variável `{clipboard}` dos textos rápidos lê o texto atual do Windows somente na visualização ou no uso.
Essa leitura explícita, por si só, não cria um registro no histórico e é recusada acima do limite de texto configurado.

Lembrar o aplicativo de destino da colagem automática vem desativado. Quando ativado, somente o nome-base do
executável (por exemplo, `notepad.exe`) é salvo, e não o título do documento ou janela, caminho completo, PID ou
HWND. Desativar afeta apenas eventos futuros. Um comando separado com confirmação em duas etapas remove
permanentemente apenas os nomes de destino anteriores do banco de dados atual, preservando data, tipo, resultado
e contagem do evento; o nome removido não pode ser restaurado no aplicativo. Isso não remove nomes de aplicativos
de origem. Para não registrar uma origem, inclua o aplicativo na lista de exclusões ou pause a captura. Exclusões
e a proteção padrão ativada para gerenciadores de senhas também se aplicam a futuros nomes de destino, mas alterações
nas configurações não inspecionam nem apagam retroativamente dados já salvos.

O bloqueador opcional de texto possivelmente sensível vem desativado. Quando ativado, regras locais restritas
ignoram, antes de salvar, blocos reconhecíveis de chaves privadas, formatos identificáveis de tokens de acesso e
formatos comuns de cartões que passem na verificação de Luhn. Podem ocorrer falsos positivos e negativos, e os
registros existentes não são analisados nem excluídos. Assim, senhas, códigos de uso único e dados de identidade,
financeiros, médicos ou profissionais confidenciais ainda podem ser capturados.

## 3. Armazenamento, criptografia e proteção de recuperação

Os novos dados são salvos em `%LOCALAPPDATA%\PCssak\AroDamA`. Somente quando esse local está vazio, o aplicativo
pode copiar as configurações e o banco de dados antigos de `%APPDATA%\ClipDeck`, sem apagar os arquivos originais.

- Conteúdos, visualizações, HTML, RTF, imagens, listas de arquivos físicos/virtuais, conteúdo de textos rápidos,
  OCR, nomes de etiquetas/quadros e miniaturas de registros ativos e excluídos são protegidos pelo Windows DPAPI
  no escopo do usuário atual e, em princípio, só podem ser descriptografados no mesmo contexto de usuário do Windows.
- Pesquisa, visualização, colagem e exportação exigem que dados selecionados sejam descriptografados na memória do
  processo. Os buffers controlados pelo aplicativo são sobrescritos após o uso quando razoavelmente possível.
- Os valores de deduplicação usam HMAC-SHA-256 com um segredo específico da instalação. A chave é protegida por
  DPAPI em `dedup-key.bin`; HMAC não substitui a criptografia do conteúdo.
- Os filtros de candidatos da pesquisa de texto completo usam outra chave HMAC específica da instalação, protegida
  por DPAPI. Eles não armazenam palavras nem conteúdos em texto simples, mas não são uma pesquisa totalmente
  criptografada que oculte todos os padrões de comprimento ou acesso. A correspondência é confirmada pela
  descriptografia individual dos candidatos na memória.
- Alguns metadados operacionais podem permanecer em texto simples: aplicativo de origem do item atual, configurações
  e estrutura do banco, nome do texto rápido, identificadores, tipos, horários, resultados, contagens, procedência,
  método de colagem, tempo de retenção, tamanho, fixação e relações de organização. Nomes de executáveis de origem
  ou destino opcional dentro de eventos são protegidos por DPAPI.
- DPAPI não protege contra malware executado com os direitos do mesmo usuário do Windows desbloqueado, captura de
  tela ou teclado, ataques à memória, acesso remoto autorizado pelo usuário nem acesso físico a um PC desbloqueado.

Antes de uma migração, controles de integridade do SQLite verificam o banco existente. Uma transição necessária de
esquema ou HMAC cria uma cópia consistente de recuperação, vinculada de modo inequívoco por um marcador aleatório
interno e pelo SHA-256 do instantâneo. Uma transição interrompida continua na próxima inicialização. A cópia vinculada
só é removida depois de verificar o banco atual, esquema, tabelas e colunas obrigatórias, marcador de chave e estado
do WAL; cópias não vinculadas ou sem origem comprovada não são apagadas automaticamente. Isso é recuperação de falha,
não um serviço externo de backup. Não mova nem exclua manualmente as pastas de dados antes dos testes finais com dados
reais e cenários de falha e recuperação.

O esquema v5 não possuía histórico por evento. A migração para v6 cria apenas um resumo no último horário de cópia
conhecido e, se houver um total de colagens automáticas, um resumo no último horário de colagem conhecido; não estima
horários, destinos, métodos nem resultados individuais do passado. O esquema v8 vincula RTF, imagens registradas,
arquivos virtuais, o estado original de `CanUploadToCloudClipboard`, filtros de pesquisa, OCR, etiquetas, quadros e
filas de colagem ao mesmo ciclo de vida `memory_id`.

O OCR funciona localmente com os pacotes de idiomas OCR do Windows instalados e não envia imagens. Os resultados podem
ser imprecisos, podem ser excluídos pelo usuário e não são uma transcrição oficial do documento original.

O backup portátil descriptografa os registros lógicos de um instantâneo SQLite consistente no contexto do usuário
atual do Windows e os recriptografa imediatamente com a senha informada, usando Argon2id e XChaCha20-Poly1305. A senha
e a chave derivada não são armazenadas nem enviadas; a memória é sobrescrita após a operação quando razoavelmente
possível. A PCSSAK não consegue recuperar uma senha esquecida nem um arquivo perdido. O backup pode conter registros
ativos e excluídos, textos rápidos, eventos, OCR e organização na data de exportação; o usuário administra segurança
e retenção do local, mídia externa ou serviço de sincronização. A importação valida um candidato isolado e substitui,
em vez de mesclar, o banco atual. Restaurar um backup antigo pode trazer de volta dados já excluídos do aplicativo atual.

## 4. Prazos de retenção, exclusão e restauração

O limite de quantidade definido pelo usuário se aplica a registros comuns não organizados. Registros fixados ou
vinculados a OCR, etiquetas, quadros ou fila de colagem são protegidos da limpeza por quantidade, portanto a quantidade
real pode ser maior. Todos os dados, protegidos ou não, também estão sujeitos a um limite lógico separado de 512 MB.
A limpeza automática por quantidade ignora o armazenamento de excluídos manual e remove eventos vinculados.

A exclusão individual ou Limpar histórico move o registro e seus eventos para o ciclo local de registros excluídos do
AroDamA, e não para a Lixeira do Windows. A exclusão por intervalo inclui as duas datas com base na data local da cópia
e protege registros fixados. Uma data futura não agenda exclusão.

- A restauração gratuita está disponível até exatamente 24 horas após a exclusão.
- Após 24 horas, o Free Early Access atual não consegue restaurar o registro, embora conteúdo e eventos criptografados
  possam permanecer no mesmo PC, para o mesmo usuário do Windows, por até 30 dias desde a exclusão. O produto atual
  não possui função nem interface Pro, pagamento, venda ou ativação remota de licença que os libere.
- Registros excluídos e eventos contam para o mesmo limite lógico de 512 MB que histórico, itens fixados e textos rápidos.
- O usuário pode excluir permanentemente antes. Dados que atingem exatamente 30 dias são removidos do banco do
  aplicativo na próxima limpeza e não podem ser restaurados pelo aplicativo.

Expiração ou exclusão permanente remove conteúdo e eventos vinculados do banco atual no nível do aplicativo; não é
apagamento seguro da mídia física. Podem permanecer vestígios em páginas livres ou WAL do SQLite, arquivos de recuperação
de migração mantidos, backups do Windows ou da organização, áreas de recuperação de disco ou cópias sincronizadas por
terceiros. Excluir um nome de destino também remove apenas o texto cifrado do banco atual e não sobrescreve cópias separadas.

O limite de 24 horas, a expiração de 30 dias e os horários dos eventos usam o relógio local do Windows. Grandes mudanças
no relógio podem afetar exibição, restauração e expiração. A linha do tempo não é assinada por uma fonte confiável de
tempo e não é um registro de auditoria inviolável nem prova jurídica. O armazenamento de excluídos e os backups portáteis
são separados; o AroDamA não recupera banco, arquivo de backup ou senha perdidos.

Uma desinstalação normal preserva o histórico e as configurações em
`%LOCALAPPDATA%\PCssak\AroDamA`. Somente se o usuário selecionar expressamente
`Excluir dados do aplicativo` no desinstalador serão excluídos, conforme uma lista de permissões exata, as
configurações, o banco de dados, as chaves de proteção, os instantâneos de recuperação de migração e os
candidatos de restauração verificados gerenciados pelo AroDamA. Mesmo assim, a raiz compartilhada
`PCssak\AroDamA` não será excluída de forma recursiva, nem serão excluídos arquivos `.arodama-backup`
exportados pelo usuário, backups ou cópias de reversão em outro local, cópias sincronizadas ou cópias de retenção
de uma organização. Verifique e remova essas cópias separadamente, se desejar.

## 5. Minimização de dados sensíveis e controles do usuário

O AroDamA respeita exclusões reconhecíveis da área de transferência do Windows, incluindo `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing` e `CanIncludeInClipboardHistory=0`. Nem todo gerenciador de senhas ou
aplicativo corporativo publica essas marcações, portanto não é possível garantir que dados sensíveis nunca sejam capturados.

O aplicativo preserva os três estados do formato registrado do Windows `CanUploadToCloudClipboard`: ausente, DWORD 1
(permitido) e DWORD 0 (bloqueado). Ao republicar um item salvo, publica primeiro o estado original para não eliminar a
intenção do aplicativo de origem de impedir o envio à nuvem. O AroDamA não envia o conteúdo nem altera as configurações
de sincronização do Windows ou de outros aplicativos. Comprimento anormal ou valor diferente de 0 ou 1 não é presumido
como permissão; a captura é recusada.

A proteção padrão para gerenciadores de senhas é apenas um filtro de conveniência que ignora um novo conteúdo antes de
lê-lo quando o nome-base do executável corresponde exatamente a `1password.exe`, `bitwarden.exe`, `keepass.exe` ou
`keepassxc.exe`. Não é uma barreira de segurança completa para todas as versões, extensões, processos intermediários ou
aplicativos elevados. O filtro de texto sensível também usa regras locais restritas e não envia o texto original nem
hashes bloqueados a logs, banco de dados ou rede. Nenhum dos controles exclui registros antigos.

O usuário pode pausar a captura, excluir aplicativos, desativar a captura de imagens/arquivos, manter desativada a memória
do destino, apagar nomes e registros, esvaziar o armazenamento de excluídos, reduzir limites e remover dados locais. Ao
tratar senhas, códigos de uso único ou dados pessoais, pause a captura; exclua aplicativos de segurança fora da lista;
use uma conta separada do Windows e bloqueie a tela em PCs compartilhados; e analise e apague o histórico periodicamente.

## 6. Acesso à rede e tratamento por terceiros

O AroDamA não envia para a PCSSAK nem para o servidor de atualização o conteúdo da área de transferência, nomes ou caminhos
de arquivos locais, textos rápidos, imagens ou resultados OCR, linhas do tempo nem backups portáteis. Após o consentimento
inicial, pode verificar por HTTPS os metadados oficiais do GitHub Release em:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

O aplicativo compara sua versão com a versão, notas da versão, URL de download e assinatura de integridade da resposta.
Só baixa o instalador quando o usuário escolhe explicitamente instalar a atualização oferecida. O GitHub pode tratar
dados padrão da solicitação, como endereço IP, horário de acesso e agente do usuário, conforme seus próprios termos de
privacidade. O AroDamA não acrescenta conteúdo da área de transferência nem histórico de uso; a política do GitHub rege
o local e o período do tratamento.

Se o Microsoft Edge WebView2 Runtime não estiver presente, a instalação Tauri NSIS poderá baixar da Microsoft o bootstrapper
do WebView2. Isso não é transferência de dados da área de transferência pelo AroDamA, e aplica-se a política da Microsoft.
Se o usuário salvar um backup criptografado em pasta gerenciada pelo OneDrive ou outro aplicativo de sincronização de
terceiros, esse aplicativo poderá enviar o arquivo conforme suas próprias configurações e política de privacidade.

Antes de ativar futuramente conta, pagamento, suporte remoto, análise ou relatório de falhas, este aviso será atualizado
com os dados efetivamente transmitidos, finalidade, retenção, fornecedores e possível transferência internacional, e será
obtido o consentimento exigido pela legislação aplicável.

## 7. Direitos do usuário, contato e alterações do aviso

Como não há conta PCSSAK nem banco central da área de transferência, a PCSSAK não consegue recuperar, exportar, corrigir
ou apagar remotamente o conteúdo local em nome do usuário. O usuário controla os dados locais com os recursos da Seção 5
e as orientações oficiais de exclusão.

Dúvidas sobre privacidade: `privacy@pcssak.com`

Suporte geral: `support@pcssak.com`

Não publique em issues públicas detalhes de vulnerabilidades, conteúdo da área de transferência, bancos de dados,
credenciais ou logs identificáveis. Use o recurso privado de comunicação de vulnerabilidades do GitHub no repositório
público oficial de versões.

PCSSAK é o nome de exibição atual do operador do produto e do site; esse nome, por si só, não afirma a existência de
pessoa jurídica ou nome empresarial registrado em determinado país. Qualquer venda paga que exija identificação do
vendedor registrado ou condições de venda separadas só começará depois que essas informações e condições forem definidas e publicadas.

Quando este aviso mudar, sua data e versão serão atualizadas. O usuário será informado antes de entrar em vigor uma
ampliação substancial do tratamento e será solicitado novo consentimento quando necessário.

---

# PCSSAK AroDamA Free Early Access Gizlilik Bildirimi

- Belge sürümü: 1.0
- Son güncelleme: 2026-09-01
- Kapsam: PCSSAK AroDamA Free Early Access for Windows
- Görünen işletmeci adı: PCSSAK
- Gizlilik iletişimi: `privacy@pcssak.com`
- Genel destek: `support@pcssak.com`

> Bu Türkçe metin, esas Korece metnin bilgilendirme amaçlı çevirisidir. Metinler arasında farklılık
> varsa Korece metin yalnızca yürürlükteki hukukun izin verdiği ölçüde esas alınır. Kullanıcının ikamet
> ettiği yerdeki emredici gizlilik ve tüketiciyi koruma kuralları ile vazgeçilemeyen diğer haklar önceliklidir.
> Bu bildirim, her yargı alanında uzman hukuk incelemesi henüz tamamlanmamış ihtiyatlı bir işletim taslağıdır;
> hukuki danışmanlık niteliği taşımaz.

## 1. İşleme ilkeleri ve ilk çalıştırma onayı

PCSSAK AroDamA, yerel işlemeyi önceleyen bir Windows uygulamasıdır. Mevcut Free Early Access sürümünde hesap,
reklam, kullanım analitiği, bulut eşitleme, uzaktan çökme raporu, ödeme veya uzaktan lisans doğrulama yoktur.
Pano geçmişi ve ayarlar kullanıcının bilgisayarında yönetilir. Güncelleme denetimi, kullanıcının onayladığı
indirme ve WebView2 hazırlığı için sınırlı ağ erişimi Bölüm 6'da açıklanmıştır.

İlk çalıştırmada kullanıcı uygulama içinde EULA'yı ve bu bildirimi açıp inceleyene, belge onay kutusunu işaretleyip
başlat düğmesine açıkça basana kadar pano yakalama ve otomatik güncelleme denetimi duraklatılır. Tamamlama ve
yakalamanın yeniden başlaması birlikte kaydedilir. Yerel ayarlar, kabul edilen EULA ve gizlilik bildirimi sürümlerini,
belge kümesinin parmak izini ve yerel kabul zamanını saklar; kabul kaydı bir hesaba veya sunucuya gönderilmez. Lisans
ya da veri işlemede önemli bir değişiklik olursa belge sürümü yükseltilir ve yeniden incelemeye kadar yakalama durur.
Yükleyici de aynı EULA'yı gösterir.

## 2. Özellikler kullanıldığında işlenen veriler

| Kategori | Örnekler | Amaç |
|---|---|---|
| Pano içeriği | Metin, HTML/RTF biçimi, görseller, fiziksel dosya yolu listeleri ve bellekte sağlanan sanal dosya adları ile baytları | Geçmiş, arama, önizleme ve yeniden kullanım |
| Kaynak ve hedef | Panonun sahibi işlem adı ve yalnızca kullanıcı seçerse otomatik yapıştırma hedefinin çalıştırılabilir dosya adı | Arama, kaynak gösterimi, hariç tutma ve tarihli hafıza zaman çizelgesi |
| Hızlı metin | Kullanıcının oluşturduğu ad ve içerik | Sık kullanılan metinleri yeniden kullanma |
| Hafıza düzenleme | İstenen OCR metni, etiketler, pano adları ve üyelikleri, görsel küçük resimleri ve yapıştırma kuyruğu sırası | Görselde metin arama, sınıflandırma ve sıralı kullanım |
| Taşınabilir yedek | Dışa aktarma anındaki etkin ve silinmiş kayıtları, hızlı metni, olayları, OCR ve düzenleme verilerini içerebilen şifreli dosya | Kurtarma veya başka bilgisayara taşıma |
| Ayarlar | Kısayollar, tema, dil, saklama sınırları, hariç uygulamalar, duraklatma, görsel/dosya yakalama ve ilk bildirim tamamlama | Kullanıcı tercihlerini koruma |
| İşletim meta verileri | Öğe/olay kimliği, tür, başlangıç/bitiş zamanı, sonuç, sayı, kaynak sınıfı, yapıştırma yöntemi, boyut, sabitleme ve yinelenen değer | Sıralama, zaman çizelgesi, bütünlük, saklama ve tekilleştirme |

Hızlı metindeki `{clipboard}` değişkeni mevcut Windows metnini yalnızca önizleme veya kullanım sırasında okur.
Bu açık okuma tek başına geçmişe yeni kayıt eklemez ve ayarlı metin sınırını aşarsa reddedilir.

Otomatik yapıştırma hedefi uygulamasını hatırlama varsayılan olarak kapalıdır. Açıldığında yalnızca çalıştırılabilir
dosyanın temel adı (ör. `notepad.exe`) saklanır; belge/pencere başlığı, tam yol, PID veya HWND saklanmaz. Kapatma
yalnızca sonraki olayları etkiler. İki adımlı onay gerektiren ayrı bir komut, tarih, tür, sonuç ve sayı gibi olay
bilgilerini koruyarak yalnızca geçmiş hedef adlarını geçerli veritabanından kalıcı siler; silinen ad uygulamada geri
alınamaz. Kaynak uygulama adları silinmez. Bir kaynağı saklamamak için uygulamayı Hariç tutulan uygulamalara ekleyin
veya yakalamayı duraklatın. Hariç tutmalar ve etkin standart parola yöneticisi koruması sonraki hedef adlarına da
uygulanır; ayar değişikliği önceden saklanan veriyi geriye dönük incelemez veya silmez.

Olası hassas metin engelleyicisi varsayılan olarak kapalıdır. Açıldığında dar kapsamlı yerel kurallar, tanınabilir
özel anahtar bloklarını, erişim belirteci biçimlerini ve Luhn denetimini geçen yaygın ödeme kartı biçimlerini
kaydetmeden önce atlar. Yanlış olumlu ve yanlış olumsuz sonuçlar olabilir; eski kayıtlar incelenmez veya silinmez.
Parolalar, tek kullanımlık kodlar, kimlik, mali, sağlık veya gizli iş verileri bu nedenle yine yakalanabilir.

## 3. Saklama, şifreleme ve kurtarma koruması

Yeni veriler `%LOCALAPPDATA%\PCssak\AroDamA` altında saklanır. Yalnızca bu konum boşsa eski
`%APPDATA%\ClipDeck` ayarları ve veritabanı kopyalanabilir; eski dosyalar silinmez.

- Etkin ve silinmiş kayıtların içeriği, önizlemeleri, HTML, RTF, görseller, fiziksel/sanal dosya listeleri,
  hızlı metin içerikleri, OCR, etiket/pano adları ve küçük resimler mevcut kullanıcı kapsamındaki Windows DPAPI
  ile korunur ve kural olarak yalnızca aynı Windows kullanıcı bağlamında çözülebilir.
- Arama, önizleme, yapıştırma ve yedek dışa aktarma sırasında seçilen verilerin işlem belleğinde çözülmesi gerekir.
  Uygulamanın sahip olduğu arabellekler kullanımdan sonra makul ölçüde üzerine yazılır.
- Tekilleştirme değerleri kurulum başına gizli anahtarla HMAC-SHA-256 kullanır. Anahtar `dedup-key.bin` içinde
  DPAPI korumalıdır; HMAC içerik şifrelemesinin yerini tutmaz.
- Tam metin arama aday filtreleri ayrı, kurulum başına DPAPI korumalı bir HMAC anahtarı kullanır. Düz metin sözcük
  veya içerik saklamaz; ancak bütün uzunluk ve erişim örüntülerini gizleyen tam şifreli arama değildir. Gerçek eşleşme,
  adayların bellekte tek tek çözülmesiyle doğrulanır.
- Bazı işletim meta verileri düz metin olabilir: geçerli öğenin kaynak uygulaması, ayarlar ve veritabanı yapısı,
  hızlı metin adı, kimlikler, türler, zamanlar, sonuçlar, sayılar, kaynak sınıfı, yapıştırma yöntemi, saklama zamanı,
  boyut, sabitleme ve düzenleme ilişkileri. Olaylardaki kaynak veya isteğe bağlı hedef çalıştırılabilir dosya adları
  DPAPI ile korunur.
- DPAPI, aynı kilidi açık Windows kullanıcısı olarak çalışan kötü amaçlı yazılıma, ekran/klavye kaydına, bellek
  saldırılarına, kullanıcının izin verdiği uzaktan denetime veya kilidi açık bilgisayara fiziksel erişime karşı korumaz.

Geçişten önce SQLite bütünlüğü denetlenir. Gerekli şema veya HMAC geçişinde, veritabanı içindeki rastgele bir geçiş
işareti ve anlık görüntünün SHA-256 değeriyle kesin olarak bağlanan tutarlı kurtarma kopyası oluşturulur. Kesilen geçiş
sonraki başlangıçta sürer. Bağlı kopya ancak mevcut veritabanı, şema, zorunlu tablo/sütunlar, anahtar işareti ve WAL
durumu doğrulandıktan sonra silinir; bağlantısı ya da kaynağı kanıtlanamayan kopyalar otomatik silinmez. Bu bir çökme
kurtarma düzenidir, harici yedekleme hizmeti değildir. Gerçek kullanıcı verileriyle hata ve kurtarma senaryoları son
olarak sınanmadan veri klasörlerini elle taşımayın veya silmeyin.

Şema v5'te olay bazlı geçmiş yoktu. v6 geçişi yalnızca o zamanki son kopyalama zamanında bir özet ve otomatik
yapıştırma toplamı varsa o zamanki son yapıştırma zamanında bir özet oluşturur; geçmiş bireysel zamanları, hedefleri,
yöntemleri veya sonuçları tahmin etmez. Şema v8, RTF'yi, kayıtlı görselleri, sanal dosyaları, kaynak
`CanUploadToCloudClipboard` durumunu, arama filtrelerini, OCR'yi, etiketleri, panoları ve yapıştırma kuyruklarını aynı
`memory_id` yaşam döngüsüne bağlar.

OCR, kurulu Windows OCR dil paketleriyle bilgisayarda yerel çalışır ve görselleri yüklemez. Sonuçlar hatalı olabilir,
kullanıcı tarafından silinebilir ve asıl belgenin resmî dökümü sayılmamalıdır.

Taşınabilir yedek, tutarlı SQLite anlık görüntüsündeki mantıksal kayıtları mevcut Windows kullanıcı bağlamında çözer
ve kullanıcının girdiği parolayla Argon2id ve XChaCha20-Poly1305 kullanarak hemen yeniden şifreler. Parola ve türetilen
anahtar saklanmaz veya sunucuya gönderilmez; işlem sonrası bellek makul ölçüde üzerine yazılır. PCSSAK unutulan parolayı
veya kayıp dosyayı kurtaramaz. Yedek dışa aktarma anındaki etkin/silinmiş kayıtları, hızlı metni, olayları, OCR ve
düzenlemeyi içerebilir; konumun, harici aygıtın veya eşitleme hizmetinin güvenlik ve saklama süresini kullanıcı yönetir.
İçe aktarma yalıtılmış bir adayı doğrular ve mevcut veritabanıyla birleştirmek yerine onu değiştirir. Eski bir yedeği
geri yüklemek, mevcut uygulamada silinmiş verileri yeniden ortaya çıkarabilir.

## 4. Saklama, silme ve geri yükleme süreleri

Kullanıcının belirlediği adet sınırı düzenlenmemiş olağan kayıtlara uygulanır. Sabitlenen veya OCR, etiket, pano ya da
yapıştırma kuyruğuna bağlı kayıtlar adet temizliğinden korunur; gerçek sayı daha yüksek olabilir. Korunan ve korunmayan
tüm veriler ayrıca 512 MB mantıksal depolama sınırına tabidir. Otomatik adet temizliği, elle silinen kayıt deposunu
atlayıp bağlantılı olayları da kaldırır.

Tek tek silme veya Geçmişi temizleme, kaydı ve bağlı olaylarını Windows Geri Dönüşüm Kutusu'na değil AroDamA'nın
yerel silinmiş kayıt yaşam döngüsüne taşır. Tarih aralığıyla silme, kaydın yerel kopyalama tarihine göre iki sınırı da
kapsar ve sabit kayıtları korur. Gelecek bir tarih zamanlanmış silme oluşturmaz.

- Silmeden sonra tam 24 saate kadar ücretsiz geri yükleme yapılabilir.
- 24 saatten sonra mevcut Free Early Access kaydı geri yükleyemez; buna karşın şifreli içerik ve olaylar, silinmeden
  itibaren aynı bilgisayardaki aynı Windows kullanıcısı altında en çok 30 gün kalabilir. Mevcut üründe bu veriyi açan
  Pro, ödeme, satış, uzaktan lisans etkinleştirme özelliği veya arayüz yoktur.
- Silinmiş kayıtlar ve olaylar, geçmiş, sabit öğeler ve hızlı metinlerle aynı 512 MB mantıksal sınıra dahildir.
- Kullanıcı daha önce kalıcı silebilir. Tam 30 güne ulaşan veri bir sonraki temizlemede uygulama veritabanından çıkarılır
  ve uygulamada geri yüklenemez.

Sürenin dolması veya kalıcı silme, içerik ve bağlantılı olayları geçerli veritabanından uygulama düzeyinde kaldırır;
fiziksel ortamın güvenli silinmesi değildir. SQLite boş sayfaları veya WAL, saklanan geçiş kurtarma dosyaları, Windows
veya kuruluş yedekleri, disk kurtarma alanları ya da üçüncü taraf eşitlenmiş kopyalarda izler kalabilir. Kaydedilmiş hedef
uygulama adının silinmesi de yalnızca geçerli veritabanındaki şifreli metni kaldırır, ayrı kopyaların üzerine yazmaz.

24 saatlik geri yükleme, 30 günlük sona erme ve olay zamanları yerel Windows sistem saatini kullanır. Büyük saat
değişiklikleri görüntüleme, geri yükleme ve sona ermeyi etkileyebilir. Zaman çizelgesi güvenilir saat kaynağıyla
imzalanmış, kurcalamaya dayanıklı bir denetim günlüğü veya hukuki delil değildir. Silinmiş kayıt deposu ile taşınabilir
yedekler ayrıdır; AroDamA kayıp veritabanını, yedek dosyasını veya parolayı kurtaramaz.

Normal kaldırma, `%LOCALAPPDATA%\PCssak\AroDamA` içindeki geçmişi ve ayarları korur. Yalnızca kullanıcı
kaldırıcıda `Uygulama verilerini sil` seçeneğini açıkça seçerse AroDamA'nın yönettiği ayarlar, veritabanı,
koruma anahtarları, geçiş kurtarma anlık görüntüleri ve doğrulanmış geri yükleme adayları kesin bir izin listesine
göre silinir. Bu durumda bile paylaşılan `PCssak\AroDamA` kökü yinelemeli olarak silinmez; kullanıcının dışa
aktardığı `.arodama-backup` dosyaları, başka bir konumdaki yedek veya geri alma kopyaları, eşitlenmiş kopyalar ve
bir kuruluşun saklama kopyaları silinmez. İstenirse bu kopyalar ayrıca incelenip silinmelidir.

## 5. Hassas veriyi en aza indirme ve kullanıcı denetimleri

AroDamA, `Clipboard Viewer Ignore`, `ExcludeClipboardContentFromMonitorProcessing` ve
`CanIncludeInClipboardHistory=0` gibi tanınan Windows pano hariç tutma işaretlerine uyar. Her parola yöneticisi veya
iş uygulaması bu işaretleri yayımlamaz; hassas verinin hiç yakalanmayacağı garanti edilemez.

Windows kayıtlı biçimi `CanUploadToCloudClipboard` için üç durum korunur: yok, DWORD 1 (izin verildi) ve DWORD 0
(engellendi). Saklanan öğe yeniden yayımlanırken kaynak uygulamanın buluta yüklememe isteğini ortadan kaldırmamak için
önce özgün durum yayımlanır. AroDamA içeriği yüklemez ve Windows'un ya da diğer uygulamaların eşitleme ayarlarını
değiştirmez. Olağan dışı uzunluk veya 0 ve 1 dışındaki değer izin sayılmaz; yakalama reddedilir.

Varsayılan parola yöneticisi koruması, Windows çalıştırılabilir dosyasının temel adı tam olarak `1password.exe`,
`bitwarden.exe`, `keepass.exe` veya `keepassxc.exe` olduğunda yeni içeriği okumadan atlayan kolaylık filtresidir.
Her sürüm, uzantı, aracı işlem veya yükseltilmiş uygulama için tam güvenlik sınırı değildir. Hassas metin filtresi de
dar yerel kurallar kullanır ve özgün metni ya da engellenen karmaları günlüğe, veritabanına veya ağa göndermez. İki
denetim de eski kayıtları silmez.

Kullanıcı yakalamayı duraklatabilir, uygulamaları hariç tutabilir, görsel/dosya yakalamayı kapatabilir, hedef uygulama
hafızasını kapalı tutabilir, kayıtlı hedef adlarını ve geçmişi silebilir, silinen kayıt deposunu boşaltabilir, sınırları
düşürebilir ve yerel verileri kaldırabilir. Parola, tek kullanımlık kod veya kişisel veri kullanırken yakalamayı
duraklatın; listede olmayan güvenlik uygulamalarını hariç tutun; ortak bilgisayarlarda ayrı Windows hesabı kullanıp
ekranı kilitleyin; geçmişi düzenli inceleyip silin.

## 6. Ağ erişimi ve üçüncü taraf işlemesi

AroDamA pano içeriğini, yerel dosya adlarını/yollarını, hızlı metni, OCR görsellerini/sonuçlarını, hafıza zaman
çizelgesini veya taşınabilir yedekleri PCSSAK'a ya da güncelleme sunucusuna yüklemez. İlk çalıştırma onayından sonra
aşağıdaki resmî GitHub Release meta verisini HTTPS ile denetleyebilir:

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

Uygulama kendi sürümünü yanıttaki sürüm, sürüm notları, indirme URL'si ve bütünlük imzasıyla karşılaştırır. Yükleyici
yalnızca kullanıcı sunulan güncellemeyi kurmayı açıkça seçerse indirilir. GitHub, IP adresi, erişim zamanı ve kullanıcı
aracısı gibi standart istek verilerini kendi gizlilik koşullarına göre işleyebilir. AroDamA isteğe pano içeriği veya
kullanım geçmişi eklemez; GitHub'ın işleme yeri ve saklama süresini kendi politikası belirler.

Microsoft Edge WebView2 Runtime yoksa Tauri NSIS kurulumu Microsoft'tan WebView2 bootstrapper indirebilir. Bu,
AroDamA pano verisi aktarımı değildir ve Microsoft politikası geçerlidir. Kullanıcı şifreli yedeği OneDrive veya başka
bir üçüncü taraf eşitleme uygulamasının yönettiği klasöre kaydederse bu uygulama dosyayı kendi ayar ve gizlilik politikasına
göre yükleyebilir.

Gelecekte hesap, ödeme, uzaktan destek, analitik veya çökme raporu etkinleştirilmeden önce bu bildirim gerçekten iletilen
veri, amaç, saklama, sağlayıcılar ve olası uluslararası aktarım ile güncellenecek ve yürürlükteki hukukun gerektirdiği
onay alınacaktır.

## 7. Kullanıcı hakları, iletişim ve bildirim değişiklikleri

PCSSAK hesabı veya merkezi pano veritabanı olmadığından PCSSAK, kullanıcı adına yerel içeriği uzaktan alamaz, dışa
aktaramaz, düzeltemez veya silemez. Kullanıcı yerel veriyi Bölüm 5'teki özellikler ve resmî silme yönergesiyle yönetir.

Gizlilik iletişimi: `privacy@pcssak.com`

Genel destek: `support@pcssak.com`

Güvenlik açığı ayrıntılarını, pano içeriğini, veritabanını, kimlik bilgilerini veya kişiyi belirleyen günlükleri herkese
açık bir Issue'da yayımlamayın. Resmî genel sürüm deposundaki GitHub özel güvenlik açığı bildirimini kullanın.

PCSSAK, ürün ve web sitesindeki mevcut görünen işletmeci adıdır; bu ifade tek başına herhangi bir ülkede tüzel kişi
veya tescilli ticaret unvanı bulunduğunu ileri sürmez. Tescilli satıcı açıklaması veya ayrı satış koşulları gerektiren
ücretli satışlar, bu bilgiler ve koşullar belirlenip yayımlandıktan sonra başlayacaktır.

Bu bildirim değiştiğinde tarih ve sürüm güncellenir. Veri işlemenin önemli ölçüde genişlemesi yürürlüğe girmeden önce
kullanıcı bilgilendirilir ve gerektiğinde yeniden onayı alınır.

---

# Avis de confidentialité de PCSSAK AroDamA Free Early Access

- Version du document : 1.0
- Dernière mise à jour : 2026-09-01
- Produit concerné : PCSSAK AroDamA Free Early Access for Windows
- Nom d'opérateur affiché : PCSSAK
- Questions relatives à la confidentialité : `privacy@pcssak.com`
- Assistance générale : `support@pcssak.com`

> Ce texte français est une traduction informative du texte coréen faisant foi. En cas de divergence,
> le texte coréen ne prévaut que dans la mesure autorisée par le droit applicable. Les règles impératives
> de protection des données et des consommateurs ainsi que les autres droits auxquels l'utilisateur ne
> peut renoncer dans son lieu de résidence prévalent. Ce document est un projet opérationnel prudent qui
> n'a pas encore fait l'objet d'un examen juridique professionnel dans chaque pays et ne constitue pas un avis juridique.

## 1. Principes de traitement et consentement au premier démarrage

PCSSAK AroDamA est une application Windows privilégiant le traitement local. La version Free Early Access
actuelle ne comporte aucun compte, publicité, mesure d'utilisation, synchronisation dans le cloud, envoi à
distance de rapports de plantage, paiement ou validation distante de licence. L'historique du presse-papiers
et les réglages sont gérés sur le PC de l'utilisateur. Les accès réseau limités nécessaires à la recherche de
mises à jour, aux téléchargements approuvés par l'utilisateur et à la préparation de WebView2 sont décrits à la section 6.

Au premier démarrage, la capture du presse-papiers et la recherche automatique de mises à jour restent suspendues
jusqu'à ce que l'utilisateur puisse ouvrir et consulter l'EULA et le présent avis dans l'application, cocher la case
de confirmation des documents et appuyer explicitement sur le bouton de démarrage. La fin de cette étape et la reprise
de la capture sont enregistrées ensemble. Les réglages locaux conservent les versions acceptées de l'EULA et de l'avis,
l'empreinte du jeu de documents et l'heure locale d'acceptation ; aucun enregistrement d'acceptation n'est envoyé à un
compte ou à un serveur. Une modification importante de la licence ou du traitement entraîne une nouvelle version des
documents et suspend la capture jusqu'à un nouvel examen. Le programme d'installation affiche le même EULA.

## 2. Données traitées lors de l'utilisation des fonctions

| Catégorie | Exemples | Finalité |
|---|---|---|
| Contenu du presse-papiers | Texte, mise en forme HTML/RTF, images, listes de chemins de fichiers physiques, noms et octets de fichiers virtuels fournis en mémoire | Historique, recherche, aperçu et réutilisation |
| Source et destination | Nom du processus propriétaire du presse-papiers et, uniquement après activation, nom de l'exécutable cible du collage automatique | Recherche, affichage de la source, exclusions et chronologie datée |
| Textes rapides | Nom et contenu créés par l'utilisateur | Réutilisation de textes fréquents |
| Organisation de la mémoire | Texte OCR demandé, étiquettes, noms et appartenances de tableaux, miniatures et ordre de la file de collage | Recherche de texte d'image, classement et réutilisation ordonnée |
| Sauvegarde portable | Fichier chiffré pouvant contenir, à l'exportation, des éléments actifs et supprimés, textes rapides, événements, OCR et données d'organisation | Restauration ou transfert vers un autre PC |
| Réglages | Raccourcis, thème, langue, limites, applications exclues, pause, capture d'images/fichiers et fin de l'information initiale | Conserver les préférences |
| Métadonnées opérationnelles | Identifiants d'élément/événement, type, heures de début/fin, résultat, nombre, provenance, méthode de collage, taille, épinglage et valeur de doublon | Tri, chronologie, intégrité, conservation et dédoublonnage |

La variable `{clipboard}` d'un texte rapide ne lit le texte Windows actuel que lors de l'aperçu ou de l'utilisation.
Cette lecture explicite ne crée pas à elle seule une nouvelle entrée d'historique et est refusée au-delà de la limite configurée.

La mémorisation de l'application cible du collage automatique est désactivée par défaut. Si elle est activée, seul le
nom de base de l'exécutable (par exemple `notepad.exe`) est conservé, et non le titre du document ou de la fenêtre, le
chemin complet, le PID ou le HWND. La désactivation ne concerne que les événements futurs. Une commande distincte avec
confirmation en deux étapes supprime définitivement de la base actuelle uniquement les anciens noms de cible, tout en
conservant date, type, résultat et nombre de l'événement ; le nom supprimé n'est pas récupérable dans l'application.
Les noms des applications sources ne sont pas supprimés. Pour ne pas conserver une source, ajoutez l'application aux
exclusions ou suspendez la capture. Les exclusions et la protection par défaut activée des gestionnaires de mots de
passe s'appliquent aussi aux futurs noms de cible ; un changement de réglage n'examine ni ne supprime rétroactivement
les données déjà enregistrées.

Le bloqueur facultatif de texte potentiellement sensible est désactivé par défaut. S'il est activé, des règles locales
limitées écartent avant enregistrement les blocs de clé privée reconnaissables, certains formats identifiables de jetons
d'accès et les formats courants de cartes qui réussissent le contrôle de Luhn. Des faux positifs et négatifs sont possibles,
et les anciennes entrées ne sont ni analysées ni supprimées. Des mots de passe, codes à usage unique et données d'identité,
financières, médicales ou professionnelles confidentielles peuvent donc toujours être capturés.

## 3. Stockage, chiffrement et protection de la récupération

Les nouvelles données sont stockées sous `%LOCALAPPDATA%\PCssak\AroDamA`. Uniquement si cet emplacement est vide,
l'application peut copier l'ancienne base et les réglages de `%APPDATA%\ClipDeck`, sans supprimer les anciens fichiers.

- Le contenu, les aperçus, HTML, RTF, images, listes de fichiers physiques/virtuels, corps des textes rapides, OCR,
  noms d'étiquettes/tableaux et miniatures des éléments actifs et supprimés sont protégés par Windows DPAPI dans
  le périmètre de l'utilisateur courant et ne sont en principe déchiffrables que dans le même contexte Windows.
- Pour la recherche, l'aperçu, le collage et l'exportation, certaines données doivent être déchiffrées en mémoire.
  Les tampons maîtrisés par l'application sont écrasés après usage dans la mesure raisonnablement possible.
- Les valeurs de dédoublonnage utilisent HMAC-SHA-256 avec un secret propre à l'installation. La clé est protégée
  par DPAPI dans `dedup-key.bin` ; HMAC ne remplace pas le chiffrement du contenu.
- Les filtres de candidats de recherche intégrale utilisent une autre clé HMAC propre à l'installation et protégée
  par DPAPI. Ils ne stockent aucun mot ni corps en clair, mais ne constituent pas une recherche entièrement chiffrée
  masquant tous les schémas de longueur ou d'accès. La correspondance réelle est vérifiée en déchiffrant séparément
  chaque candidat en mémoire.
- Certaines métadonnées opérationnelles peuvent rester en clair : application source de l'élément actuel, réglages
  et structure de la base, nom du texte rapide, identifiants, types, heures, résultats, nombres, provenance, méthode
  de collage, durée de conservation, taille, épinglage et liens d'organisation. Les noms d'exécutables source ou
  cible facultative contenus dans les événements sont protégés par DPAPI.
- DPAPI ne protège pas contre un logiciel malveillant s'exécutant sous le même utilisateur Windows déverrouillé,
  la capture d'écran ou de clavier, une attaque de la mémoire, un contrôle à distance autorisé par l'utilisateur
  ou l'accès physique à un PC déverrouillé.

Avant migration, l'intégrité SQLite est contrôlée. Une transition nécessaire de schéma ou de HMAC crée une copie de
récupération cohérente, liée sans ambiguïté par un marqueur aléatoire dans la base et le SHA-256 de l'instantané. Une
transition interrompue reprend au démarrage suivant. Une copie liée n'est supprimée qu'après vérification de la base
actuelle, du schéma, des tables et colonnes requises, du marqueur de clé et de l'état WAL ; une copie non liée ou dont
l'origine n'est pas prouvée n'est pas supprimée automatiquement. Il s'agit d'une récupération après incident, pas
d'un service de sauvegarde externe. Ne déplacez ni ne supprimez manuellement les dossiers de données avant les essais
finaux avec de vraies données et des scénarios d'échec et de récupération.

Le schéma v5 ne comportait pas d'historique par événement. La migration v6 crée seulement un résumé à la dernière heure
de copie alors connue et, s'il existe un cumul de collages automatiques, un résumé à sa dernière heure de collage ; elle
n'invente pas les heures, cibles, méthodes ou résultats individuels passés. Le schéma v8 relie RTF, images enregistrées,
fichiers virtuels, état source de `CanUploadToCloudClipboard`, filtres de recherche, OCR, étiquettes, tableaux et files
de collage au même cycle de vie `memory_id`.

L'OCR fonctionne localement avec les modules linguistiques OCR de Windows installés et ne téléverse pas les images.
Ses résultats peuvent être inexacts, sont supprimables et ne constituent pas une transcription officielle de l'original.

Une sauvegarde portable déchiffre les enregistrements logiques d'un instantané SQLite cohérent dans le contexte de
l'utilisateur Windows actuel, puis les rechiffre immédiatement avec le mot de passe saisi, au moyen d'Argon2id et de
XChaCha20-Poly1305. Le mot de passe et la clé dérivée ne sont ni stockés ni envoyés ; la mémoire est écrasée après
l'opération dans la mesure raisonnablement possible. PCSSAK ne peut récupérer ni mot de passe oublié ni fichier perdu.
La sauvegarde peut contenir les éléments actifs et supprimés, textes rapides, événements, OCR et organisation à la date
de l'exportation ; l'utilisateur gère la sécurité et la conservation de l'emplacement, du support externe ou du service
de synchronisation. L'importation vérifie un candidat isolé et remplace la base actuelle au lieu de la fusionner. Une
ancienne sauvegarde peut réintroduire des données déjà supprimées de l'application actuelle.

## 4. Durées de conservation, suppression et restauration

La limite de nombre choisie s'applique aux éléments ordinaires non organisés. Les éléments épinglés ou liés à l'OCR,
à une étiquette, un tableau ou une file de collage sont protégés contre le nettoyage par nombre ; le nombre réel peut
donc être supérieur. Toutes les données, protégées ou non, sont également soumises à une limite logique distincte de
512 MB. Le nettoyage automatique par nombre contourne le dépôt manuel des éléments supprimés et retire les événements liés.

Une suppression individuelle ou « Effacer l'historique » déplace l'élément et ses événements dans le cycle local des
éléments supprimés d'AroDamA, et non dans la Corbeille Windows. La suppression par plage inclut les deux dates selon la
date locale de copie et protège les éléments épinglés. Une date future ne planifie aucune suppression.

- La restauration gratuite est possible jusqu'à exactement 24 heures après la suppression.
- Après 24 heures, la version Free Early Access actuelle ne peut plus restaurer l'élément, même si le contenu et les
  événements chiffrés peuvent rester sur le même PC, sous le même utilisateur Windows, pendant au plus 30 jours à
  compter de la suppression. Le produit actuel ne comporte aucune fonction ni interface Pro, de paiement, de vente
  ou d'activation distante de licence permettant de les déverrouiller.
- Les éléments supprimés et les événements sont comptés dans la même limite logique de 512 MB que l'historique,
  les éléments épinglés et les textes rapides.
- L'utilisateur peut les supprimer définitivement plus tôt. Les données atteignant exactement 30 jours sont retirées
  de la base de l'application lors du nettoyage suivant et ne sont plus restaurables par l'application.

L'expiration ou la suppression définitive retire le contenu et les événements liés de la base actuelle au niveau de
l'application ; il ne s'agit pas d'un effacement sécurisé du support physique. Des traces peuvent subsister dans les
pages libres ou le WAL de SQLite, des fichiers de récupération de migration conservés, les sauvegardes Windows ou
d'entreprise, les zones de récupération du disque ou des copies synchronisées par des tiers. La suppression d'un nom
d'application cible retire également seulement le texte chiffré de la base actuelle sans écraser les copies séparées.

La limite de restauration de 24 heures, l'expiration à 30 jours et les heures des événements utilisent l'horloge locale
de Windows. Une modification importante de l'horloge peut affecter l'affichage, la restauration et l'expiration. La
chronologie n'est pas signée par une source horaire fiable et ne constitue ni un journal d'audit infalsifiable ni une
preuve juridique. Le dépôt des éléments supprimés et les sauvegardes portables sont distincts ; AroDamA ne peut récupérer
une base, un fichier de sauvegarde ou un mot de passe perdu.

Une désinstallation normale conserve l'historique et les paramètres dans
`%LOCALAPPDATA%\PCssak\AroDamA`. Ce n'est que si l'utilisateur sélectionne expressément
`Supprimer les données de l'application` dans le programme de désinstallation que les paramètres, la base de
données, les clés de protection, les instantanés de récupération de migration et les candidats de restauration
vérifiés gérés par AroDamA sont supprimés selon une liste d'autorisation précise. Même dans ce cas, la racine
partagée `PCssak\AroDamA` n'est pas supprimée récursivement. Les fichiers `.arodama-backup` exportés par
l'utilisateur, les sauvegardes ou copies de restauration situées ailleurs, les copies synchronisées et les
copies conservées par une organisation ne sont pas supprimés. Ces copies doivent être vérifiées et supprimées
séparément si nécessaire.

## 5. Réduction des données sensibles et contrôles de l'utilisateur

AroDamA respecte les exclusions reconnues du presse-papiers Windows, notamment `Clipboard Viewer Ignore`,
`ExcludeClipboardContentFromMonitorProcessing` et `CanIncludeInClipboardHistory=0`. Tous les gestionnaires de mots
de passe et logiciels professionnels ne publient pas ces indicateurs ; l'absence totale de capture de données sensibles
ne peut donc être garantie.

Les trois états du format Windows enregistré `CanUploadToCloudClipboard` sont préservés : absent, DWORD 1 (autorisé)
et DWORD 0 (interdit). Lors de la republication d'un élément, AroDamA republie d'abord l'état d'origine afin de ne pas
annuler le refus de téléversement cloud de l'application source. AroDamA ne téléverse pas le contenu et ne modifie pas
les réglages de synchronisation de Windows ou des autres applications. Une longueur anormale ou une valeur autre que
0 ou 1 n'est pas présumée autorisée ; la capture est refusée.

La protection par défaut des gestionnaires de mots de passe n'est qu'un filtre pratique qui ignore le nouveau contenu
avant lecture lorsque le nom de base de l'exécutable correspond exactement à `1password.exe`, `bitwarden.exe`,
`keepass.exe` ou `keepassxc.exe`. Ce n'est pas une frontière de sécurité complète couvrant toutes les versions,
extensions, processus intermédiaires ou applications élevées. Le filtre sensible utilise lui aussi des règles locales
limitées et n'envoie ni le texte source ni les condensats bloqués aux journaux, à la base ou au réseau. Aucun des deux
contrôles ne supprime les anciennes entrées.

L'utilisateur peut suspendre la capture, exclure des applications, désactiver la capture d'images/fichiers, laisser
désactivée la mémorisation de la cible, supprimer des noms cibles et des entrées, vider le dépôt des éléments supprimés,
réduire les limites et retirer les données locales. Lors du traitement de mots de passe, codes à usage unique ou données
personnelles, suspendez la capture ; excluez les logiciels de sécurité absents de la liste ; utilisez un compte Windows
distinct et verrouillez l'écran sur les PC partagés ; contrôlez et supprimez régulièrement l'historique.

## 6. Accès réseau et traitement par des tiers

AroDamA ne téléverse vers PCSSAK ou le serveur de mise à jour ni contenu du presse-papiers, ni noms ou chemins de fichiers
locaux, textes rapides, images ou résultats OCR, chronologies ou sauvegardes portables. Après le consentement initial,
l'application peut consulter par HTTPS les métadonnées officielles GitHub Release à l'adresse suivante :

`https://github.com/pcssakinc/pcssak-arodama-releases/releases/latest/download/latest.json`

L'application compare sa version à la version, aux notes de publication, à l'URL de téléchargement et à la signature
d'intégrité de la réponse. Elle ne télécharge le programme d'installation que si l'utilisateur choisit expressément
d'installer la mise à jour proposée. GitHub peut traiter les données standard de requête, telles que l'adresse IP,
l'heure d'accès et l'agent utilisateur, selon ses propres conditions de confidentialité. AroDamA n'ajoute ni contenu
du presse-papiers ni historique d'utilisation ; la politique de GitHub régit le lieu et la durée de son traitement.

Si Microsoft Edge WebView2 Runtime est absent, l'installation Tauri NSIS peut télécharger le programme d'amorçage
WebView2 auprès de Microsoft. Il ne s'agit pas d'un transfert de données de presse-papiers par AroDamA et la politique
de Microsoft s'applique. Si l'utilisateur place une sauvegarde chiffrée dans un dossier géré par OneDrive ou une autre
application de synchronisation tierce, celle-ci peut téléverser le fichier selon ses réglages et sa politique de confidentialité.

Avant l'activation future d'un compte, paiement, support à distance, outil d'analyse ou rapport de plantage, cet avis
sera mis à jour avec les données réellement transmises, leur finalité, leur conservation, les prestataires et tout
transfert international possible, et le consentement exigé par la loi applicable sera recueilli.

## 7. Droits de l'utilisateur, contact et modification de l'avis

En l'absence de compte PCSSAK et de base centrale de presse-papiers, PCSSAK ne peut pas récupérer, exporter, rectifier
ou supprimer à distance le contenu local pour le compte de l'utilisateur. L'utilisateur contrôle ses données locales
au moyen des fonctions de la section 5 et des instructions officielles de suppression.

Questions relatives à la confidentialité : `privacy@pcssak.com`

Assistance générale : `support@pcssak.com`

Ne publiez pas dans un ticket public des détails de vulnérabilité, le contenu du presse-papiers, une base de données,
des identifiants ou des journaux permettant une identification. Utilisez le signalement privé de vulnérabilités de
GitHub dans le dépôt public officiel des versions.

PCSSAK est actuellement le nom d'opérateur affiché pour le produit et le site ; ce seul nom ne prétend pas qu'une
société ou un nom commercial est enregistré dans un pays donné. Toute vente payante nécessitant l'identification d'un
vendeur enregistré ou des conditions de vente distinctes ne débutera qu'après leur définition et leur publication.

Lors d'une modification du présent avis, sa date et sa version seront mises à jour. L'utilisateur sera informé avant
l'entrée en vigueur de toute extension substantielle du traitement et un nouveau consentement sera demandé si nécessaire.
