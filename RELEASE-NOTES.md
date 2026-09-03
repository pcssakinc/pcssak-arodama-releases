# PCSSAK AroDamA 0.4.1 Free Early Access

- Release channel: Free Early Access
- Release type: localization and update reliability patch
- Architectures: Windows x64 and x86
- Paid features: not included or visible
- Windows Authenticode: not signed
- Tauri updater integrity signature: included with each update installer

## 한국어

AroDamA 0.4.1은 0.4.0의 로컬 클립보드 기록·검색·정리·복구 기능을 유지하면서,
설치 단계에서 사용자가 선택한 언어가 첫 실행까지 정확히 이어지도록 고친 패치입니다.
기존 사용자가 앱에서 저장한 언어와 로컬 기록·설정은 업데이트가 덮어쓰지 않습니다.

### 변경 사항

- 신규 설치에서 NSIS 설치 언어를 첫 앱 언어로 한 번만 안전하게 저장
- 영어·한국어·일본어·독일어·스페인어·브라질 포르투갈어·튀르키예어·프랑스어별
  설치 EULA와 앱 내 EULA·개인정보 안내 제공
- 지원하지 않는 설치 언어는 Windows 선호 언어를 확인한 뒤 영어로 안전하게 대체
- 기존 사용자 언어, 날짜·숫자 지역 형식, 클립보드 DB와 개인정보 보호 설정 보존
- 자동 업데이트와 기존 버전 제거 중 저장 언어가 없거나 손상돼도 언어 선택창을 띄우지 않고
  지원 언어·Windows UI 언어·영어 순서로 안전하게 계속 진행
- 일반 제거에서는 기록과 설정을 보존하고, 사용자가 `앱 데이터 삭제`를 명시적으로 선택한
  경우에만 AroDamA 관리 데이터의 정확한 허용목록을 삭제하며 내보낸 백업은 보존
- 손상됐거나 더 새 버전에서 만든 설정 원본을 일반 저장으로 덮어쓰지 않고, 명시적 복구 때
  같은 폴더에 원본 백업을 남긴 뒤 캡처가 중지된 안전 설정을 게시
- 0.4.0과 같은 Tauri 업데이트 공개키를 사용해 앱 안에서 0.4.1 확인·다운로드·설치 가능
- 다국어 EULA 생성, 언어 연결, 조항·연락처 누락과 설치기 템플릿 드리프트 자동 검증

### 설치 전 확인

현재 설치 파일은 Windows Authenticode 미서명입니다. Windows가 `알 수 없는 게시자` 또는
SmartScreen 경고를 표시할 수 있습니다. 공식 PCSSAK 페이지의 고정 `v0.4.1` URL과
SHA-256을 확인하십시오. Tauri `.sig`는 앱 내부 업데이트 파일의 무결성을 검증하지만
Windows 게시자 신원을 증명하지 않습니다.

현지어 EULA는 사용 편의를 위한 참고 번역입니다. 적용 법률이 허용하는 범위에서 한국어
기준문이 우선하며, 사용자의 거주지에서 강제되는 소비자·개인정보 권리는 영향을 받지
않습니다. 원어민 및 관할별 법률 검토는 Early Access의 별도 검토 항목입니다.

지원: `support@pcssak.com`
개인정보: `privacy@pcssak.com`

## English

AroDamA 0.4.1 keeps the local clipboard history, search, organization, and restore features from
0.4.0 while fixing the language handoff from the installer to first launch. An update does not
overwrite an existing user's saved app language, local records, or settings.

### Changes

- Applies the explicitly selected NSIS installer language once on a new installation.
- Provides installer EULAs and in-app EULAs and privacy notices in English, Korean, Japanese,
  German, Spanish, Brazilian Portuguese, Turkish, and French.
- Falls back through Windows language preferences and then English for unsupported languages.
- Preserves the user's app language, regional date and number formatting, clipboard database,
  and privacy controls during update.
- Keeps passive update and previous-version removal non-interactive even when the saved language
  is absent or damaged, using the supported language set, Windows UI language, and English fallback.
- Preserves history and settings during a normal uninstall. The exact AroDamA-managed-data allowlist
  is removed only when the user explicitly selects `Delete app data`; exported backups stay untouched.
- Refuses to overwrite a damaged or newer-schema settings file through ordinary saves. Explicit
  recovery first keeps an original backup in the same folder and publishes capture-paused safe settings.
- Uses the same Tauri updater public key as 0.4.0 for in-app check, download, install, and restart.
- Adds deterministic validation for localized EULAs, legal sections, contacts, language mapping,
  and the pinned installer template.

### Before installation

The installers are not signed with Windows Authenticode. Windows may show Unknown Publisher or
SmartScreen warnings. Verify the fixed official `v0.4.1` URL and SHA-256. A Tauri `.sig`
protects in-app update integrity but does not authenticate the Windows publisher.

Localized EULAs are reference translations for convenience. The Korean controlling text prevails
to the extent permitted by applicable law, without limiting mandatory consumer or privacy rights
in the user's location. Native-language and jurisdiction-specific legal review remains a separate
Early Access review item.

Support: `support@pcssak.com`
Privacy: `privacy@pcssak.com`
