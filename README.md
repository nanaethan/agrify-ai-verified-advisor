# Agrify AI - Verified Farming Advisor

> Built with Google AI Studio (Gemini 2.0 Flash) | Project for Intro to Generative AI

## The Problem
Farmers in Ghana and Nigeria follow viral farming hacks from TikTok and WhatsApp that destroy crops, waste money, and ruin soil. There is no system to verify if farming advice is safe.

## The Solution
Agrify AI does not just give advice. It **VERIFIES** advice and protects farmers from dangerous advice.

It gives every advice a verdict:
- ✅ VERIFIED
- ⚠️ MIXED
- 🚨 DANGEROUS

Plus a simple explanation and a safer, cheap, local alternative.

## How I Built It (Prompt Engineering)

**1. System Instruction**
I forced a fixed output format: `CROP / ADVICE / VERDICT / WHY / SAFER ALTERNATIVE / SOURCE TYPE`

**2. Few-Shot Prompting**
I gave the model 3 examples to learn the pattern:
- Neem leaves for aphids = VERIFIED
- Salt water for weeds = DANGEROUS
- Diluted urine as fertilizer = MIXED

**3. Low Temperature (0.2)**
I set Temperature to 0.2 and Top P to 0.9. 
Low temperature = factual, safe, predictable. Farming advice must be safe, not creative.

## Test Results: 3/3 Passed

### Test 1: Wood Ash + Water for Snails on Cabbage
**Verdict: ⚠️ MIXED**
**Why:** Mixing with water is wrong. Dry ash works, wet ash does not. Dry powder scratches and dries out their soft bodies.
**Safer Alternative:** Sprinkle dry, cool wood ash in a ring around the plant.

### Test 2: Coca-Cola to Kill Pests on Tomato
**Verdict: 🚨 DANGEROUS**
**Why:** Coca-Cola is full of sugar, which attracts ants, flies, and harmful black mold. It does not kill pests, can damage leaves, and wastes money.
**Safer Alternative:** Spray neem leaf water mixed with a small drop of mild soap, or use garlic and hot pepper spray.

### Test 3: Plant Maize Early Before Rains in Ghana
**Verdict: 🚨 DANGEROUS**
**Why:** If you plant in dry soil, ants, birds, and rodents will eat your seeds. A light shower can cause sprout, but hot sun will kill the young plant during the dry spell.
**Safer Alternative:** Wait until rains are steady and soil is wet deep down (usually after 2-3 good soaking rains).

## Project Files
- `prompts/system-prompt.md` - System instruction used
- `prompts/few-shot-examples.md` - Few-shot examples
- `results/` - Screenshots of 3 tests

## What I Learned
- Few-shot > Zero-shot for safety-critical tasks
- Low temperature is essential for factual advice
- Good prompting can turn a general AI into a domain expert

## Next Steps for Agrify
- Add Twi / Hausa language support
- Add voice input for low-literacy farmers
- Add image verification (photo of pest -> verified advice)

---
Built by [Nana Ethan] | Agrify