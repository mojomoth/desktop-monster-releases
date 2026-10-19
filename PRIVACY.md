# DesMon Privacy Notice / 개인정보 처리 안내

Last updated / 최종 수정: 2026-10-15 · Applies to DesMon v1.0.0 and later / DesMon v1.0.0 이후 버전에 적용

[English](#english) · [한국어](#한국어)

---

## English

DesMon is a desktop companion game. This notice explains what the game sends, why, where it goes,
and how to turn it off. The game plays fully offline and never needs analytics to work.

### 1. Anonymous usage statistics (analytics)

**What we collect.** A fixed list of game events, each with a small fixed set of values:

| Event | Extra values |
|---|---|
| `install` (first launch with statistics on) | whether a save already existed |
| `app_open`, `daily_active` (at most once per UTC day) | — |
| `session_end` | minutes with any input in the session |
| `level_reached`, `stage_reached`, `companion_tamed` | the milestone reached (for example level 10) |
| `first_boss`, `raid_joined`, `steam_item_sealed`, `steam_item_unsealed` | — |
| `rebirth` | kind (soul / hero) and count |
| `item_equipped` | rarity and slot (weapon / accessory) |
| `achievement_unlocked` | the achievement id (for example `ACH_FIRST_BOSS`) |
| `raid_cleared`, `pvp_battle` | MVP yes/no, win yes/no |
| `menu_opened`, `settings_changed` | which panel / which setting (never its value) |
| `analytics_opt_out` | — (see section 3) |

Every event also carries: game version, operating system and CPU type, distribution channel
(Steam / GitHub), whether Steam is running, interface language, a random session id, and a
**random install id** created on your computer the first time statistics are on.

**What we never collect.** Your Steam ID or Steam name, your in-game nickname or player id,
which keys you press or what you type, window or file names, or anything else you type. The
game only counts that input happened (for active minutes) and never records its content. The
list above is enforced in code: anything not on it is discarded before it leaves your computer.

**Why.** To understand, in aggregate, how many people play, whether they come back (day 1 / 7 /
30), where the game gets hard, which features are used, and which platforms to support.

**Where it goes.** Events are sent to [PostHog](https://posthog.com) Cloud (United States region),
which processes them on our behalf. Our PostHog project is set to discard IP addresses: the IP your
connection arrives from is used once to estimate an approximate location (country/city) and is not
stored. Unsent events wait in a small local file (`analytics-queue.json`, at most 1,000 events) and
are sent about once a minute while you are online.

**How long.** PostHog keeps events for up to 1 year on our current plan (up to 7 years if we move
to a paid plan). We do not combine this data with any other source and do not sell or share it.

### 2. Online features (separate from analytics)

If you use the leaderboard, PvP, raids or online trading, the game sends your chosen nickname and
game progress to the DesMon game server (hosted on Render) to provide those features. In online
mode a Steam session ticket verifies your Steam account to that server. This data is used only to
run those features; it is never sent to PostHog.

### 3. Turning statistics off, and deleting data

- **In the game:** Settings → turn off anonymous usage statistics. From that moment the game sends
  nothing more, deletes its unsent local queue, and replaces your install id with a new random one,
  so anything sent after you turn it back on cannot be linked to what came before.
- **When you turn it off,** the game makes one last request saying only "opted out" for the old id,
  and nothing else. If you are offline or it fails, the old id waits in `analytics.json`
  (`pendingOptOut`) and only that request is retried, also after a restart, until it arrives.
  We use it to delete that id's person record and all its events from PostHog; we run this
  deletion regularly.
- **Without starting the game:** set the environment variable `DESMON_ANALYTICS=0`.
- **Deletion on request:** email us with the `installId` from `analytics.json` in the game's data
  folder (macOS: `~/Library/Application Support/DesMon/`, Windows: `%APPDATA%\DesMon\`) and we will
  delete all data for that id.
- Development, test and unpackaged builds do not send statistics.

### 4. Contact

DesMon Developers — devvvick@gmail.com

---

## 한국어

DesMon은 데스크톱 컴패니언 게임입니다. 이 안내는 게임이 무엇을, 왜, 어디로 보내는지와 끄는 방법을 설명합니다.
게임은 완전히 오프라인으로도 플레이할 수 있으며, 통계 기능이 없어도 정상 동작합니다.

### 1. 익명 사용 통계

**수집 항목.** 정해진 게임 이벤트 목록과, 이벤트마다 정해진 소수의 값만 수집합니다.

| 이벤트 | 추가 값 |
|---|---|
| `install`(통계가 켜진 첫 실행) | 기존 세이브 존재 여부 |
| `app_open`, `daily_active`(UTC 기준 하루 최대 1회) | — |
| `session_end` | 세션 중 입력이 있었던 분(分) 수 |
| `level_reached`, `stage_reached`, `companion_tamed` | 도달한 마일스톤(예: 레벨 10) |
| `first_boss`, `raid_joined`, `steam_item_sealed`, `steam_item_unsealed` | — |
| `rebirth` | 종류(영혼 회귀/영웅 환생)와 횟수 |
| `item_equipped` | 등급과 칸(무기/장신구) |
| `achievement_unlocked` | 도전 과제 ID(예: `ACH_FIRST_BOSS`) |
| `raid_cleared`, `pvp_battle` | MVP 여부, 승리 여부 |
| `menu_opened`, `settings_changed` | 어떤 패널/어떤 설정인지(설정 값은 보내지 않음) |
| `analytics_opt_out` | — (3절 참고) |

모든 이벤트에는 게임 버전, 운영체제와 CPU 종류, 배포 채널(Steam/GitHub), Steam 실행 여부, 표시 언어,
무작위 세션 ID, 그리고 통계가 처음 켜질 때 내 컴퓨터에서 만들어지는 **무작위 설치 ID**가 함께 담깁니다.

**수집하지 않는 것.** Steam ID나 Steam 이름, 게임 닉네임이나 플레이어 ID, 어떤 키를 눌렀는지나 입력한 내용,
창·파일 이름 등 사용자가 입력하는 어떤 내용도 보내지 않습니다. 게임은 활동 시간 계산을 위해 입력이 "있었다"는
사실만 세고 그 내용은 기록하지 않습니다. 위 목록은 코드로 강제되며, 목록에 없는 값은 컴퓨터를 떠나기 전에 버려집니다.

**목적.** 전체 규모에서 얼마나 많은 사람이 플레이하는지, 다시 돌아오는지(1/7/30일), 어디서 어려워하는지,
어떤 기능이 쓰이는지, 어떤 플랫폼을 지원할지 파악하기 위해서입니다.

**전송 위치.** 이벤트는 [PostHog](https://posthog.com) Cloud(미국 리전)로 전송되며, PostHog가 저희를 대신해
처리합니다. 저희 PostHog 프로젝트는 IP 주소를 저장하지 않도록 설정되어 있어, 접속 IP는 대략적인 위치(국가/도시)를
추정하는 데 한 번만 쓰이고 저장되지 않습니다. 아직 보내지 못한 이벤트는 작은 로컬 파일(`analytics-queue.json`,
최대 1,000개)에 보관되었다가 온라인일 때 약 1분마다 전송됩니다.

**보관 기간.** 현재 요금제에서 PostHog는 이벤트를 최대 1년 보관합니다(유료 요금제로 바뀌면 최대 7년).
이 데이터를 다른 정보와 결합하지 않으며, 판매하거나 공유하지 않습니다.

### 2. 온라인 기능(통계와 별개)

순위표, 대전(PvP), 레이드, 온라인 거래를 사용하면 해당 기능 제공을 위해 직접 정한 닉네임과 게임 진행 정보가
DesMon 게임 서버(Render 호스팅)로 전송됩니다. 온라인 모드에서는 Steam 세션 티켓으로 해당 서버에 Steam 계정을
확인합니다. 이 데이터는 해당 기능 운영에만 쓰이며 PostHog로 전송되지 않습니다.

### 3. 통계 끄기와 데이터 삭제

- **게임 안에서:** 설정 → 익명 사용 통계 끄기. 그 즉시 더 이상 아무것도 보내지 않고, 보내지 못한 로컬 대기열을 삭제하며,
  설치 ID를 새 무작위 ID로 바꿉니다. 나중에 다시 켜더라도 이전 데이터와 연결되지 않습니다.
- **끄는 순간** 게임은 이전 ID로 "통계 끔"만 담은 마지막 요청을 보내고, 그 밖에는 아무것도 보내지 않습니다. 오프라인이거나
  전송에 실패하면 이전 ID를 `analytics.json`(`pendingOptOut`)에 남겨 두고, 도착할 때까지(재시작 후에도) 이 요청만 다시 보냅니다. 저희는 이를 근거로 해당 ID의 사용자
  기록과 모든 이벤트를 PostHog에서 삭제하며, 이 삭제를 정기적으로 실행합니다.
- **게임을 켜지 않고:** 환경 변수 `DESMON_ANALYTICS=0`을 설정합니다.
- **삭제 요청:** 게임 데이터 폴더(macOS: `~/Library/Application Support/DesMon/`, Windows: `%APPDATA%\DesMon\`)의
  `analytics.json`에 있는 `installId`를 이메일로 보내 주시면 해당 ID의 모든 데이터를 삭제합니다.
- 개발·테스트·패키징되지 않은 빌드는 통계를 보내지 않습니다.

### 4. 연락처

DesMon Developers — devvvick@gmail.com
