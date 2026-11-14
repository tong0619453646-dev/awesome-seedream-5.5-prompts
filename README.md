<div align="center">

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=banner&utm_campaign=awesome-seedream-5.5-prompts"><img src="assets/banner.jpg" alt="Awesome Seedream 5.5 Prompts" width="100%"></a>

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey)](LICENSE)
[![Prompts](https://img.shields.io/badge/Prompts-51_cases-111111)](README.md#menu)
[![Try Seedream 5.5 on APIKO](https://img.shields.io/badge/Try_Seedream_5.5-on_APIKO-4F46E5)](https://apiko.app/models/seedream-5.5?utm_source=github&utm_medium=badge&utm_campaign=awesome-seedream-5.5-prompts&utm_content=model_try)
[![Seedream 5.5 API docs](https://img.shields.io/badge/Seedream_5.5-API_docs-111111)](https://apiko.app/docs/api-manual/image-series/seedream-5.5/images?utm_source=github&utm_medium=badge&utm_campaign=awesome-seedream-5.5-prompts&utm_content=docs)

[![🇺🇸 English](https://img.shields.io/badge/%F0%9F%87%BA%F0%9F%87%B8_English-Current-111111)](README.md)
[![🇨🇳 简体中文](https://img.shields.io/badge/%F0%9F%87%A8%F0%9F%87%B3_%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-%E6%9F%A5%E7%9C%8B-4F46E5)](README_zh-CN.md)
[![🇹🇼 繁體中文](https://img.shields.io/badge/%F0%9F%87%B9%F0%9F%87%BC_%E7%B9%81%E9%AB%94%E4%B8%AD%E6%96%87-%E6%9F%A5%E7%9C%8B-4F46E5)](README_zh-TW.md)
[![🇰🇷 한국어](https://img.shields.io/badge/%F0%9F%87%B0%F0%9F%87%B7_%ED%95%9C%EA%B5%AD%EC%96%B4-%EB%B3%B4%EA%B8%B0-4F46E5)](README_ko.md)

</div>

# Awesome Seedream 5.5 Prompts

<a id="introduction"></a>
## 🌟 Introduction

**Seedream 5.5 prompts: 51 examples with the images they made, from ByteDance Seed, BytePlus and creators: photos, posters, transparent PNGs, characters.**

Every result on this page was made with Seedream 5.5. Copy a prompt, or send it to the playground and change the details.

Search and filter them on [apiko.app/seedream-5-5-prompts](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=readme&utm_campaign=awesome-seedream-5.5-prompts&utm_content=intro).

> [!NOTE]
> Each prompt is kept exactly as its author posted it, so most are in English; titles and descriptions are ours. Every case credits the author and links to the original post.

<a id="quick-start"></a>
## 🚀 Quick start

**In the browser:** every case has a **Run on APIKO** link. It opens the example on [apiko.app](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=quickstart&utm_campaign=awesome-seedream-5.5-prompts&utm_content=browser); press **Use** there to load the prompt into the Seedream 5.5 playground.

**With the API:** create an [APIKO API key](https://apiko.app/dashboard/apikeys?utm_source=github&utm_medium=quickstart&utm_campaign=awesome-seedream-5.5-prompts&utm_content=api_key), then create an async task and poll it until the image is ready.

```bash
export APIKO_API_KEY="your_key_here"

TASK_ID=$(curl -s https://api.apiko.app/v1/images/generations \
  -H "Authorization: Bearer $APIKO_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
  "model": "seedream-5.5",
  "prompt": "A minimalist poster of a paper boat on a calm lake at sunrise, the title \"Morning\" in bold serif type.",
  "size": "16:9",
  "resolution": "1K",
  "async": true
}' | python3 -c 'import json,sys; print(json.load(sys.stdin)["id"])')

# When status is "completed", the image is at data[0].url (kept for 24 hours).
while :; do
  TASK=$(curl -s https://api.apiko.app/v1/tasks/$TASK_ID \
    -H "Authorization: Bearer $APIKO_API_KEY")
  printf '%s\n' "$TASK"
  printf '%s' "$TASK" | grep -qE '"status": *"(completed|failed)"|"error": *\{' && break
  sleep 5
done
```

Endpoints: `POST https://api.apiko.app/v1/images/generations` (create a task) · `GET https://api.apiko.app/v1/tasks/{id}` (read the status and result)

<a id="how-to-write"></a>
## ✍️ How to write a Seedream 5.5 prompt

Four structures that recur in the prompts on this page.

- **Photograph it like a camera would** · `Format + angle + light source + film or lens + what stays imperfect` — The realism prompts name the frame (vertical 3:4, ultra-wide, tilted 25°), the light (flash, window light, sodium lamp) and the grain or underexposure they want.
- **Quote every word** · `Layout + "exact text in quotes" + hierarchy + "no extra text"` — Posters, labels and infographics put each line in quotes and say where it sits, then forbid invented words.
- **Ask for transparency in words and in the setting** · `Subject + "transparent background" + which parts are semi-transparent` — Asset prompts say which areas are empty, which are translucent and which stay opaque. Set Background to transparent as well.
- **Edit one thing, list what stays** · `Change X + keep A, B, C exactly` — Edit prompts name the single change and then list what must not move, which is how Seedream 5.5 keeps untouched pixels the same across rounds.

**What the examples show**

- **Short prompts work for snapshots.** One line such as "phone snapshot, ultra-real, a Beijing hutong, snowing" produced believable street photos with no camera settings.
- **Chinese text holds at small sizes.** The butterfly infographic, the storyboard and the meme grid render dense Chinese labels; check them letter by letter before print.
- **Grids keep one character consistent.** Turnaround sheets, six-panel storyboards and 3×3 meme sheets ask for the same face, outfit and light in every cell.
- **A reference image sets the style.** The yarn lettering and owl crops take texture and composition from an uploaded image; upload your own when a card is marked as needing one.

<a id="menu"></a>
## 📑 Menu

- [• Photography](#photography) (19)
  - [White cat in a night bar, flash and Provia film](#photography-01)
  - [Father napping with his baby in window light](#photography-02)
  - [Lemon wall and purple door on a southern European corner](#photography-03)
  - [Windswept woman in a frame tilted 25 degrees](#photography-04)
  - [Older diners in a European bistro on a summer evening](#photography-05)
  - [Golden building reflected in rain puddles](#photography-06)
  - [Commuters with motion blur on a subway platform](#photography-07)
  - [Donkey peering through a fence gap, ultra-wide](#photography-08)
  - [Water droplets spelling "seedream" above a pool](#photography-09)
  - [Low-angle rooftop chess shot with an oversized king](#photography-10)
  - [London shopfront at night with signs in three languages](#photography-11)
  - [Macro of one eye with a tear and tiny glass text](#photography-12)
  - [Old fisherman mending a net at blue hour](#photography-13)
  - [Winter editorial beside a 1990s Soviet bus](#photography-14)
  - [Over-the-shoulder glance on a subway escalator](#photography-15)
  - [Phone snapshot of a Beijing hutong in snow](#photography-16)
  - [Sanitation worker sweeping snow outside Beijing](#photography-17)
  - [Snow on the Haihe River in Tianjin](#photography-18)
  - [Daisy in a melting ice cube over 60 minutes](#photography-19)
- [• Text, posters and design](#text-design) (11)
  - [Newspaper page "The Shakespeare Chronicle"](#text-design-01)
  - [Graffiti collage poster about street printing](#text-design-02)
  - [Infographic poster "From Seed to Salad"](#text-design-03)
  - [Bilingual blue morpho butterfly infographic](#text-design-04)
  - [Magazine cover packed with small cover lines](#text-design-05)
  - [Skincare serum label mock-up with fine print](#text-design-06)
  - [Swiss-style gig poster "Night Signal"](#text-design-07)
  - [Field-guide plate of a fictional deep-sea eel](#text-design-08)
  - [Ten icon styles for a screen-recording app](#text-design-09)
  - [Short-drama cover "第13层" in a dark hallway](#text-design-10)
  - [Inflated 3D lettering "夯爆了"](#text-design-11)
- [• Transparent PNGs and edits](#transparent-assets) (12)
  - [Running girl, one transparent layer per frame](#transparent-assets-01)
  - [Two cartoon sticker sets on a transparent background](#transparent-assets-02)
  - ["Seedream 5.5" in blue yarn lettering](#transparent-assets-03)
  - [Four plush characters as separate PNGs](#transparent-assets-04)
  - [Edit: blow a pink bubblegum bubble, keep everything else](#transparent-assets-05)
  - [Christmas acrylic standee with a music-player UI](#transparent-assets-06)
  - [Stickers pulled from two photos onto one transparent sheet](#transparent-assets-07)
  - [Glass jellyfish lamp with partial transparency](#transparent-assets-08)
  - [Amber perfume bottle as a transparent asset](#transparent-assets-09)
  - [Full-body streetwear cut-out](#transparent-assets-10)
  - [Hand holding a frosted acrylic sheet](#transparent-assets-11)
  - [Chrome ribbon logo shape for overlays](#transparent-assets-12)
- [• Illustration and characters](#illustration-characters) (9)
  - [Gouache picture book: a cloud-sea glider workshop](#illustration-characters-01)
  - ["Berry Club" blueberry character board](#illustration-characters-02)
  - [Paper-quilling dancer with a rainbow umbrella](#illustration-characters-03)
  - [Turnaround sheet of a young physician in hanfu](#illustration-characters-04)
  - [Anime character card with a color palette](#illustration-characters-05)
  - [Six-panel storyboard with shot sizes](#illustration-characters-06)
  - [Village at dusk, outside and inside, in one diptych](#illustration-characters-07)
  - [3×3 meme sheet of a whale-tail girl](#illustration-characters-08)
  - [Felt plush figure of a whale-tail girl](#illustration-characters-09)
- [❓ FAQ](#faq)
- [🔗 Related](#related)

<a id="photography"></a>
## • Photography

> Street, documentary, portrait and phone-snapshot prompts that test light, skin and materials. · 19 cases

<a id="photography-01"></a>
### 1. White cat in a night bar, flash and Provia film

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-01#photography-01)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-01#photography-01"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-01.webp" width="480" alt="White cat in a night bar, flash and Provia film – Seedream 5.5"></a>

**Prompt:**

```text
A white cat sits elegantly among bottles and glasses in a bar at night. Shoot from a low angle with a tilted composition, using flash, Fujifilm Provia colors and film grain. Capture dappled light, bright highlights and crisp detail for a vintage photographic feel.
```

<a id="photography-02"></a>
### 2. Father napping with his baby in window light

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-02#photography-02)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-02#photography-02"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-02.webp" width="480" alt="Father napping with his baby in window light – Seedream 5.5"></a>

**Prompt:**

```text
A warm documentary photograph of a young father reclining on a dark purple-gray fabric sofa, holding a sleeping baby. Cream knitted cushions and a mustard-yellow blanket show soft, tactile fabric textures. Warm golden daylight enters through a window on the right. Relaxed poses, natural skin tones, gentle shadows and film grain capture a quiet, intimate afternoon.
```

<a id="photography-03"></a>
### 3. Lemon wall and purple door on a southern European corner

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-03#photography-03)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-03#photography-03"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-03.webp" width="320" alt="Lemon wall and purple door on a southern European corner – Seedream 5.5"></a>

**Prompt:**

```text
A vertical 3:4 street photograph of a southern European corner. A lemon-yellow limewashed wall, an old deep-purple wooden door and hanging royal-purple linen form a bold geometric composition. Golden flowers fill a weathered metal bucket at the lower right. Strong afternoon sunlight casts crisp shadows, revealing textured plaster, fabric folds, rust and layered petals in vivid complementary purple and yellow.
```

<a id="photography-04"></a>
### 4. Windswept woman in a frame tilted 25 degrees

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-04#photography-04)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-04#photography-04"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-04.webp" width="480" alt="Windswept woman in a frame tilted 25 degrees – Seedream 5.5"></a>

**Prompt:**

```text
A candid horizontal street photograph of a long-haired woman in a burgundy top and light brown jacket looking down at her phone. Strong wind sweeps her hair across her sunglasses and face. The entire frame tilts about 25 degrees clockwise, with consistent perspective across the figure, buildings, lamppost and pavement. Natural clothing folds, hurried framing and asymmetric cropping create an unposed everyday moment.
```

<a id="photography-05"></a>
### 5. Older diners in a European bistro on a summer evening

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-05#photography-05)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-05#photography-05"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-05.webp" width="480" alt="Older diners in a European bistro on a summer evening – Seedream 5.5"></a>

**Prompt:**

```text
A candid horizontal snapshot inside a neighborhood bistro in Europe on a summer evening. Two older diners eat naturally at a table covered with cream linen, unaware of the camera. Glasses, cutlery, breadcrumbs and worn wooden furniture show everyday use. Warm pendant lights mix with traces of cool evening light. Slight underexposure, subtle high-ISO grain and foreground occlusion create an intimate, spontaneous atmosphere.
```

<a id="photography-06"></a>
### 6. Golden building reflected in rain puddles

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-06#photography-06)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-06#photography-06"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-06.webp" width="320" alt="Golden building reflected in rain puddles – Seedream 5.5"></a>

**Prompt:**

```text
A vertical 3:4 street photograph after rain, taken from a low angle looking down at wet paving stones and irregular puddles. Reflections of an old building’s golden carvings, window frames and colonnades are fragmented by exposed stones, puddle edges and ripples. Warm golden light contrasts with deep-blue reflections, preserving worn joints and wet surface textures. No full building, people or vehicles appear.
```

<a id="photography-07"></a>
### 7. Commuters with motion blur on a subway platform

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-07#photography-07)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-07#photography-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-07.webp" width="480" alt="Commuters with motion blur on a subway platform – Seedream 5.5"></a>

**Prompt:**

```text
Photograph a busy modern city subway platform filled with Asian commuters walking briskly in orderly flows. Use central perspective, with the platform, yellow safety lines and overhead lights receding into the distance. Combine motion blur, soft diffuse light and a subtle glow while retaining highlight and shadow detail to convey the energy of urban life.
```

<a id="photography-08"></a>
### 8. Donkey peering through a fence gap, ultra-wide

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-08#photography-08)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-08#photography-08"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-08.webp" width="480" alt="Donkey peering through a fence gap, ultra-wide – Seedream 5.5"></a>

**Prompt:**

```text
A horizontal ultra-wide-angle photograph of a curious gray-brown donkey peering through a vertical gap in a weathered wooden fence. Its broad muzzle nearly touches the lens, while its eyes and long ears recede in exaggerated close-up perspective. Focus on the muzzle’s fine hair, whiskers and skin texture, with softly blurred fence boards, blue sky and grass beyond. Natural daylight creates a playful candid moment.
```

<a id="photography-09"></a>
### 9. Water droplets spelling "seedream" above a pool

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-09#photography-09)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-09#photography-09"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-09.webp" width="320" alt="Water droplets spelling &quot;seedream&quot; above a pool – Seedream 5.5"></a>

**Prompt:**

```text
A hand lifts a string of water droplets from a miniature swimming pool. The droplets spell “seedream” vertically. Surreal summer photography with vivid colors and a film-like texture.
```

<a id="photography-10"></a>
### 10. Low-angle rooftop chess shot with an oversized king

by [@MayorKingAI](https://x.com/MayorKingAI) · 4:5 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-10#photography-10)** · [Original post](https://x.com/MayorKingAI/status/2120198834508955990)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-10#photography-10"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-10.webp" width="320" alt="Low-angle rooftop chess shot with an oversized king – Seedream 5.5"></a>

**Prompt:**

```text
An ultra-realistic high-fashion editorial photograph of a striking 28-year-old Japanese man with sharp facial features, a defined jawline, slightly messy medium-length black hair and narrow rectangular black sunglasses, sitting confidently on a rooftop terrace while playing chess.

He wears an oversized luxurious emerald-green faux-fur coat over a black silk shirt, tailored black trousers and a subtle silver chain necklace. His expression is calm, confident and slightly intimidating, looking directly toward the camera.

Camera composition: An extreme low-angle shot taken from the very edge of a chessboard, with the camera positioned only a few centimeters above the board's surface. The black-and-white chessboard dominates the entire bottom third of the frame, its squares appearing exceptionally large in the foreground and rapidly shrinking toward the seated man.

The man is centered in the composition, visible from approximately the knees upward, leaning slightly forward. His right arm extends directly toward the camera, with his hand dramatically enlarged by perspective. He is gripping the top of a polished ivory wooden king chess piece between his thumb and index finger, moving it toward an empty square near the camera. The king is dramatically oversized in the immediate foreground due to the wide-angle perspective, while the remaining chess pieces appear progressively smaller toward the background.

His other hand rests naturally near his knee. The chess pieces are physically accurate and positioned naturally on the board, with realistic contact shadows and detailed polished wooden surfaces.

Environment: An open urban rooftop with subtle concrete architectural details, low surrounding rooftops and an enormous vivid cyan-blue sky with a few soft, scattered white clouds. The bright sky occupies the upper half of the composition, creating strong visual contrast against the emerald-green coat.

Photography: Shot on a Sony A1 II with a 20mm wide-angle lens, camera placed at chessboard level, f/8, ISO 100, 1/1000s. Deep environmental perspective, exaggerated foreground scale, realistic optical distortion, crisp textures across the chessboard and subject. Bright natural midday sunlight, accurate skin tones, natural facial asymmetry, individual hair strands, detailed fabric and fur fibers, subtle imperfections and physically realistic shadows.

Authentic luxury fashion campaign photography, bold editorial framing, natural photographic color grading, exceptionally realistic skin texture, no artificial skin smoothing, no CGI appearance, no illustration, no plastic textures, no excessive cinematic effects.
```

<a id="photography-11"></a>
### 11. London shopfront at night with signs in three languages

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-11#photography-11)** · [Original post](https://x.com/Dheepanratnam/status/2119767938173387065)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-11#photography-11"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-11.webp" width="480" alt="London shopfront at night with signs in three languages – Seedream 5.5"></a>

**Prompt:**

```text
Photorealistic street scene in a multicultural London neighbourhood at night. A shopfront sign reads exactly “OPEN LATE” in English, with a smaller hanging sign reading exactly “欢迎光临” in simplified Chinese and another small poster reading exactly “Bienvenue” in French. Realistic neon glow, legible typography, correct character shapes, no duplicated letters, no warped glyphs, natural perspective on the signs, cinematic night photography, wet pavement reflections, no extra invented text.
```

<a id="photography-12"></a>
### 12. Macro of one eye with a tear and tiny glass text

by [@Yuziyyaa](https://x.com/Yuziyyaa) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-12#photography-12)** · [Original post](https://x.com/Yuziyyaa/status/2119799602580955179)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-12#photography-12"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-12.webp" width="480" alt="Macro of one eye with a tear and tiny glass text – Seedream 5.5"></a>

**Prompt:**

```text
电影感极致特写，年轻女性的一只眼睛占据画面中心，下眼睑挂着一颗即将落下的泪珠，泪珠有真实折射、内部高光和边缘表面张力。虹膜呈深棕色纤维纹理，瞳孔因光线略微放大，睫毛湿润粘连且根根可辨。几缕深色湿润发丝从上方垂落横过眼睛，发丝边缘被逆光打透呈金边，每根有独立厚度与细微毛躁。皮肤可见毛孔、绒毛与自然油光差异。画面右下角有一小片透明玻璃片，玻璃上印有清晰小字“Seedream 5.5”和中文“百轮测试”，字体无崩坏。光线为戏剧性侧光+冷暖对比（面部偏暖，阴影偏冷蓝），泪珠与玻璃同时反射高光。85mm微距，浅景深，背景深蓝黑色调，超写实摄影，皮肤与液体有真实物理质感，无CG感。
```

<a id="photography-13"></a>
### 13. Old fisherman mending a net at blue hour

by [@ahmetmertugrul](https://x.com/ahmetmertugrul) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-13#photography-13)** · [Original post](https://x.com/ahmetmertugrul/status/2119922071916757233)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-13#photography-13"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-13.webp" width="480" alt="Old fisherman mending a net at blue hour – Seedream 5.5"></a>

**Prompt:**

```text
Candid documentary photo, 85mm lens, f/2. An elderly fisherman in his seventies mending a tangled orange net on a wooden dock at blue hour. Mixed lighting: cold blue ambient sky from the left, a single warm sodium-vapor streetlamp from behind creating a rim light on his white stubble and the loose net fibers. Visible pores, deep wrinkles, sun spots, slightly chapped lips, a small healed scar on his knuckle. Wet wooden planks with puddles reflecting the lamp. Light drizzle visible only in the backlight. No beauty retouching, natural film grain, slight underexposure in the shadows.
```

<a id="photography-14"></a>
### 14. Winter editorial beside a 1990s Soviet bus

by [@ZaraIrahh](https://x.com/ZaraIrahh) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-14#photography-14)** · [Original post](https://x.com/ZaraIrahh/status/2120161811571912709)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-14#photography-14"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-14.webp" width="320" alt="Winter editorial beside a 1990s Soviet bus – Seedream 5.5"></a>

**Prompt:**

```text
Photorealistic fashion editorial with the atmosphere of a winter morning in the early 1990s, in a Soviet-era residential neighborhood. A beautiful adult brunette woman with delicate facial features stands beside the open folding doors of an aged cream-and-red Soviet LiAZ-677 city bus. She holds a small bouquet of dried wildflowers wrapped in vintage brown kraft paper, gently gripping it with both hands in front of her thighs.

She wears an oversized charcoal wool coat, a soft ivory knitted scarf, a dark burgundy ribbed sweater, straight dark trousers and black leather winter boots. Loose dark brown hair falls naturally around her face, a few strands lifted by the freezing wind. Flushed cheeks, minimal makeup, thoughtful expression, looking slightly past the camera, shoulders gently raised against the cold.

Snow-covered pavement, compacted gray snow beside the bus wheels, frosted windows with condensation, faded red paint, weathered metal. Blurred Soviet apartment blocks and a modest bus shelter in the distance. Fine snowflakes in the air, visible breath. The delicate dried flowers add a subtle warm color accent against the muted winter surroundings.

Three-quarter portrait framed from the knees up, eye-level camera, woman placed off-center, the bus filling one side of the composition. Cold overcast daylight with direct on-camera flash, crisp face, deep background, subtle analog film grain, restrained colors, candid 1990s street photography combined with luxury fashion editorial. Real skin texture, tactile wool, believable hands and bouquet construction, shot on a 50mm lens --ar 3:4 --style raw --s 150 --no modern cars smartphones logos text watermark
```

<a id="photography-15"></a>
### 15. Over-the-shoulder glance on a subway escalator

by [@johnAGI168](https://x.com/johnAGI168) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-15#photography-15)** · [Original post](https://x.com/johnAGI168/status/2120363733713039575)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-15#photography-15"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-15.webp" width="320" alt="Over-the-shoulder glance on a subway escalator – Seedream 5.5"></a>

**Prompt:**

```text
A cinematic vertical 35mm photograph captured at eye level — an evocative over-the-shoulder medium portrait of a stunning young East Asian woman looking back toward the camera while riding a dimly lit subway escalator.

She possesses delicate, melancholic beauty with expressive dark eyes and natural lips, casting an enigmatic glance over her shoulder. Her long, layered jet-black hair blows freely in the underground draft, with loose strands sweeping across her cheeks and face with realistic kinetic motion. She wears a minimalist black spaghetti-strap slip top that reveals elegant collarbones and bare shoulders.

The setting is a vintage metro tunnel with escalator railings receding into deep perspective. Overhead linear fluorescent lights glow with a soft amber-green halation bloom, while the distant terminal melts into colorful circular bokeh of red, cyan, and warm white, creating a moody, nostalgic urban atmosphere reminiscent of 90s cinema.

Shot on a fast 50mm vintage prime at f/1.4 with soft diffusion filtration and authentic 35mm film grain in an M1 cinematic narrative register. Genuine human skin with fine pores, biological warmth, realistic wind dynamics on hair, and rich color-negative film roll-off — cinematic frame, strictly no CGI, no 3D render, no plastic skin, no artificial smoothing.
```

<a id="photography-16"></a>
### 16. Phone snapshot of a Beijing hutong in snow

by [@vista8](https://x.com/vista8) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-16#photography-16)** · [Original post](https://x.com/vista8/status/2120085580264714732)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-16#photography-16"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-16.webp" width="480" alt="Phone snapshot of a Beijing hutong in snow – Seedream 5.5"></a>

**Prompt:**

```text
手机随手拍，超真实，北京一个胡同，下雪了
```

<a id="photography-17"></a>
### 17. Sanitation worker sweeping snow outside Beijing

by [@vista8](https://x.com/vista8) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-17#photography-17)** · [Original post](https://x.com/vista8/status/2120085580264714732)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-17#photography-17"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-17.webp" width="480" alt="Sanitation worker sweeping snow outside Beijing – Seedream 5.5"></a>

**Prompt:**

```text
手机随手拍，北京五环外，环卫工人在扫雪，超真实
```

<a id="photography-18"></a>
### 18. Snow on the Haihe River in Tianjin

by [@vista8](https://x.com/vista8) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-18#photography-18)** · [Original post](https://x.com/vista8/status/2120085580264714732)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-18#photography-18"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-18.webp" width="480" alt="Snow on the Haihe River in Tianjin – Seedream 5.5"></a>

**Prompt:**

```text
手机随手拍，超真实，天津海河边，下雪了
```

<a id="photography-19"></a>
### 19. Daisy in a melting ice cube over 60 minutes

by [@oran_ge](https://x.com/oran_ge) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-19#photography-19)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=photography-19#photography-19"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/photography-19.webp" width="480" alt="Daisy in a melting ice cube over 60 minutes – Seedream 5.5"></a>

**Prompt:**

```text
2×3 六格，同一机位。一块方冰里冻着一朵小雏菊，放在白瓷盘上，背景深灰蓝。六格依次是 0、5、10、20、40、60 分钟：冰从完整方块，到边缘化开、体积变薄，最后只剩一摊水，雏菊一直在原来的位置。每格底部标分钟数。冷调柔光，冰要通透，能看见花被冻在里面的折射。
```

<a id="text-design"></a>
## • Text, posters and design

> Newspapers, infographics, covers, labels and icons where the words have to come out right. · 11 cases

<a id="text-design-01"></a>
### 20. Newspaper page "The Shakespeare Chronicle"

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-01#text-design-01)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-01#text-design-01"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-01.webp" width="480" alt="Newspaper page &quot;The Shakespeare Chronicle&quot; – Seedream 5.5"></a>

**Prompt:**

```text
Design a landscape literary newspaper with the masthead “THE SHAKESPEARE CHRONICLE” and the headline “WILLIAM SHAKESPEARE”. On warm ivory paper, illustrate Shakespeare and the Globe Theatre in black engraving, with muted blue clouds and waves weaving through the page. Arrange seven short articles in English around the illustrations, using bold serif headings and legible small type.
```

<a id="text-design-02"></a>
### 21. Graffiti collage poster about street printing

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-02#text-design-02)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-02#text-design-02"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-02.webp" width="320" alt="Graffiti collage poster about street printing – Seedream 5.5"></a>

**Prompt:**

```text
Create a graffiti collage poster about collaborative street printing, using lime green, aubergine purple and mint over a gray-white photocopied paper texture. Oversized “PRINT PLAY!” lettering overlaps diagonally. A grayscale printmaker at the upper right holds a roller and print sample, with printing tools and handwritten phrases including “MAKE A MARK” and “PASS IT ON” below. Preserve matte halftone ink, fine grain and legible lettering in a layered, asymmetric composition.
```

<a id="text-design-03"></a>
### 22. Infographic poster "From Seed to Salad"

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-03#text-design-03)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-03#text-design-03"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-03.webp" width="320" alt="Infographic poster &quot;From Seed to Salad&quot; – Seedream 5.5"></a>

**Prompt:**

```text
Create an illustrated infographic poster titled “FROM SEED TO SALAD” on warm-white paper with a handmade print texture. One continuous path snakes across three tiers, linking six numbered stages in order: SOW, SPROUT, GROW, TEND, HARVEST and SHARE. Five correctly directed arrows connect the sequence. Pair miniature gardening scenes and English descriptions with each stage, keeping the reading order clear, lettering legible and colors soft yet varied.
```

<a id="text-design-04"></a>
### 23. Bilingual blue morpho butterfly infographic

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-04#text-design-04)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-04#text-design-04"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-04.webp" width="480" alt="Bilingual blue morpho butterfly infographic – Seedream 5.5"></a>

**Prompt:**

```text
A horizontal natural-history infographic titled “蓝闪蝶：一只蝴蝶的微观宇宙”, with the English heading “BLUE MORPHO・A CLOSER LOOK”. A large blue morpho spreads its wings against a black background, surrounded by eight macro-detail modules: antennae, structural color, wing margin, proboscis, compound eye, ventral wing, wing venation and wing scales. Pair Chinese explanations with English terms and observation notes. Preserve legible small text and fine wing textures, with a footer stating that enlarged details are illustrative and not to scale.
```

<a id="text-design-05"></a>
### 24. Magazine cover packed with small cover lines

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-05#text-design-05)** · [Original post](https://x.com/Dheepanratnam/status/2119767938173387065)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-05#text-design-05"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-05.webp" width="480" alt="Magazine cover packed with small cover lines – Seedream 5.5"></a>

**Prompt:**

```text
Premium magazine cover design titled “THE FUTURE OF CREATIVE TOOLS”, with a realistic portrait of a stylish creative director in the lower third. Dense small cover lines around the edges: “Issue 24”, “AI Workflows”, “Design Systems”, “Cinematic Image Making”, “Inside the Studio”, “November 2026”. Clean modern serif masthead, precise kerning, crisp letterforms, editorial grid, muted cream background, subtle paper texture, high-end print-design layout. All text must be spelled exactly as written, no distorted letters, no duplicated words, no gibberish.
```

<a id="text-design-06"></a>
### 25. Skincare serum label mock-up with fine print

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-06#text-design-06)** · [Original post](https://x.com/Dheepanratnam/status/2119767938173387065)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-06#text-design-06"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-06.webp" width="480" alt="Skincare serum label mock-up with fine print – Seedream 5.5"></a>

**Prompt:**

```text
Minimalist skincare packaging mock-up on a pale stone pedestal. A frosted-glass serum bottle has a clean label reading exactly “LUMEN — BARRIER REPAIR SERUM”, with smaller text beneath: “30 ml / 1.0 fl oz”. Elegant sans-serif typography, perfectly straight label alignment, crisp small print, realistic glass refraction, soft studio lighting, subtle shadow, premium cosmetic advertising photography, no misspelled words, no extra branding, no watermark.
```

<a id="text-design-07"></a>
### 26. Swiss-style gig poster "Night Signal"

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-07#text-design-07)** · [Original post](https://x.com/Dheepanratnam/status/2119767938173387065)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-07#text-design-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-07.webp" width="480" alt="Swiss-style gig poster &quot;Night Signal&quot; – Seedream 5.5"></a>

**Prompt:**

```text
Bold gig poster for an underground electronic music night. Large headline reads exactly “NIGHT SIGNAL”, with supporting text: “Friday 27 November”, “Warehouse 9, London”, “Doors 10PM”. Experimental Swiss-style layout, high-contrast black, off-white and electric blue, grainy risograph texture, sharp geometric typography, intentional negative space, screen-print aesthetic. All words spelled exactly as specified, no extra text, no warped letters, no AI artefacts.
```

<a id="text-design-08"></a>
### 27. Field-guide plate of a fictional deep-sea eel

by [@ahmetmertugrul](https://x.com/ahmetmertugrul) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-08#text-design-08)** · [Original post](https://x.com/ahmetmertugrul/status/2119915956365369596)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-08#text-design-08"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-08.webp" width="480" alt="Field-guide plate of a fictional deep-sea eel – Seedream 5.5"></a>

**Prompt:**

```text
A vintage naturalist field-guide page, aged cream paper with foxing stains, documenting a fictional deep-sea creature called "Lanternfin Abyssal Eel". Center: a detailed scientific ink-and-watercolor illustration of the eel with bioluminescent spots. Surrounding it, 10 numbered callout labels with thin leader lines, each with a 2-line caption in small serif type (e.g. "3. Photophore cluster — emits pulses at 490 nm to lure prey"). Top header in ornate engraved capitals: "PLATE XLVII — CREATURES OF THE MIDNIGHT ZONE". Bottom: a small data table with columns "Depth", "Length", "Lifespan", "Diet" and three rows of values, plus a tiny scale bar reading "10 cm". Flat top-down scan, every word sharp and legible.
```

<a id="text-design-09"></a>
### 28. Ten icon styles for a screen-recording app

by [@vista8](https://x.com/vista8) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-09#text-design-09)** · [Original post](https://x.com/vista8/status/2120085580264714732)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-09#text-design-09"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-09.webp" width="480" alt="Ten icon styles for a screen-recording app – Seedream 5.5"></a>

**Prompt:**

```text
为一款名叫 Capwise 的录屏软件设计 10 种不同风格的 icon，扁平风格，顶级水平
```

<a id="text-design-10"></a>
### 29. Short-drama cover "第13层" in a dark hallway

by [@oran_ge](https://x.com/oran_ge) · 9:16 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-10#text-design-10)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-10#text-design-10"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-10.webp" width="320" alt="Short-drama cover &quot;第13层&quot; in a dark hallway – Seedream 5.5"></a>

**Prompt:**

```text
9:16 竖屏短剧封面。昏暗老楼走廊，尽头一扇半开的电梯门，门上红色 LED 楼层数字「13」是最亮的东西。三行字：顶部标题「第13层」，中部副题「短剧 · 全集上线」，底部一行「别按那个键」。红色数字要跳、字要清楚，三行字居中对称，不许压到人脸。冷绿灰调，走廊纵深要能看出景深，只有电梯里透出一点红光。
```

<a id="text-design-11"></a>
### 30. Inflated 3D lettering "夯爆了"

by [@oran_ge](https://x.com/oran_ge) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-11#text-design-11)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=text-design-11#text-design-11"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/text-design-11.webp" width="320" alt="Inflated 3D lettering &quot;夯爆了&quot; – Seedream 5.5"></a>

**Prompt:**

```text
三个膨胀立体大字「夯爆了」，糖果色塑料气球质感，字要撑满画面，字与字之间互相挤压、有前后遮挡，边缘高光通透。浅粉橘色背景，几颗小星星和一团小烟做点缀。字体卡通、笔画圆胖。
```

<a id="transparent-assets"></a>
## • Transparent PNGs and edits

> Native RGBA output: stickers, product cut-outs, semi-transparent glass, plus edits that keep the rest of the image. · 12 cases

<a id="transparent-assets-01"></a>
### 31. Running girl, one transparent layer per frame

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-01#transparent-assets-01)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-01#transparent-assets-01"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-01.webp" width="320" alt="Running girl, one transparent layer per frame – Seedream 5.5"></a>

**Prompt:**

```text
Generate a sequence of images showing a girl running to the right, each on a separate layer with a transparent background.
```

<a id="transparent-assets-02"></a>
### 32. Two cartoon sticker sets on a transparent background

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 9:16 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-02#transparent-assets-02)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-02#transparent-assets-02"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-02.webp" width="320" alt="Two cartoon sticker sets on a transparent background – Seedream 5.5"></a>

**Prompt:**

```text
Generate two sets of cartoon stickers: one featuring ocean elements and cartoon cats, and the other featuring animals and plants. Keep the background transparent outside the sticker elements in both sets.
```

<a id="transparent-assets-03"></a>
### 33. "Seedream 5.5" in blue yarn lettering

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-03#transparent-assets-03)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-03#transparent-assets-03"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-03.webp" width="480" alt="&quot;Seedream 5.5&quot; in blue yarn lettering – Seedream 5.5"></a>

> 📎 Upload your own reference image for this one.

**Prompt:**

```text
Create “Seedream 5.5” inspired by the reference texture and style. Use rounded, bold sans-serif letters wrapped in alternating royal-blue and lake-blue yarn, with visible fibers, fuzz and side shadows. Use a 16:9 landscape format with a transparent background outside the lettering.
```

<a id="transparent-assets-04"></a>
### 34. Four plush characters as separate PNGs

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-04#transparent-assets-04)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-04#transparent-assets-04"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-04.webp" width="480" alt="Four plush characters as separate PNGs – Seedream 5.5"></a>

**Prompt:**

```text
Create a playful blue plush 3D cartoon character with a rounded body, big eyes and short limbs. Add three characters in the same style with distinct shapes and expressions. Output each character as a separate image with a transparent background, so the four characters can be separated and combined like puzzle pieces.
```

<a id="transparent-assets-05"></a>
### 35. Edit: blow a pink bubblegum bubble, keep everything else

by [@BytePlus ModelArk](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-05#transparent-assets-05)** · [Original post](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5#multi-turn-editing-consistency)

<table>
<tr><td align="center"><a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-05#transparent-assets-05"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-05.webp" width="260" alt="Edit: blow a pink bubblegum bubble, keep everything else – Seedream 5.5 1"></a></td><td align="center"><a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-05#transparent-assets-05"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-05-2.webp" width="260" alt="Edit: blow a pink bubblegum bubble, keep everything else – Seedream 5.5 2"></a></td></tr>
</table>

> 📎 Upload your own reference image for this one.

**Prompt:**

```text
Have the person blow a round, semi-transparent pink bubblegum bubble. Preserve the identity, facial features, gaze, hairstyle, pearl earrings, clothing, pose, blue background, composition, and visual style of the person.
```

<a id="transparent-assets-06"></a>
### 36. Christmas acrylic standee with a music-player UI

by [@BytePlus ModelArk](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-06#transparent-assets-06)** · [Original post](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5#transparent-background)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-06#transparent-assets-06"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-06.webp" width="320" alt="Christmas acrylic standee with a music-player UI – Seedream 5.5"></a>

**Prompt:**

```text
A transparent acrylic standee with a Christmas theme, a rectangular outline, and a thin white edge on all sides that brings out the transparent material. Use a scrapbook collage style: place a red-and-green two-tone vinyl record with a golden rim at the center, surrounded by a dimensional Christmas wreath of acorn leaves and pine branches. Decorate the wreath with hand-drawn red berries, golden four-pointed stars, reindeer, and snowflake stickers. Overlay a minimalist white music-player UI below, with play/pause controls, a progress bar (01:24 / 04:32), and a volume icon. Use vintage red, forest green, champagne gold, and off-white. Add occasional highlights refracted by the acrylic thickness for a realistic product finish. Set a transparent background.
```

<a id="transparent-assets-07"></a>
### 37. Stickers pulled from two photos onto one transparent sheet

by [@BytePlus ModelArk](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5) · 3:2 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-07#transparent-assets-07)** · [Original post](https://docs.byteplus.com/en/docs/ModelArk/seedream-5-5#transparent-background)

<table>
<tr><td align="center"><a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-07#transparent-assets-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-07.webp" width="190" alt="Stickers pulled from two photos onto one transparent sheet – Seedream 5.5 1"></a></td><td align="center"><a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-07#transparent-assets-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-07-2.webp" width="190" alt="Stickers pulled from two photos onto one transparent sheet – Seedream 5.5 2"></a></td><td align="center"><a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-07#transparent-assets-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-07-3.webp" width="190" alt="Stickers pulled from two photos onto one transparent sheet – Seedream 5.5 3"></a></td></tr>
</table>

> 📎 Upload your own reference image for this one.

**Prompt:**

```text
Extract the sticker elements from Image 1 and Image 2 separately, then place all extracted stickers in one transparent-background image. Preserve each sticker's original text, colors, shapes, and details; remove all background content other than the stickers. Arrange the stickers separately without overlap, with sharp and intact edges.
```

<a id="transparent-assets-08"></a>
### 38. Glass jellyfish lamp with partial transparency

by [@ahmetmertugrul](https://x.com/ahmetmertugrul) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-08#transparent-assets-08)** · [Original post](https://x.com/ahmetmertugrul/status/2119920477535719739)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-08#transparent-assets-08"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-08.webp" width="480" alt="Glass jellyfish lamp with partial transparency – Seedream 5.5"></a>

**Prompt:**

```text
Transparent background, PNG with alpha channel. A hand-blown glass jellyfish lamp floating in mid-air: semi-transparent frosted bell with visible internal air bubbles, long trailing tentacles made of thin glass threads that fade from fully opaque at the top to almost invisible at the tips, a faint warm amber glow inside the bell, soft caustic refractions, wisps of translucent steam drifting from the tentacle ends. No background, no ground shadow, clean anti-aliased edges, studio product lighting.
```

<a id="transparent-assets-09"></a>
### 39. Amber perfume bottle as a transparent asset

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-09#transparent-assets-09)** · [Original post](https://x.com/Dheepanratnam/status/2119775195573481859)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-09#transparent-assets-09"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-09.webp" width="480" alt="Amber perfume bottle as a transparent asset – Seedream 5.5"></a>

**Prompt:**

```text
Studio product asset of a translucent amber glass perfume bottle with a brushed-gold cap, floating centred in the frame. Fully transparent background with native alpha channel, clean accurate edges around the glass, cap and reflections, no background colour bleed, no white halo, no cut-off shadows. Preserve realistic glass refraction and internal liquid. Commercial e-commerce asset, front-facing composition, high detail, suitable for direct placement onto any design background.
```

<a id="transparent-assets-10"></a>
### 40. Full-body streetwear cut-out

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-10#transparent-assets-10)** · [Original post](https://x.com/Dheepanratnam/status/2119775195573481859)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-10#transparent-assets-10"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-10.webp" width="320" alt="Full-body streetwear cut-out – Seedream 5.5"></a>

**Prompt:**

```text
Full-body cut-out asset of a stylish young Black male streetwear model wearing an oversized charcoal puffer jacket, baggy denim jeans and white trainers, walking casually. Fully transparent background with native alpha channel, precise edges around curly hair, jacket fibres, shoelaces and fingers, no background remnants, no halo, no clipped limbs. Natural stance, studio-quality lighting from front left, suitable for compositing into a fashion campaign.
```

<a id="transparent-assets-11"></a>
### 41. Hand holding a frosted acrylic sheet

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-11#transparent-assets-11)** · [Original post](https://x.com/Dheepanratnam/status/2119775195573481859)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-11#transparent-assets-11"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-11.webp" width="480" alt="Hand holding a frosted acrylic sheet – Seedream 5.5"></a>

**Prompt:**

```text
PNG asset of a hand holding a clear acrylic sheet with a subtle frosted edge, photographed straight on. The acrylic sheet must have realistic partial transparency, visible refraction and a soft translucent gradient, while the hand and fingers remain fully opaque. Native alpha channel, clean anti-aliased edges, no background, no colour contamination, no harsh cut-out edges. Premium UI/design asset, centred composition.
```

<a id="transparent-assets-12"></a>
### 42. Chrome ribbon logo shape for overlays

by [@Dheepanratnam](https://x.com/Dheepanratnam) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-12#transparent-assets-12)** · [Original post](https://x.com/Dheepanratnam/status/2119775195573481859)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=transparent-assets-12#transparent-assets-12"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/transparent-assets-12.webp" width="480" alt="Chrome ribbon logo shape for overlays – Seedream 5.5"></a>

**Prompt:**

```text
Transparent PNG asset of a floating 3D chrome ribbon logo shape, elegantly twisted like liquid metal, with realistic specular highlights and soft internal reflections. Fully transparent background, native alpha channel, crisp edges around every curve, no background glow, no rectangular bounding artefacts, no drop shadow baked in. Minimal premium brand asset, centred, suitable for overlaying on video or web design.
```

<a id="illustration-characters"></a>
## • Illustration and characters

> Picture books, character sheets, storyboards, meme grids and toy designs. · 9 cases

<a id="illustration-characters-01"></a>
### 43. Gouache picture book: a cloud-sea glider workshop

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-01#illustration-characters-01)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-01#illustration-characters-01"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-01.webp" width="320" alt="Gouache picture book: a cloud-sea glider workshop – Seedream 5.5"></a>

**Prompt:**

```text
A fantasy picture-book illustration with delicate gouache textures, set in a cloud-sea glider workshop. A bear mechanic steadies the mast, a red panda pilot pulls the sail rope from inside the boat, and an otter assistant approaches in the foreground carrying a wooden securing pin. A low, upward-looking view and gently tilted perspective emphasize the bow, triangular sail and tall timber roof. Cream, deep teal and honey-colored wood create a bright, warm scene of teamwork.
```

<a id="illustration-characters-02"></a>
### 44. "Berry Club" blueberry character board

by [@ByteDance Seed](https://seed.bytedance.com/en/seedream5_5) · 3:4 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-02#illustration-characters-02)** · [Original post](https://seed.bytedance.com/en/seedream5_5)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-02#illustration-characters-02"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-02.webp" width="320" alt="&quot;Berry Club&quot; blueberry character board – Seedream 5.5"></a>

**Prompt:**

```text
Design a vertical blueberry collectible-character board with sky-blue and cream cloud-shaped sections. Use the title “BERRY CLUB” and the Chinese tagline “小小一颗，慢慢快乐”. Feature the main character “莓小蓝” alongside four themed variants: MAIL RUNNER, RAINY DAY, STAR GUARDIAN and BLUEBERRY CHEF. Below, arrange front, side and back views, five expressions and six accessories. Keep consistent character proportions, matte vinyl textures and rounded bilingual typography in a rich, orderly layout.
```

<a id="illustration-characters-03"></a>
### 45. Paper-quilling dancer with a rainbow umbrella

by [@yourPlugAI](https://x.com/yourPlugAI) · 2:3 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-03#illustration-characters-03)** · [Original post](https://x.com/yourPlugAI/status/2120176960999403776)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-03#illustration-characters-03"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-03.webp" width="320" alt="Paper-quilling dancer with a rainbow umbrella – Seedream 5.5"></a>

**Prompt:**

```text
3D paper quilling art of a graceful woman dancing in side-profile. She wears an elegant sleeveless v-neck dress made of intricately coiled paper strips in a vivid rainbow gradient—transitioning seamlessly through yellow, orange, red, magenta, deep purple, royal blue, and emerald green. 

Her long brown hair flows in the wind behind her as she gracefully holds an open quilled umbrella featuring matching rainbow paper panels overhead. She wears bright red high heels, standing atop quilled paper water ripples reflecting vibrant hues. Surrounding her in mid-air are multiple detailed quilled paper butterflies in shades of bright orange, yellow, pink, and sky blue. 

The background is a solid matte dark charcoal grey cardstock, featuring subtle overhead studio directional lighting that casts soft 3D drop shadows underneath the layered paper elements, emphasizing realistic texture and depth. High detail, paper craft sculpture aesthetic, 4k resolution. --ar 2:3
```

<a id="illustration-characters-04"></a>
### 46. Turnaround sheet of a young physician in hanfu

by [@oran_ge](https://x.com/oran_ge) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-04#illustration-characters-04)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-04#illustration-characters-04"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-04.webp" width="480" alt="Turnaround sheet of a young physician in hanfu – Seedream 5.5"></a>

**Prompt:**

```text
角色设定稿，浅灰白底，竖版。正面、四分之三侧、背面三个全身视图并排，身高比例一致，脚底在同一条线上。人物：二十二岁女医，浅青色交领短半臂加素色长裙，发髻插一支木簪。三视图下方排三个表情头：平静、微忧、含泪。最底部一行标注「沈昭 · 医女 · 二十二岁」。线稿干净、淡彩上色，旁边加一点植物线描做边饰。
```

<a id="illustration-characters-05"></a>
### 47. Anime character card with a color palette

by [@oran_ge](https://x.com/oran_ge) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-05#illustration-characters-05)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-05#illustration-characters-05"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-05.webp" width="480" alt="Anime character card with a color palette – Seedream 5.5"></a>

**Prompt:**

```text
漫剧人设卡，浅灰底，竖版。同一位角色三个视图：正面、四分之三侧、背面，白发、眼下有一颗小痣、深蓝连帽外套、校服裤。右侧竖排色卡，写上「主色 · 辅色」并给出三个色块。底部标注「林夜 · 十七岁 · 高中生」。二次元赛璐璐上色，边缘线干净，不要多余装饰。
```

<a id="illustration-characters-06"></a>
### 48. Six-panel storyboard with shot sizes

by [@oran_ge](https://x.com/oran_ge) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-06#illustration-characters-06)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-06#illustration-characters-06"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-06.webp" width="480" alt="Six-panel storyboard with shot sizes – Seedream 5.5"></a>

**Prompt:**

```text
六格分镜故事板，2 行 3 列，同一角色同一服装同一场景。每格左上角标镜号 1–6，格下一行标注景别：1 全景、2 中景、3 近景、4 特写、5 大特写、6 仰拍（低角度从下往上拍人物）。铅笔线稿风格，淡彩上色，纸面有轻微纸纹，格与格之间用细线分隔。标注文字必须是中文，不要错字。
```

<a id="illustration-characters-07"></a>
### 49. Village at dusk, outside and inside, in one diptych

by [@oran_ge](https://x.com/oran_ge) · 16:9 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-07#illustration-characters-07)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-07#illustration-characters-07"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-07.webp" width="480" alt="Village at dusk, outside and inside, in one diptych – Seedream 5.5"></a>

**Prompt:**

```text
左右两格拼成一张，同一天的同一时刻。左格：黄昏村落广角，土墙、晒谷架、远处山脊和炊烟；右格：从屋内门框向外看同一个院子，前景有一盏将熄的油灯和一把缺口柴刀。两格的光线方向、色温、时间必须一致。各带一行中文标注，左格「清河村 · 黄昏」，右格「清河村 · 屋内」。
```

<a id="illustration-characters-08"></a>
### 50. 3×3 meme sheet of a whale-tail girl

by [@oran_ge](https://x.com/oran_ge) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-08#illustration-characters-08)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-08#illustration-characters-08"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-08.webp" width="480" alt="3×3 meme sheet of a whale-tail girl – Seedream 5.5"></a>

**Prompt:**

```text
3×3 九宫格表情包，同一位少女：蓝发、鲸鱼尾巴、白色卫衣。九个格各一句中文标签，写在格中央偏下：只看一集、电子榨菜、再来一集、两倍速、砍头式剧透、真香、上头、断更了、完结撒花。每格配一件小道具（手机、泡面、遥控器、纸巾、行李箱……），九格同一画风、同一角色、同一光线。标签用黑色描边白字，必须九个字都对。格与格之间留细白缝。
```

<a id="illustration-characters-09"></a>
### 51. Felt plush figure of a whale-tail girl

by [@oran_ge](https://x.com/oran_ge) · 1:1 · **[▶ Run on APIKO](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-09#illustration-characters-09)** · [Original post](https://x.com/oran_ge/status/2120037929615503812)

<a href="https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=case&utm_campaign=awesome-seedream-5.5-prompts&utm_content=illustration-characters-09#illustration-characters-09"><img src="https://media.apiko.app/prompts/seedream-5-5-prompts/illustration-characters-09.webp" width="480" alt="Felt plush figure of a whale-tail girl – Seedream 5.5"></a>

**Prompt:**

```text
一只毛绒潮玩，鲸鱼尾少女。奶白色长绒，蓝色围裙，圆头大眼，尾巴自然卷曲。要毛毡质感：绒毛纤维一根根可见，围裙上有针脚，填充物把形体撑得圆但不僵硬。米色无缝背景，柔和棚拍光，正面站立，2:3 竖版，不要文字不要水印。
```

<a id="faq"></a>
## ❓ FAQ

<details>
<summary><b>Are all of these really Seedream 5.5 results?</b></summary>

Yes. Each card comes from ByteDance Seed’s Seedream 5.5 page, the BytePlus Seedream 5.5 docs, or a creator post or article that names Seedream 5.5 next to that image. In side-by-side tests only the image labelled Seedream 5.5 is used.

</details>

<details>
<summary><b>Can I use these prompts?</b></summary>

You can copy, edit and run any prompt. The results belong to the credited source, so check the original page or post before reusing an image.

</details>

<details>
<summary><b>How do I get a transparent PNG?</b></summary>

Describe the transparent areas in the prompt and set Background to transparent with PNG output. In the API the fields are background: "transparent" and output_format: "png".

</details>

<details>
<summary><b>Which sizes and ratios does Seedream 5.5 support?</b></summary>

Ten aspect ratios (1:1, 4:3, 3:4, 16:9, 9:16, 3:2, 2:3, 21:9, 2:1, 1:2) at 1K, 1.5K or 2K, with up to 10 reference images per request.

</details>

<details>
<summary><b>How do I call Seedream 5.5 from code?</b></summary>

Send the prompt to POST /v1/images/generations with model "seedream-5.5" and your APIKO key. The API docs list every field; the model page shows the current price.

</details>


<a id="related"></a>
## 🔗 Related

- [Seedream 5.5 Prompts · apiko.app](https://apiko.app/seedream-5-5-prompts?utm_source=github&utm_medium=related&utm_campaign=awesome-seedream-5.5-prompts)
- [Seedream 5.5](https://apiko.app/models/seedream-5.5?utm_source=github&utm_medium=related&utm_campaign=awesome-seedream-5.5-prompts)
- [Seedream 5.0 Pro](https://apiko.app/models/doubao-seedream-5-0-pro?utm_source=github&utm_medium=related&utm_campaign=awesome-seedream-5.5-prompts)
- [Nano Banana 2.1 prompts](https://apiko.app/nano-banana-2-1-prompts?utm_source=github&utm_medium=related&utm_campaign=awesome-seedream-5.5-prompts)
- [GPT Image 2.6 prompts](https://apiko.app/gpt-image-2-6-prompts?utm_source=github&utm_medium=related&utm_campaign=awesome-seedream-5.5-prompts)
- [Code examples for the APIKO API](https://github.com/tong0619453646-dev/apiko-ai-api-examples)

**More prompt collections**

- [Awesome Seedance 2.5 Prompts](https://github.com/tong0619453646-dev/awesome-seedance-2.5-prompts)
- [Awesome Seedance 2.0 Prompts](https://github.com/tong0619453646-dev/awesome-seedance-2.0-prompts)
- [Awesome Kling 4.0 Prompts](https://github.com/tong0619453646-dev/awesome-kling-4.0-prompts)
- [Awesome GPT Image 2.6 Prompts](https://github.com/tong0619453646-dev/awesome-gpt-image-2.6-prompts)
- [Awesome Nano Banana 2.1 Prompts](https://github.com/tong0619453646-dev/awesome-nano-banana-2.1-prompts)
- [Awesome GPT Image 2.5 Prompts](https://github.com/tong0619453646-dev/awesome-gpt-image-2.5-prompts)
- [Awesome GPT Image 2 Prompts](https://github.com/tong0619453646-dev/awesome-gpt-image-2-prompts)
- [Awesome Claude Opus 5.5 Video Prompts](https://github.com/tong0619453646-dev/awesome-claude-opus-5.5-video-prompts)
- [Awesome Claude Fable 5.2 Video Prompts](https://github.com/tong0619453646-dev/awesome-claude-fable-5.2-video-prompts)
- [Awesome Wan 3.0 Prompts](https://github.com/tong0619453646-dev/awesome-wan-3.0-prompts)

<a id="license"></a>
## 📄 License and credits

Prompts and results belong to the sources credited on each card: ByteDance Seed (the Seedream 5.5 model page), BytePlus ModelArk (the Seedream 5.5 docs) and creators whose own post or article names Seedream 5.5. Each card links to its source. Titles, descriptions, translations and the build scripts are released under [CC BY 4.0](LICENSE).

If this list saves you time, a ⭐ helps others find it.
