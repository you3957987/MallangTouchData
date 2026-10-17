# MallangTouchData

말랑이 만지기 외부 운영 데이터입니다.

`mailbox/mailbox.json`은 우편함용 배포 데이터 예제이며 현재 게임 번들의 `Resource/Mailbox/mailbox.json`과 같은 샘플입니다. 우편 3개와 공지 13개를 포함합니다. 공지 중 10개는 스크롤 테스트용 무보상 예시입니다. 실제 서비스 전에 내용과 보상 ID를 확인하세요.

- `id`는 고유하고 재지급하지 않을 항목은 변경하지 않습니다.
- `type`은 `mail` 또는 `notice`입니다.
- `date`는 `YYYY-MM-DD`입니다.
- 우편의 `reward_type`은 `mallang_shards`, `reward_amount`는 양의 정수입니다.
- 공지는 `reward_type`이 빈 문자열이고 `reward_amount`가 0입니다.
- `claimed`·`read`·`visible`은 클라이언트의 기존 저장 파일에 ID별로 기록하며 운영 JSON에서 수령 여부를 제어하지 않습니다.

현재 게임은 번들 JSON을 읽습니다. 이후 HTTPRequest로 이 저장소의 JSON을 내려받아 `user://mailbox.json`에 저장한 뒤 `MailboxManager.load_catalog("user://mailbox.json")`를 호출하면 됩니다. 실제 원격 다운로드 및 GitHub 게시·푸시는 수행하지 않았습니다. 자세한 스키마·저장 정책은 MallangTouch의 `docs/MailboxSystem.md`를 참고하세요.
