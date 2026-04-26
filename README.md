# Local STT for Windows

Windows용 오프라인 음성 전사 프로그램입니다.

공공기관 민원 업무를 처리하다 보면 녹취 파일, 통화 녹음 파일, 음성 자료를 받아 검토해야 하는 경우가 있습니다. 특히 내부망 환경에서는 외부 STT 서비스를 쓰기 어렵고, 별도 STT 시스템이 없는 기관에서는 1시간이 넘는 녹취 파일을 담당자가 직접 처음부터 끝까지 들어야 하는 일이 생깁니다.

이 프로그램은 그런 상황에서 조금이라도 업무 부담을 줄이기 위해 만들었습니다. GPU 없이 일반 Windows PC의 CPU만으로 동작하며, 음성 파일을 로컬 PC 안에서 전사합니다. 개인정보나 민원 관련 정보 때문에 파일을 외부로 반출하기 어려운 환경에서도 활용할 수 있습니다.

다만 CPU만 사용하는 로컬 프로그램이기 때문에 아주 고성능의 AI STT 시스템만큼 빠르거나 정확하지는 않을 수 있습니다. 예를 들어 10분짜리 음성 파일도 PC 성능, 선택한 모델, 화자 분리 여부에 따라 변환에 15분 이상 걸릴 수 있습니다. 그래도 변환이 진행되는 동안 다른 업무를 할 수 있으므로, 녹취 파일을 전부 직접 듣는 것보다는 도움이 될 수 있습니다.

이 프로그램의 내부 반입, 설치, 활용, 처리 결과 검토에 대한 책임은 모두 사용자와 소속 기관에 있습니다. 기관의 보안 정책과 개인정보 처리 기준을 반드시 확인한 뒤 사용하세요.

## Download

대부분의 사용자는 아래 **full 버전**을 받으면 됩니다.

