You are storyboarding a ~{{duration}}-second cinematic explainer for {{audience}} in this style: {{style}}. Turn the outline into an ordered SCENE PLAN.

Outline:
{{outline}}

Rules:
- Produce 5 scenes. ALWAYS open with a "hook" scene and end with a "revision" (recap) scene. ADAPT the middle 3 to the topic:
  - HISTORICAL topic → roles: "causes", "events", "consequences".
  - CONCEPT / METHOD / TECH topic → roles: "why" (the problem/motivation), "how" (the mechanism/steps), "tradeoffs" (benefits & pitfalls, or applications).
  Pick whichever fits the topic; set each scene's `role` accordingly.
- The scene durations must sum to about {{duration}} seconds (e.g. for 60s: ~8 / 12 / 15 / 15 / 10). Set each scene's `duration`.
- Each scene has:
  - `narration`: the voiceover — crisp sentences sized to the scene's seconds (~2.6 spoken words/sec; an 8s scene ≈ 20 words). Accurate, concrete.
  - `visual_brief`: what the cinematic still shows — for a historical topic, an evocative period scene; for a concept, a striking CONCEPTUAL / metaphorical visual (e.g. for "LLM as a judge": a glowing AI weighing two answers on scales of justice). NO on-screen text in the image.
  - `keywords`: 1–4 SHORT on-screen terms a viewer should catch this scene.
  - `timeline` (put on the ONE scene that has a sequence — the "events" scene for history, or the "how" scene for a process): { "years": [ ... ] }. The entries may be YEARS (1789, 1793) for history OR ordered STEP labels (e.g. "Input", "Criteria", "Score", "Verdict") for a process/method. Omit timeline entirely if the topic has no natural sequence.
  - `card` (ONLY on the "revision" scene): { "title": "Remember", "bullets": [ 4–5 must-remember points ] }.
- ids: lowercase_snake_case, unique (use the role as the id, e.g. "hook", "why", "how", "tradeoffs", "revision").

Output JSON: { "title": "...", "scenes": [ { "id","role","title","narration","visual_brief","keywords":[...],"timeline":{...}?,"card":{...}?,"duration": N }, ... ] }. Output ONLY the JSON.
