# Cime Donation Roulette (시메 후원 룰렛)

**Cime Donation Roulette**는 시메(Cime) 후원 및 채팅 내역을 연동하여, 마인크래프트 게임 내에서 가중치 기반의 룰렛 이벤트를 트리거할 수 있게 해주는 마인크래프트 플러그인 & 포지(Forge) 모드 프로젝트입니다.

## 📦 제공되는 버전 (Versions)

본 리포지토리에는 두 가지 마크 환경을 위한 버전이 제공됩니다.

### 1. Paper 플러그인 (1.21)
* **파일 위치**: `build/libs/CimeDonationRoulette.jar`
* **지원 버전**: Minecraft Paper 1.21
* **기능**: Spigot/Paper 서버에서 독립적으로 룰렛 이벤트를 실행할 수 있습니다.
* **명령어**: `/cimeroulette <status|reload|reconnect|test|chat>`
* **권한**: `cime.roulette.admin` (관리자 전용 제어 권한)

### 2. Forge 모드 (1.20.1)
* **파일 위치**: `build/libs/cimedonationroulette-0.1.0.jar`
* **지원 버전**: Minecraft Forge 1.20.1 (Forge 47 이상)
* **기능**: 서버 사이드 모드로 동작하여 룰렛 이벤트와 연동됩니다.

## 🛠️ 추가 구성 요소 (Web & Bot)

플러그인/모드뿐만 아니라 방송 화면 출력 및 관리를 위한 웹 환경과 봇 서버가 포함되어 있습니다.
* **Bot Server**: `apps/bot-server` (후원 및 채팅 데이터 수집)
* **Admin Web**: `apps/admin-web` (룰렛 가중치 및 이벤트 관리 웹페이지)
* **방송용 UI**: `채팅html/`, `후원html/` 디렉토리에 포함된 방송 오버레이용 소스

## 🚀 설치 및 적용 방법 (Installation)

### ◾ 마인크래프트 서버 적용
1. 본인 서버 환경(Paper 1.21 또는 Forge 1.20.1)에 맞는 `.jar` 파일을 다운로드합니다.
2. 서버의 `plugins/` 또는 `mods/` 폴더에 해당 jar 파일을 넣습니다.
3. 서버를 구동하여 구성 파일(`config.yml` 등)이 생성되게 한 후, 필요한 연동 설정값(주소 등)을 세팅합니다.

### ◾ 웹 및 봇 서버 구동 (개발/직접 구동 시)
```bash
# 의존성 설치 (pnpm 권장)
pnpm install

# 봇 서버 실행
npm run dev:bot

# 관리자 웹 실행
npm run dev:web
```

## 📜 라이선스 (License)
MIT License
