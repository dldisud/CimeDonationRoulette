# Cime Donation Roulette

![Minecraft Paper](https://img.shields.io/badge/Minecraft%20Paper-1.21-green?style=flat-square)
![Minecraft Forge](https://img.shields.io/badge/Minecraft%20Forge-1.20.1-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

씨미(Cime) 플랫폼의 후원 및 채팅 내역과 연동하여, 마인크래프트 게임 내에서 가중치 기반의 룰렛 이벤트를 트리거할 수 있게 해주는 서버 연동 플러그인 및 모드입니다. 외부 데이터 연동을 통해 스트리머와 시청자 간의 상호작용을 마인크래프트 게임 플레이로 확장할 수 있습니다.

## ✨ 주요 기능 (Features)

* **실시간 이벤트 연동**: 방송 후원 및 채팅과 즉각적으로 연동되어 마인크래프트 내 이벤트를 발생시킵니다.
* **가중치 기반 확률 시스템**: 각 이벤트(아이템 지급, 몹 스폰, 버프/디버프 등)에 개별 가중치를 설정하여 다채로운 확률적 재미를 제공합니다.
* **채팅 연동 모드 ON/OFF 제어**: 후원뿐만 아니라 일반 시청자 채팅을 통해서도 룰렛이 돌아가게 할지 여부를 손쉽게 켜고 끌 수 있습니다.
* **천장 (Pity) 시스템 지원**: 채팅 연동 시청자들을 위해, 일정 횟수 이상 꽝이 지속되면 확정적으로 좋은 혹은 강력한 이벤트가 터지게 만들어주는 '천장' 설정이 가능합니다.
* **다중 플랫폼 지원**: 최신 Paper 환경(1.21)과 인기 있는 모드 로더인 Forge 환경(1.20.1)의 서버 사이드를 모두 지원합니다.

## 📦 제공되는 버전 (Supported Versions)

본 리포지토리에서는 두 가지 마인크래프트 환경을 지원합니다:

### 1. Paper 플러그인
* **지원 버전**: Minecraft Paper 1.21
* **특징**: Spigot 또는 Paper 계열의 서버 환경에 스크립트 기반으로 가볍고 빠르게 적용하기 적합합니다.

### 2. Forge 모드
* **지원 버전**: Minecraft Forge 1.20.1 (Forge 47 이상 필수)
* **특징**: 대형 모드팩을 즐기는 환경에서 서버 사이드 모드로 충돌 없이 함께 구동할 수 있습니다.

## 🚀 설치 방법 (Installation)

1. **Releases** 탭(또는 프로젝트의 빌드 결과물)에서 서버 환경(Paper 1.21 또는 Forge 1.20.1)에 맞는 `.jar` 파일을 다운로드합니다.
2. 마인크래프트 서버 폴더의 `plugins/` (Paper) 또는 `mods/` (Forge) 디렉토리에 다운로드한 파일을 위치시킵니다.
3. 마인크래프트 서버를 구동하여 설정 파일이 생성되도록 합니다.
4. 서버 종류 후 플러그인/모드 폴더 내에 생성된 `config.yml` 파일을 열어 필수 환경 설정을 진행합니다. (아래 ⚙️ 설정 방법 참고)
5. 설정을 저장한 후, 서버를 다시 구동하여 게임을 시작합니다. (인게임에서 `/cimeroulette reload`를 사용하여 설정을 바로 적용할 수도 있습니다.)

## ⚙️ 설정 방법 (Configuration)

플러그인/모드를 처음 실행하면 생성되는 `config.yml` 파일에서 봇 연동 및 이벤트 세부 설정을 변경할 수 있습니다.

### 핵심 연동 설정
* `cime.alert-key`: (필수) 씨미 플랫폼에서 발급받은 알림 키(Alert Key)를 입력합니다. 이 값이 있어야 후원 내역을 정상적으로 받아올 수 있습니다.
* `target.player-name`: 룰렛 이벤트 효과를 받을 특정 스트리머(플레이어) 닉네임을 지정합니다. 비워둘 경우 서버에 접속 중인 랜덤 유저에게 발동됩니다.

### 채팅 연동 & 천장 시스템 설정 (Chat & Pity)
* `chat.enabled` (`true`/`false`): 시청자의 일반 채팅에도 룰렛 발동 기회를 부여할지(ON/OFF) 결정합니다.
* `chat.chance-percent`: 일반 채팅 1회당 룰렛이 돌아갈 확률(%)을 설정합니다. (예: `3.0` = 3% 확률)
* `chat.pity.enabled` (`true`/`false`): 채팅 룰렛 천장 시스템 활성화 여부입니다.
* `chat.pity.threshold`: 룰렛이 연속으로 꽝이 났을 때, 몇 번 만에 확정 이벤트를 터뜨릴지 천장 횟수를 지정합니다. (예: `50`회)
* `chat.cooldown`: 도배 방지를 위해 유저당(또는 글로벌) 단위로 채팅 룰렛 쿨타임(초)을 설정할 수 있습니다.

### 룰렛 확률 및 이벤트 (Roulette Settings)
* `roulette.group-weights`: `GOOD`(좋은 이벤트)과 `BAD`(나쁜 이벤트) 등의 그룹별 크게 터지는 가중치 비율을 조절할 수 있습니다.
* `roulette.spin-tiers`: 후원 금액에 따라 룰렛이 몇 번 연속으로 돌아갈지(spins) 티어를 설정합니다. (예: 1000원 단위 1번, 5000원 단위 2번 등)
* `roulette.events`: 게임 안에 발동되는 다양한 이벤트(예: `LAVA_DROP`, `RANDOM_POTION`, `LIGHTNING_STRIKE` 등)들의 개별 켜기/끄기(`enabled`) 및 세부 가중치(`weight`)를 각각 마음대로 튜닝할 수 있습니다.

## 💻 명령어 및 권한 (Commands & Permissions)

*아래 명령어는 주로 Paper 플러그인 환경을 기준으로 작성되었습니다.*

### 명령어 (Commands)
접두사: `/cimeroulette`

* `status` : 현재 연동 상태 및 플러그인 구동 상태를 확인합니다.
* `reload` : 설정 파일(`config.yml`)을 갱신하여 인게임에 즉시 반영합니다.
* `reconnect` : 외부 이벤트 연동 서버와의 연결이 끊어졌을 때 강제로 재연결을 시도합니다.
* `test` : 등록된 룰렛 이벤트를 수동으로 강제 트리거하여 테스트합니다.
* `chat` : 채팅 연동과 관련된 부가 기능을 테스트하거나 제어합니다.

### 권한 (Permissions)
* `cime.roulette.admin` : 플러그인의 모든 관리자 명령어에 접근할 수 있는 권한입니다. (기본 부여 대상: OP)

## 📄 라이선스 (License)

이 프로젝트는 [MIT License](LICENSE)를 따릅니다.
