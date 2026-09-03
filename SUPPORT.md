# PCSSAK AroDamA 지원 안내 / Support

- 적용 버전 / Applies to: `0.4.x Free Early Access`
- 일반 문의 / General support: `support@pcssak.com`
- 개인정보 문의 / Privacy: `privacy@pcssak.com`

이 파일은 현재 운영 안내입니다. 이미 공개한 릴리스에 첨부된 지원 문서는 해당 버전의 기록으로
보존하며 교체하지 않습니다. / This is living support guidance; version-pinned release attachments
retain their original bytes.

## 한국어

### 문의 경로

| 내용 | 공식 경로 |
| --- | --- |
| 질문·사용 후기·개선 아이디어 | [공개 토론](https://github.com/pcssakinc/pcssak-arodama-releases/discussions). 공지는 Announcements, 질문은 Q&A, 제안은 Ideas를 사용합니다. |
| 재현 가능한 오류 | [오류 양식](https://github.com/pcssakinc/pcssak-arodama-releases/issues/new?template=bug-report.yml). 합성 예시로 한 문제씩 제보합니다. |
| GitHub 이용이 어려운 일반 문의 | `support@pcssak.com`. 일반 이메일에도 실제 클립보드·DB·백업·비밀정보를 첨부하지 않습니다. |
| 개인정보 처리 문의 | `privacy@pcssak.com`. 확인에 필요한 최소 내용만 보냅니다. |
| 악용 가능한 취약점 | [GitHub 비공개 보안 신고](https://github.com/pcssakinc/pcssak-arodama-releases/security/advisories/new). 일반 이메일·공개 이슈·토론에 상세를 보내지 않습니다. |

의견 검토 상태와 기여·보상 경계는 [기여 원칙](CONTRIBUTING.md)을 따릅니다. 오류·기능 제안을
중복 게시하지 말고 관련 토론과 이슈를 서로 연결하십시오.

### 지원 범위

PCSSAK AroDamA 0.4.x는 무료 Early Access입니다. 기능 변경과 결함이 있을 수 있으며,
문의 응답이나 수정 완료 시한을 보장하지 않습니다. 현재 지원 후보는 다음과 같습니다.

- Windows 11 Home/Pro x64: 주 지원 후보
- Windows 10 22H2 Home/Pro x64: 제한적 호환 후보
- Windows 10 22H2 x86: 별도 x86 설치본을 사용하는 제한적 호환 후보
- Windows 11 x86, Windows on ARM, Windows S 모드, Windows Server, macOS, Linux, Wine: 미지원

Windows 10 호환 표기는 운영체제 자체의 보안 지원을 뜻하지 않습니다. 실제 지원 범위는
깨끗한 대상 장치에서 완료한 검증 결과보다 넓게 주장하지 않습니다.

### 일반 오류를 신고할 때

가능하면 다음 정보만 보내 주십시오.

- AroDamA 버전과 x64 또는 x86 구분
- Windows 버전·에디션과 화면 배율
- 문제가 발생한 기능과 재현 순서
- 표시된 오류 문구
- 민감정보를 제거한 화면 캡처

이메일이나 공개 게시물에 클립보드 본문, 데이터베이스, 백업 파일, 백업 암호, Windows 사용자
이름, 개인 경로, 개인정보, 인증정보 또는 업무 기밀을 첨부하지 마십시오.

### 보안 취약점

공개되기 전의 취약점 세부 내용은 일반 지원 이메일이나 공개 이슈에 보내지 마십시오. 공식
`pcssakinc/pcssak-arodama-releases` GitHub 저장소의 **비공개 보안 권고(Private security
advisory)** 기능을 사용하십시오. 2026-09-03 읽기 전용 API 확인에서 비공개 신고 기능은 활성화 상태였습니다. 경로가 보이지
않으면 일반 지원에는 접수 경로 문의만 보내고 취약점 세부사항은 보내지 마십시오. 자세한 범위와 처리 원칙은 `SECURITY.md`를 따릅니다.

## English

### Contact routes

| Topic | Official route |
| --- | --- |
| Questions, experiences, and ideas | [Discussions](https://github.com/pcssakinc/pcssak-arodama-releases/discussions): Announcements for notices, Q&A for questions, Ideas for proposals. |
| Reproducible defect | [Bug form](https://github.com/pcssakinc/pcssak-arodama-releases/issues/new?template=bug-report.yml), one problem with synthetic data. |
| General help without GitHub | `support@pcssak.com`; do not attach clipboard data, databases, backups, or secrets to ordinary email either. |
| Privacy processing inquiry | `privacy@pcssak.com`, with only the minimum necessary details. |
| Exploitable vulnerability | [Private security report](https://github.com/pcssakinc/pcssak-arodama-releases/security/advisories/new), not general email, public Issues, or Discussions. |

See [CONTRIBUTING.md](CONTRIBUTING.md) for feedback handling and contribution/compensation boundaries.
Link related discussions and issues instead of submitting the same defect or proposal repeatedly.

### Support scope

PCSSAK AroDamA 0.4.x is Free Early Access software. Features may change, defects may remain, and no
response or remediation deadline is promised. The current support candidates are:

- Windows 11 Home/Pro x64: primary candidate
- Windows 10 22H2 Home/Pro x64: limited compatibility candidate
- Windows 10 22H2 x86: limited compatibility candidate using the separate x86 installer
- Windows 11 x86, Windows on ARM, Windows S mode, Windows Server, macOS, Linux, and Wine: unsupported

Windows 10 compatibility does not extend Microsoft's operating-system security support. Public
support claims must not exceed the clean-device validation that has actually been completed.

### Reporting a general issue

When possible, provide only the AroDamA version and architecture, Windows version and edition,
display scale, affected function, reproduction steps, exact error text, and a screenshot with all
sensitive information removed.

Do not attach clipboard content, databases, backup files, backup passwords, Windows user names,
personal paths, personal data, credentials, or confidential work information to email or public posts.

### Security vulnerabilities

Do not send non-public vulnerability details through general support email or a public issue. Use the
**Private security advisory** feature in the official `pcssakinc/pcssak-arodama-releases` GitHub
repository. A read-only API check confirmed the feature enabled on 2026-09-03. If the route is
unavailable, ask general support only how to obtain the private route; do not include exploit details. See `SECURITY.md` for scope and handling expectations.
