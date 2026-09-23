# Apple Silicon Mac에서 사용하기

Windows와 Mac은 같은 GUI, 원문 자료, 번역 저장본, 공동작업 JSON을 사용합니다. 게임을 실행하지 않고 동봉된 원문 자료로 번역할 수 있습니다. Mac용 Node.js를 제외한 별도 라이브러리나 Rosetta는 필요하지 않습니다.

1. [Node.js 공식 다운로드](https://nodejs.org/en/download)에서 macOS용 LTS를 설치합니다. Apple Silicon용 아키텍처는 **ARM64**입니다. Node.js 22 이상이 필요합니다.
2. 받은 ZIP을 다운로드 폴더나 문서 폴더의 **새 폴더에 전부 압축 해제**합니다. 이전 작업실 폴더에 덮어쓰지 마세요.
3. `DEI-Korean-Workbench` 안의 **Start.command**를 더블클릭합니다. 브라우저에서 `http://127.0.0.1:3219/`가 열립니다. 터미널 창은 닫아도 작업실은 실행 상태로 남습니다.
4. 번역 후 **초안 저장 / 검수 완료**를 누릅니다. 종료하려면 **Stop.command**를 실행합니다.

실행 권한이 없다는 안내가 나오면 터미널에서 `bash `를 입력하고, Start.command 파일을 창으로 끌어온 뒤 Enter를 누르세요. 종료도 같은 방법으로 Stop.command를 실행할 수 있습니다. 직접 실행 권한을 설정할 때는 [Apple의 실행 파일 안내](https://support.apple.com/en-mt/guide/terminal/apdd100908f-06b3-4e63-8a87-32e71241bab4/mac)를 참고하세요. ZIP에는 실행 권한을 포함했습니다.

## 기존 작업 이어받기

새 배포본의 `data/workspace.json`에는 배포 당시 작업이 들어 있습니다. 본인이 더 작업한 저장본이 있다면 먼저 전체 백업을 보관하고, 작업실을 Stop.command로 종료한 상태에서 그 백업을 새 폴더의 `data/workspace.json`으로 복사한 뒤 다시 실행합니다. Windows에서 내려받은 전체 백업도 그대로 사용할 수 있습니다.

GitHub 공동작업에는 **기존 공통 기준본**을 계속 사용합니다. OS가 달라졌다는 이유로 기준본을 다시 만들 필요가 없습니다. 변경 파일 업로드와 비교·합치기는 Windows와 같은 순서입니다. 동시에 서로 다른 작업실 폴더를 실행하지 마세요.

## 모드 파일 경로 — 다시 읽을 때만 필요

처음 열고 번역할 때에는 모드 파일 경로가 필요하지 않습니다. `data/catalog.json`에 추출한 원문과 기존 번역이 포함되어 있습니다.

모드가 업데이트되어 **모드 파일 다시 읽기**를 사용하려면, `config.json` 옆에 **config.local.json**을 만들어 자신의 실제 파일 경로를 지정하세요. 이 파일은 자신의 PC에만 두고 GitHub에 올리지 않습니다. 지정하지 않은 항목은 config.json의 경로를 사용합니다. 다섯 파일 모두 필요합니다.

```json
{
  "paths": {
    "기존 DEI 한글패치": "~/Documents/DEI Mods/DEI_KOR.pack",
    "로마 2 한글패치": "~/Documents/DEI Mods/local_kr.pack",
    "DEI Part 1": "~/Documents/DEI Mods/___divide_et_impera_010_part1.pack",
    "DEI Part 9": "~/Documents/DEI Mods/___divide_et_impera_010_part9.pack",
    "DEI Part 10": "~/Documents/DEI Mods/___divide_et_impera_010_part10.pack"
  }
}
```

위 경로는 예시입니다. `~/`는 자신의 홈 폴더, 상대 경로는 작업실 폴더를 기준으로 해석합니다. 외장 디스크는 `/Volumes/디스크 이름/...` 같은 실제 경로를 사용하세요. 파일명을 포함한 경로를 입력하고, 다시 읽기 전에 전체 작업 백업을 내려받으세요.

## 확인 범위

이 배포본은 Node.js 기반 웹 작업실의 실행·한글 저장·복원·번역 병합을 위한 것입니다. Rome II 게임 자체의 Apple Silicon 실행이나 게임에서의 패치 표시를 보증하는 것은 아닙니다. 운영체제별 자동 시험 결과는 저장소의 Actions에서 확인할 수 있습니다.
