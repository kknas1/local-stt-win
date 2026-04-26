# Local STT Windows v3.0.0

## Release Assets

- `local_stt_v3_1.0.0_full.exe`
- `local_stt_v3_1.0.0_safe.exe`
- `ggml-large-v3-turbo-q5_0.bin`

## 변경사항

- Windows 오프라인 설치본 제공
- 여러 STT 모델 선택 구조
- CPU 사용량 옵션
- 화자 분리 옵션
- 모델팩/외부 모델 추가 설치 방식
- 회사 PC 호환성을 위한 safe 설치본 제공

## 포함 기능

- 오프라인 음성 전사
- `faster-whisper` 기반 STT
- `whisper.cpp` 기반 STT
- 화자 분리
- 로컬 웹 UI
- Windows 설치 프로그램

## 설치본 차이

### full

- 전체 기능 설치본입니다.
- 화자 분리와 요약 관련 런타임을 포함합니다.
- 일부 회사 PC에서는 torch DLL 오류가 발생할 수 있습니다.

### safe

- torch 계열 런타임을 제외한 설치본입니다.
- 회사 PC에서 DLL 오류가 나는 경우 사용할 수 있습니다.
- 화자 분리와 AI 요약 기능은 제한될 수 있습니다.

## 추가 모델

`ggml-large-v3-turbo-q5_0.bin`은 설치본에 포함되어 있지 않은 선택 모델입니다.

설치 파일과 같은 폴더에 두고 설치하거나, 설치 후 아래 폴더에 복사해서 사용할 수 있습니다.

```text
%LOCALAPPDATA%\Programs\LocalSTT\runtime\models\whispercpp
```

## SHA256

릴리즈 업로드 파일의 SHA256입니다.

```text
local_stt_v3_1.0.0_full.exe  SHA256: 7437e3124b2d23cfe3dc4944c5b0bd4a622b56da0554550cf0a15e5b9508e64b
local_stt_v3_1.0.0_safe.exe  SHA256: d2dd37528ae012b6f317ac95779441c457990528d86a65f1484c43cbcd3c570e
ggml-large-v3-turbo-q5_0.bin SHA256: 394221709cd5ad1f40c46e6031ca61bce88931e6e088c188294c6d5a55ffa7e2
```

## Known Issues

- 8GB RAM PC에서 큰 모델은 느리거나 실패할 수 있습니다.
- 화자 분리는 CPU를 많이 사용할 수 있습니다.
- 일부 회사 PC에서 보안 정책 또는 DLL 문제로 실행이 제한될 수 있습니다.
- STT 결과는 공식 기록으로 사용하기 전에 사람이 검토해야 합니다.