- [codex_stt_v3_1.0.0_full.exe](https://github.com/kknas1/local-stt-win/releases/download/v3.0.0/codex_stt_v3_1.0.0_full.exe): 전체 기능 설치본. 일반적으로 이 파일을 권장합니다.
- [codex_stt_v3_1.0.0_safe.exe](https://github.com/kknas1/local-stt-win/releases/download/v3.0.0/codex_stt_v3_1.0.0_safe.exe): full 버전에서 torch DLL 오류가 나는 PC용 안전 설치본입니다.
- [ggml-large-v3-turbo-q5_0.bin](https://github.com/kknas1/local-stt-win/releases/download/v3.0.0/ggml-large-v3-turbo-q5_0.bin): 선택 설치용 whisper.cpp 추가 모델입니다.

릴리즈 페이지에서 직접 확인하려면 아래 주소를 사용하세요.

- [Local STT Windows v3.0.0 Release](https://github.com/kknas1/local-stt-win/releases/tag/v3.0.0)

## 주요 기능

- 오프라인 음성 전사
- 통화 녹취 파일 처리
- 여러 STT 모델 선택
- CPU 사용량 선택
- 화자 분리
- 스테레오/모노 파일 처리
- 로컬 PC 내부 처리

## 권장 사양

- Windows 10/11 64-bit
- RAM 8GB 이상
- GPU 불필요
- 긴 통화 파일은 CPU 성능에 따라 처리 시간이 달라질 수 있음

## 설치 방법

1. [codex_stt_v3_1.0.0_full.exe](https://github.com/kknas1/local-stt-win/releases/download/v3.0.0/codex_stt_v3_1.0.0_full.exe)를 다운로드합니다.
2. 다운로드한 `codex_stt_v3_1.0.0_full.exe`를 실행합니다.
3. full 버전에서 torch DLL 오류가 나는 PC에서는 [codex_stt_v3_1.0.0_safe.exe](https://github.com/kknas1/local-stt-win/releases/download/v3.0.0/codex_stt_v3_1.0.0_safe.exe)를 사용합니다.
4. 설치 화면 안내에 따라 설치합니다.

기본 설치 위치는 다음과 같습니다.

```text
%LOCALAPPDATA%\Programs\LocalSTT
```

설치가 끝나면 바탕화면과 시작 메뉴에 `LocalSTT` 실행 아이콘이 생성됩니다.

## 실행 방법

1. 바탕화면의 `LocalSTT` 아이콘을 실행합니다.
2. 프로그램이 로컬 서버를 시작합니다.
3. 기본 브라우저가 자동으로 열리고 아래 주소로 접속됩니다.

```text
http://127.0.0.1:8000
```

기본 브라우저가 Chrome이면 Chrome으로 열립니다. 다른 브라우저가 기본값이면 해당 브라우저로 열립니다.

브라우저가 자동으로 열리지 않으면 직접 주소창에 아래 주소를 입력하세요.

```text
http://127.0.0.1:8000
```

## 사용 방법

1. 음성 파일을 선택합니다.
2. 처리 모드와 STT 모델을 선택합니다.
3. CPU 사용량을 선택합니다.
4. 화자 분리 사용 여부를 선택합니다.
5. 실행 버튼을 누릅니다.
6. 처리 완료 후 전사 결과와 화자 구간을 확인합니다.

## 서버 중지 방법

브라우저 창을 닫아도 LocalSTT 서버가 계속 실행 중일 수 있습니다.

서버를 완전히 종료하려면 시작 메뉴에서 다음 항목을 실행하세요.

```text
Start Menu > LocalSTT > Stop LocalSTT
```

정상 종료되면 `LocalSTT has been stopped.` 메시지가 표시됩니다.

## 제거 방법

Windows 설정에서 일반 프로그램처럼 제거할 수 있습니다.

```text
설정 > 앱 > 설치된 앱 > LocalSTT > 제거
```

또는 시작 메뉴의 `Uninstall LocalSTT` 항목을 실행할 수 있습니다.

## 모델 선택 가이드

- `faster-whisper small`: 기본 권장. 8GB RAM PC에서 균형이 좋습니다.
- `faster-whisper medium`: 정확도 우선. 별도 모델팩이 필요할 수 있습니다.
- `whisper.cpp base`: 빠른 초안 생성용입니다.
- `whisper.cpp tiny`: 가장 빠르지만 정확도는 낮습니다.
- `whisper.cpp large-v3-turbo-q5_0`: 추가 모델 파일을 넣은 경우 선택할 수 있습니다. CPU-only PC에서는 느릴 수 있습니다.

## 추가 모델 사용 방법

기본 설치 파일에는 용량과 설치 안정성을 고려해 일부 모델만 포함됩니다. `large-v3-turbo` 같은 큰 모델은 설치 파일 안에 포함하지 않습니다.

필요한 경우 모델 파일을 별도로 다운로드해서 설치 폴더에 넣으면 사용할 수 있습니다.

### whisper.cpp 추가 모델 넣기

`whisper.cpp`용 모델 파일은 보통 아래와 같은 이름입니다.

```text
ggml-large-v3-turbo-q5_0.bin
```

설치된 LocalSTT 폴더 안의 다음 위치에 모델 파일을 복사합니다.

```text
%LOCALAPPDATA%\Programs\LocalSTT\runtime\models\whispercpp
```

예시:

```text
%LOCALAPPDATA%\Programs\LocalSTT\runtime\models\whispercpp\ggml-large-v3-turbo-q5_0.bin
```

복사 후 LocalSTT를 다시 실행하면 모델 선택 목록에 추가 모델이 표시됩니다.

### 설치 파일 옆에 모델을 두고 설치하는 방법

새로 설치할 때는 설치 파일과 같은 폴더에 모델 파일을 함께 둘 수도 있습니다.

```text
codex_stt_v3_1.0.0_full.exe
ggml-large-v3-turbo-q5_0.bin
```

이 상태에서 설치 파일을 실행하면 `ggml-*.bin` 모델 파일이 자동으로 아래 위치로 복사됩니다.

```text
%LOCALAPPDATA%\Programs\LocalSTT\runtime\models\whispercpp
```

또는 설치 파일 옆에 `models` 폴더를 만들고 모델 구조를 넣을 수도 있습니다.

```text
codex_stt_v3_1.0.0_full.exe
models\
  whispercpp\
    ggml-large-v3-turbo-q5_0.bin
  faster-whisper-local\
    medium\
      model.bin
      config.json
      tokenizer.json
      vocabulary.json
```

이 상태에서 설치하면 `models` 폴더 전체가 아래 위치로 복사됩니다.

```text
%LOCALAPPDATA%\Programs\LocalSTT\runtime\models
```

## 화자 분리

화자 분리는 사용자가 선택할 수 있습니다.

- 끔
- 자동
- 스테레오 채널 우선
- 모노/혼합 분석

화자 수는 고정하지 않고 자동 추정하는 방향으로 설계합니다. 결과 라벨은 `A/B/C/D` 형식으로 표시됩니다.

화자 분리를 켜면 CPU 사용량과 처리 시간이 늘어날 수 있습니다.

## 개인정보와 보안

이 프로그램은 입력 파일을 외부 서버로 업로드하지 않습니다. 전사와 분석은 로컬 PC에서 수행됩니다.

다만 내부망 반입, 설치 허가, 개인정보 처리 적합성은 각 기관의 보안 정책을 따라야 합니다.

## 알려진 제한사항

- 회사 또는 기관 보안 정책에 따라 `.exe` 실행이 차단될 수 있습니다.
- 일부 PC에서는 torch 관련 DLL 문제가 발생할 수 있습니다.
- 긴 파일, 화자 분리, 정확도 우선 모델은 CPU 사용량이 높을 수 있습니다.
- STT 결과는 부정확할 수 있으므로 공식 기록이나 민원 처리에 사용하기 전 반드시 사람이 검토해야 합니다.

## License

이 프로젝트 자체 코드는 별도 LICENSE를 따릅니다. 포함된 오픈소스 라이브러리와 모델의 라이선스는 `NOTICE.md`를 확인하세요.
