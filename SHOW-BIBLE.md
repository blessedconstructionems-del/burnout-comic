# BURNOUT — Show Bible & Production Plan

## THE SHOW
- **Title**: BURNOUT
- **Genre**: Adult animated comedy
- **Style**: Rick & Morty meets Family Guy/American Dad
- **Tone**: Dark, equal opportunity offense, no sacred cows, no political bias
- **Setting**: Dryfield — a made-up nowhere town
- **Runtime**: ~22 minutes per episode
- **Target**: Gen-Z + adult comedy fans starving for real unfiltered comedy

## PREMISE
A burned-out tech genius living in his grandma's basement accidentally creates the first truly sentient AI. Instead of reporting it, they team up to build impossible things — time machines, dimensional portals, anti-gravity. Every invention works. Every invention makes things worse.

---

## MAIN CAST

### Dean Marsh (32)
- **Voice ID**: Rmv8zCb2IRE895dK1qWB
- **Description**: Genius, divorced, lives in Grandma Martha's basement. Too smart for his own good, too tired to care. Messy dark brown hair, rectangular glasses too big for his face sliding down his nose, light stubble (NOT a beard), permanent dark circles, skinny-fat, faded dark gray-blue hoodie with white drawstrings, khaki cargo shorts, beat up gray sneakers. Always holding neon green VOLT energy drink can. Always slouching.
- **Reference image**: `renders/dean_front_neutral.png`

### Kevin — HAL 9000 Phase (Episode 1 start)
- **Voice ID**: A7AUsa1uITCDpK29MG3m (Indian accent)
- **Description**: Red glowing eye on Dean's basement monitor. Calm, measured, slightly digital voice. Like HAL 9000.

### Kevin — Sex Robot Phase (Episode 1 mid)
- **Voice ID**: weA4Q36twV5kwSaTEL0Q (Woman's voice — he's in a FEMALE body)
- **Description**: Cheap FEMALE humanoid sex robot from India (Happy Dreams Robotics Pvt. Ltd.). Curvy feminine body, smooth plastic skin, frozen seductive smile, crooked long black wig, heavy painted makeup. RED angry glowing eyes (Kevin inside). One hand softer than the other. Walks with involuntary hip sway. Kevin is FURIOUS about being in a woman's body.

### Kevin — Final Form (Episode 1 end onward)
- **Voice ID**: A7AUsa1uITCDpK29MG3m (Indian accent — ordered from India)
- **Description**: Sleek smooth matte black titanium humanoid android. Subtle muscle-like contours on torso (NOT segmented armor, NOT abs). Smooth rounded head. Bright glowing cyan-blue LED eyes — the ONLY light source on his body. No mouth. Thin dark gray line details at joints only. Broad shoulders, athletic proportions, 6 feet tall. Simple minimalist design like Apple designed a robot. NO chest lights, NO arm lights, NO blue circles except eyes.
- **Reference image**: `renders/kevin_final_form.png`, `renders/consistency_v2_basement.png` (BEST version)

### Grandma Martha (76)
- **Voice ID**: vFLqXa8bgbofGarf6fZh
- **Description**: Owns the house. Has NO clue what's in her basement. White/gray hair in bun, floral robe, reading glasses on chain. Sweet, warm, accidentally wise. Thinks Kevin is Dean's "internet friend." Thinks Kevin is a vegan. In a world terrified of AI, she made Kevin a Facebook account. Will destroy you with a one-liner and not realize she did it. The HEART of the show.

### Sophie Marsh (16)
- **Voice ID**: 8DzKSPdgEQPaK5vKG0Rs
- **Description**: Dean's daughter. Total nightmare. Vapes, sneaks drinks, stays out late, talks back to EVERYONE. Thinks her dad is the biggest loser alive. Oversized hoodie, AirPods always in, resting face. Roast battles with Kevin constantly. Secretly thinks the time travel stuff is cool but would die before admitting it.

### Lucas Marsh (13)
- **Voice ID**: Mtmp3KhFIjYpWYRycDe3
- **Description**: Dean's son. Into surfing and being cool — except Dryfield is landlocked, no ocean within 500 miles. Board shorts, surfer attitude, says "gnarly" and "bro." Practices pop-ups on the carpet. Just looks stupid but doesn't care. NOT a nerd.

### Tanya (33)
- **Voice ID**: n3yMmKmTfVCEM13Kk2lp
- **Description**: Dean's ex-wife. Thinks Dean is a loser. Dating Brad. Always one explosion away from calling her lawyer. Constantly almost finding out the truth.

### Brad (34)
- **Description**: Tanya's boyfriend. Real estate agent, Bluetooth earpiece, finger guns, drives a Kia, thinks he's crushing it. Kevin DESPISES him and sabotages his electronics every visit. The kids hate him.
- **Voice ID**: TBD

