# olma-packs

얼마면 돼(BAYZ Works) 앱이 처음 실행할 때 받는 폰 안 인식 모델과 인식 팩.

| 파일 | 내용 |
|---|---|
| `packs.json` | 목록: 모델·팩 버전, 크기, SHA-256 |
| `clip_image_int8.onnx` | 사진 → 512 특징 (OpenAI CLIP ViT-B/16 사진 부분, int8) |
| `<팩>.json` / `<팩>.bin` | 이름 목록(한국어·영어) / 이름마다 미리 계산한 512 특징 (half float) |

팩: `base` 기본 생활용품(124) · `food` 음식·음료(130) · `flower` 꽃·식물(155) · `car` 자동차·탈것(50)

앱은 태그(`v1` 등)를 붙인 주소에서 받는다: `https://raw.githubusercontent.com/qqhrqqhr2/olma-packs/v1/packs.json`

## 라이선스
- 모델: OpenAI CLIP (MIT License, Copyright (c) 2021 OpenAI) — https://github.com/openai/CLIP
- 팩 데이터: BAYZ Works
