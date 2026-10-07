# DesMon — Desktop Monster

키보드를 두드리고 마우스를 클릭하면 영웅이 몬스터를 공격하는 픽셀 아트 데스크톱 동료 게임입니다. 작업하는 동안 몬스터를 처치하고, 장비와 동료를 모으며 영웅을 성장시켜 보세요.

이 저장소는 DesMon 설치 파일과 배포 안내를 제공합니다.

**[v0.13.0 다운로드](https://github.com/mojomoth/desktop-monster-releases/releases/tag/v0.13.0)** · [전체 릴리스](https://github.com/mojomoth/desktop-monster-releases/releases) · [문제 제보](https://github.com/mojomoth/desktop-monster-releases/issues)

## 다운로드

현재 배포는 **v0.13.0 개발 미리보기(Pre-release)**입니다. 2026년 10월 3일 생성된 설치 파일을 제공합니다.

| 운영체제 | 다운로드 | 크기 |
| --- | --- | --- |
| macOS 12 이상 · Apple Silicon (M 시리즈, arm64) | [DesMon-0.13.0-arm64.dmg](https://github.com/mojomoth/desktop-monster-releases/releases/download/v0.13.0/DesMon-0.13.0-arm64.dmg) | 약 107 MiB |
| Windows 11 · x64 | [DesMon-Setup-0.13.0.exe](https://github.com/mojomoth/desktop-monster-releases/releases/download/v0.13.0/DesMon-Setup-0.13.0.exe) | 약 91 MiB |

설치 파일만으로 실행할 수 있으며 Node.js나 개발 도구는 필요하지 않습니다. Intel Mac, Windows ARM 및 Linux 전용 빌드는 제공하지 않습니다. Windows 설치 파일은 생성했지만 **Windows 실기기 실행 검증은 아직 완료하지 않았습니다.**

릴리스의 **Assets**에서 설치 파일을 선택하세요. GitHub가 제공하는 `Source code` 압축 파일은 설치 파일이 아닙니다.

## 설치와 첫 실행

### macOS

1. DMG를 열고 `DesMon.app`을 **응용 프로그램(Applications)** 폴더에 복사합니다.
2. 응용 프로그램 폴더에서 DesMon을 실행합니다.
3. 시작 안내에서 **창에서 시작** 또는 **전체 입력 연결**을 선택합니다.

현재 macOS 빌드는 개발자 서명과 Apple 공증을 받지 않았습니다. 출처를 확인한 뒤에도 확인되지 않은 개발자 경고로 실행이 차단되면 **시스템 설정 → 개인정보 보호 및 보안 → 그래도 열기**를 사용하세요. 자세한 절차는 [Apple의 앱 실행 안내](https://support.apple.com/ko-kr/102445)를 참고하세요.

다른 앱에서 타이핑하거나 클릭할 때도 공격하려면 **시스템 설정 → 개인정보 보호 및 보안 → 손쉬운 사용**에서 **DesMon**을 허용하세요. 허용 후 앱을 다시 실행하고 트레이에 **입력: 전체 입력 연결됨**이 표시되는지 확인합니다.

macOS 12에서는 **시스템 환경설정 → 보안 및 개인정보 보호**를 사용합니다. 앱 실행 허용은 **일반**, 입력 권한은 **개인정보 보호 → 손쉬운 사용**에서 찾을 수 있습니다.

**창에서 시작**을 선택하면 게임 창에 포커스가 있을 때의 키보드 입력과 클릭으로 플레이할 수 있습니다. 나중에 트레이의 입력 상태 또는 **설정 → 시작 안내 다시 보기…**에서 전체 입력을 연결할 수 있습니다.

### Windows

1. `DesMon-Setup-0.13.0.exe`를 실행해 설치합니다.
2. 설치된 DesMon을 실행하고 시작 안내에서 입력 방식을 선택합니다.
3. 시스템 트레이의 DesMon 아이콘에서 메뉴를 엽니다.

현재 설치 파일은 개발용 미서명 빌드입니다. 설치 제거 후에도 저장 데이터는 유지됩니다.

## 플레이

- **입력으로 전투:** 키보드 입력과 마우스 클릭으로 몬스터를 공격하고 경험치와 금화를 얻습니다.
- **장비와 성장:** 장비를 장착·강화하고, 영웅 환생과 도감 수집을 진행합니다.
- **동료 수집:** 보스를 처치해 동료를 얻고, 동료 파티와 함께 자동 공격합니다.
- **모험 관리:** 메뉴 막대 또는 시스템 트레이의 **영웅과 모험 기록…**에서 영웅·동료·장비와 기록을 확인합니다.
- **설정:** 트레이의 **설정**에서 게임 크기·음소거·화면 흔들림을 변경합니다.
- **종료:** 트레이의 **종료**를 선택합니다.

## 온라인 기능의 현재 상태

로컬 사냥은 Steam 없이 이용할 수 있습니다. 순위·PvP·협동 레이드는 호환 서버 연결이 필요합니다. 이번 설치 파일 배포에는 운영 서버 업데이트가 포함되지 않으며, 온라인 기능의 정상 동작은 검증하지 않았습니다.

v0.13.0의 **Steam 사냥**은 로컬 진행과 분리된 개발 기능입니다. 실제 Steam App ID와 인증·서버 구성이 필요합니다. **봉인·해제·장터 거래는 출시 전 검증이 끝나지 않아 잠겨 있습니다.** 이번 배포는 Steam 거래 출시 버전이 아닙니다.

## 저장 데이터와 업데이트

진행 상황은 자동으로 저장됩니다.

| 운영체제 | 저장 폴더 |
| --- | --- |
| macOS | `~/Library/Application Support/DesMon/` |
| Windows | `%APPDATA%\DesMon\` |

업데이트 전에는 앱을 종료하고 **저장 폴더 전체를 백업**하세요. 새 설치 파일을 실행하거나 macOS의 기존 앱을 교체한 뒤 다시 실행하면 됩니다. `identity.json`에는 인증 정보가 있으므로 공개하거나 이슈에 첨부하지 마세요.

게임 안에서 진행 초기화와 최근 백업 복원을 사용할 수 있습니다. 이전 버전으로 돌아갈 때는 해당 버전에서 만든 백업을 사용하세요.

## 다운로드 파일 확인

릴리스에 첨부된 [SHA256SUMS.txt](https://github.com/mojomoth/desktop-monster-releases/releases/download/v0.13.0/SHA256SUMS.txt)와 다운로드한 파일의 SHA-256을 비교할 수 있습니다.

macOS에서 다운로드 폴더로 이동한 뒤:

```sh
shasum -a 256 DesMon-0.13.0-arm64.dmg
```

Windows PowerShell에서 다운로드 폴더로 이동한 뒤:

```powershell
Get-FileHash .\DesMon-Setup-0.13.0.exe -Algorithm SHA256
```

출력된 해시가 `SHA256SUMS.txt`의 해당 파일 값과 일치하는지 확인하세요.

## 문제 제보

[Issues](https://github.com/mojomoth/desktop-monster-releases/issues)에 앱 버전, 운영체제와 CPU 종류, 재현 방법, 기대한 동작과 실제 동작을 남겨주세요. 스크린샷은 도움이 되지만 저장 파일과 인증 정보는 첨부하지 마세요.
