# Cime Donation Roulette

![Minecraft Paper](https://img.shields.io/badge/Minecraft%20Paper-1.21-green?style=flat-square)
![Minecraft Forge](https://img.shields.io/badge/Minecraft%20Forge-1.20.1-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

씨미(Cime) 플랫폼의 후원 및 채팅 내역과 연동하여, 마인크래프트 게임 내에서 가중치 기반의 룰렛 이벤트를 트리거할 수 있게 해주는 서버 연동 플러그인 및 모드입니다. 외부 데이터 연동을 통해 스트리머와 시청자 간의 상호작용을 마인크래프트 게임 플레이로 확장할 수 있습니다.

## ✨ 주요 기능 (Features)

* **실시간 이벤트 연동**: 방송 후원 및 채팅과 즉각적으로 연동되어 마인크래프트 내 이벤트를 발생시킵니다.
* **가중치 기반 확률 시스템**: 각 이벤트(아이템 지급, 몹 스폰, 버프/디버프 등)에 개별 가중치를 설정하여 다채로운 확률적 재미를 제공합니다.
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
3. 마인크래프트 서버를 구동합니다.
4. 처음 구동 시 플러그인/모드 폴더에 생성되는 설정 파일(`config.yml` 등)을 열어 연동에 필요한 필수 정보(웹소켓 주소, 포트 등)를 입력합니다.
5. 설정을 저장한 후, 서버를 재시작하거나 리로드 명령어를 사용하여 설정을 서버에 적용합니다.

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