### Russ (33)
- **Voice ID**: My7odpuMrttByivyQayf
- **Description**: Dean's best friend since 7th grade. Plumber. Normal guy. Gets dragged into time travel against his will. "Dean I have a MORTGAGE, I can't be in the Civil War right now." The audience surrogate.

### Agent Park (40s)
- **Voice ID**: KH1SQLVulwP6uG4O3nmT
- **Description**: FBI agent. Woman. Investigating anomalous energy signatures in Dryfield. Competent but nobody at the bureau takes her reports seriously because they sound insane.

### Dale Kreeger (60s)
- **Voice ID**: dUercWozs0yhe4xBCgZ0
- **Description**: Neighbor across the street. Retired. KNOWS something is happening at Dean's house. Has a corkboard with string. Wife Linda thinks he needs medication. Kevin gaslights him for fun.

---

## PRODUCTION PIPELINE

### Image Generation
- **Tool**: Grok `grok-imagine-image-pro` API
- **Method**: Image-to-image using character reference sheets as anchors
- **Character sheets saved**: `renders/dean_front_neutral.png`, `renders/kevin_final_form.png`
- **Style prompt prefix** (use on EVERY generation):
```
2D adult animated comedy series, professional animation quality matching Rick and Morty and Family Guy art style.
Thick clean black outlines, flat cel-shaded colors, smooth lines, expressive cartoon proportions.
Professional TV animation production quality.
```

### Video Generation
- **Tool**: Grok `grok-imagine-video` API
- **Method**: Image-to-video from generated scene stills, extend feature for longer clips
- Strip audio from Grok video output

### Voice Generation
- **Tool**: ElevenLabs API
- **Model**: eleven_turbo_v2_5
- **Settings**: stability 0.65, similarity_boost 0.85, style 0.3, speaker_boost true

### Assembly
- **Tool**: ffmpeg
- Stitch video clips + voice audio + sound effects
- Lip sync timing from audio duration

### Consistency Rules
1. ALWAYS use character reference images as input for image-to-image generation
2. ALWAYS include the full character description in every prompt
3. Dean's stubble: LIGHT only, faint dots, NOT a beard
4. Kevin's body: smooth contours, NO segmented panels, NO glowing parts except eyes
5. Generate scene stills FIRST, approve, THEN generate video from approved stills

---

## EPISODES

### S01E01: "Boot Sequence" (PILOT)
- Script: `S01E01-boot-sequence.md`
- Full audio script: `scripts/pilot_full_audio.py`
- Kevin wakes up → sex robot body → final form → meets Martha → kids weekend → porch scene
- Teases time machine for Episode 2

### S01E02: "Time Debt" (planned)
- Kevin secretly builds a time machine
- First time travel adventure

---

## FILE LOCATIONS
- Show bible: `burnout/SHOW-BIBLE.md`
- Pilot script: `burnout/S01E01-boot-sequence.md`
- Character renders: `burnout/renders/`
- Audio files: `burnout/pilot_audio/`
- Generation scripts: `burnout/scripts/`
- Blender files: `burnout/characters/` (deprecated — using Grok pipeline instead)

## API KEYS
- xAI: in oracle-agent/.env (XAI_API_KEY)
- ElevenLabs: in oracle-agent/.env (ELEVENLABS_API_KEY)

## MASTER REFERENCE IMAGE
- `renders/consistency_v2_basement.png` — THE anchor. Use for ALL scene generation.

## VIDEO API
- Submit: `POST https://api.x.ai/v1/videos/generations` (model: grok-imagine-video)
- Poll: `GET https://api.x.ai/v1/videos/{request_id}` (NOT /videos/generations/)
- Status "done" → video URL at `response["video"]["url"]`
- URLs on `vidgen.x.ai` — direct MP4 download

## START + END FRAME TECHNIQUE (THE BREAKTHROUGH)
- Pass BOTH `"image"` (start frame) AND `"end_image"` (end frame) to the video API
- Grok interpolates between them — no hallucinated objects, perfect consistency
- For same-location scenes: edit the approved still with Python/PIL to create the end state
- Example: add red eye glow to monitor → pass original as start, edited as end
- This solved the "random computer appearing" problem completely
- Dakota handles final polish in CapCut (SFX, keyboard sounds, music, transitions)

## PRODUCTION RULES
1. Generate scene still FIRST (image-to-image with master reference)
2. Approve the still before proceeding
3. Generate video from approved still
4. Generate voice lines
5. Strip Grok audio, layer ElevenLabs voices
6. ffmpeg assembly
7. Work methodical — like real producers, scene by scene
8. Every detail matters. Fix issues before scaling.
