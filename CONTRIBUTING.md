# Issue and Contribution Guidelines / 이슈·기여 원칙

This public release repository is for verified PCssak AroDamA release documentation, support
guidance, security reporting, and user feedback. Proprietary application source is maintained in a
separate private repository. Installers and generated release assets belong only to version-pinned
GitHub Releases; never add them to a Pull Request or repository commit.

이 공개 배포 저장소는 검증된 PCssak AroDamA 릴리스 문서, 지원 안내, 보안 신고와 사용자 의견을
위한 곳입니다. 자체 애플리케이션 소스는 별도 비공개 저장소에서 관리합니다. 설치본과 생성 릴리스
자산은 버전 고정 GitHub Release에만 두며 Pull Request나 저장소 커밋에 추가하지 않습니다.

## Responsible reports

- Search existing Issues before opening a new report and keep one problem per Issue.
- Use the structured bug or feature form and synthetic, non-sensitive examples.
- Do not attach clipboard text, images, file lists, HTML or RTF, OCR output, databases, backups,
  backup passwords, diagnostic archives, personal paths, usernames, credentials, customer data,
  confidential work, private keys, tokens, or complete raw logs.
- Do not upload third-party files, source, screenshots, or binaries unless you have permission to
  share them and have removed all sensitive information.
- Do not publish exploitable vulnerability details. Follow [SECURITY.md](SECURITY.md) and use
  GitHub Private Vulnerability Reporting.
- Do not ask users to disable SmartScreen, antivirus, Windows security, a firewall, or organization
  policy as a troubleshooting step.

## Documentation contributions

Small corrections to release documentation, safe reproduction instructions, accessibility wording,
and user-facing translations can be proposed through an Issue. Open a Pull Request only after
PCSSAK requests or agrees to the contribution.

Do not replace the Korean authoritative EULA or Privacy Policy with an unreviewed translation. Do
not describe a translation, license interpretation, compatibility result, or security test as
professionally certified unless that evidence has actually been recorded for the exact release.

By submitting text you created, you confirm that you have the right to provide it and allow PCSSAK
to reproduce, edit, and distribute it as project documentation. Third-party materials remain under
their own rights and licenses. A contribution does not grant access to proprietary source code.

## Feedback handling and fair participation

Use [Discussions](https://github.com/pcssakinc/pcssak-arodama-releases/discussions) for questions,
experiences, and ideas, and structured Issues for reproducible defects. A useful small report is
more helpful than many speculative or AI-generated reports. Verify any AI-assisted submission
personally and state the environment and what you actually observed.

PCSSAK distinguishes received, needs information, under review, planned, released, and
on hold/not adopted. A status can be a short maintainer reply; these are not promised labels or
response deadlines. Where practicable, explain the decision and connect an accepted change to the
relevant release. Critical feedback is welcome; moderation concerns spam, abuse, privacy exposure,
and unsafe or unrelated content, not simply a negative opinion.

The text-contribution permission above remains unchanged and can cover documentation used with
commercial versions. Feedback does not by itself promise product ownership, payment, revenue
sharing, employment, source access, or implementation. Paid work, rewards, or revenue sharing need
separate explicit written terms before work begins. External code requires separate prior agreement
on scope, provenance, rights, tests, and any compensation; do not paste it into a public report.
Only credit contributors with their consent and chosen display name; do not publish private identity.

## 한국어

- 새 Issue를 만들기 전에 기존 내용을 검색하고 Issue 하나에는 문제 하나만 적습니다.
- 구조화된 버그·기능 제안 양식을 사용하고 합성된 비민감 예시만 사용합니다.
- 클립보드 글·이미지·파일 목록·HTML·RTF·OCR 결과·DB·백업·백업 암호·진단 압축·개인 경로·
  사용자명·자격증명·고객 자료·업무 기밀·개인키·토큰·원본 전체 로그를 첨부하지 않습니다.
- 공유 권한이 없는 제3자 파일·소스·화면·바이너리를 올리지 않으며, 허용된 자료도 민감정보를
  모두 제거합니다.
- 악용 가능한 취약점 세부 정보는 공개하지 않고 [SECURITY.md](SECURITY.md)에 따라 GitHub
  비공개 보안 신고를 사용합니다.
- 문제 해결을 이유로 SmartScreen·백신·Windows 보안·방화벽·조직 정책을 끄라고 안내하지 않습니다.

릴리스 문서의 작은 오류, 안전한 재현 안내, 접근성 문구와 사용자용 번역은 Issue로 제안할 수
있습니다. Pull Request는 PCSSAK이 요청하거나 사전에 동의한 경우에만 만드십시오.

국문 정본 EULA·개인정보 처리방침을 검토되지 않은 번역으로 바꾸거나 번역·라이선스 해석·호환성·
보안 시험을 실제 근거 없이 전문 인증된 결과로 표시하면 안 됩니다.

직접 작성한 텍스트를 제출하면 해당 내용을 제공할 권한이 있고 PCSSAK이 프로젝트 문서로 복제·
편집·배포할 수 있도록 허용한다는 뜻입니다. 제3자 자료는 각 권리와 라이선스를 따르며, 기여로
비공개 소스 접근 권한이 생기지 않습니다.

### 의견 처리와 공정한 참여

질문·사용 후기·아이디어는 [공개 토론](https://github.com/pcssakinc/pcssak-arodama-releases/discussions),
재현 가능한 오류는 구조화된 이슈를 사용합니다. 추측이나 AI 생성 제보를 대량으로 보내기보다
직접 확인한 소량의 구체적 제보를 부탁드립니다. AI 보조 자료도 사람이 환경과 관찰 결과를
확인해 작성하십시오.

접수·추가 정보 필요·검토 중·계획됨·반영됨·보류 또는 채택하지 않음을 구분합니다. 상태는 운영자의
짧은 답변으로도 표시할 수 있으며 특정 라벨 개설이나 응답 시한 약속이 아닙니다. 가능한 범위에서
결정 이유를 설명하고 반영한 변경을 릴리스에 연결합니다. 비판적인 의견도 환영하며, 단순히
부정적이라는 이유가 아니라 도배·괴롭힘·개인정보 노출·위험하거나 무관한 내용을 기준으로
관리합니다.

위 문서 기여 이용 허락은 그대로이며 유료 버전과 함께 제공되는 문서에도 사용될 수 있습니다.
의견 제출 자체가 제품 소유권·보수·수익 배분·고용·소스 접근·구현을 약속하지는 않습니다.
유료 협력·포상·수익 배분은 착수 전에 명시적인 별도 서면 조건으로 합의합니다. 외부 코드는
범위·출처·권리·시험·보상 여부를 먼저 별도 합의하며 공개 제보에 붙여 넣지 마십시오.
공개 감사 표시는 당사자의 동의를 받아 원하는 표시명만 사용하고 비공개 신원을 공개하지 않습니다.
