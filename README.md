# olma-packs

얼마면 돼(BAYZ Works) 앱이 처음 실행할 때 받는 폰 안 인식 모델과 인식 팩.

| 파일 | 내용 |
|---|---|
| `packs.json` | 목록: 모델·팩 버전, 크기, SHA-256 |
| `clip_image_int8.onnx` | 사진 → 512 특징 (OpenAI CLIP ViT-B/16 사진 부분, int8) |
| `<팩>.json` / `<팩>.bin` | 이름 목록(한국어·영어) / 이름마다 미리 계산한 512 특징 (half float) |

팩: `base` 기본 생활용품(124) · `food` 음식·음료(130) · `flower` 꽃·식물(155) · `car` 자동차·탈것(50)
v2에서 더함: `kitchen` 주방용품(55) · `cleaning` 생활화학·욕실(47) · `beauty` 화장품(39) · `tools` 공구·DIY(38) · `stationery` 문구·사무(40) · `electronics` 전자기기(38) · `fashion` 옷·신발·잡화(42)

v4에서 더함 (브랜드 + 종류 이름, 생김새 설명, 무게 분류 preset 포함): `brand_appliance` 브랜드 가전(51) · `brand_digital` 브랜드 디지털(58) · `brand_living` 브랜드 생활용품(63)

`community/`: 모두의 기억 (태그 없이 main에서 받음, 앱을 켤 때 새 판 확인)

앱은 태그(`v1` 등)를 붙인 주소에서 받는다: `https://raw.githubusercontent.com/qqhrqqhr2/olma-packs/v2/packs.json` (v1은 기본 4팩, 예전 앱용)`

## 라이선스
- 모델: OpenAI CLIP (MIT License, Copyright (c) 2021 OpenAI) — https://github.com/openai/CLIP
- 팩 데이터: BAYZ Works

v5 (2026-11-02): 모든 팩을 각도별 여러 줄로 다시 만듦 — 이름 하나에 기본·위에서·옆/뒤·가까이 설명 줄(앱은 가장 닮은 줄로 비교). 기본 팩에 labels_more 전부 포함(생활용품 424·음식 386·꽃 155·탈것 173), 팩끼리 겹치는 이름은 앞 팩에만. 만드는 법: olma 저장소 tools/clip/build_all_packs.py
