# Silent E Ninja Dojo

A ninja-themed phonics game that helps 2nd graders master **long vowel silent e (VCe)** words such as *cake, bike, home, cube*.
Silent e sneaks to the end of a word without a sound, and the vowel says its name.

Created by The Vanpool School.

## Play it on GitHub Pages

1. Put `index.html` (and this README and `.nojekyll`) in the root of a GitHub repository.
2. Open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then **Save**.
4. After a minute your game is live at `https://<your-username>.github.io/<repo-name>/`.

You can also just double-click `index.html` to play offline.

## Why it works anywhere

- One self-contained file: no build step, no CDN, no fonts or scripts loaded from other sites.
- Only relative paths, so it works at a user site (`username.github.io`) or a project site (`username.github.io/repo/`).
- Progress is saved in the browser's `localStorage` under the namespaced key `vce-ninja-dojo/v1`, so it will not collide with other projects on the same `github.io` domain. No accounts, no tracking, no data leaves the device.
- Read-aloud uses the browser's built-in speech (Web Speech API). If a device has no voice, the game still works.

## How it plays

| Level | Missions | Trial |
|---|---|---|
| 1. Bamboo Grove (one-part words) | Star Toss, Silent Sneak, Scroll Seal, Dojo Tales | Green Belt Trial |
| 2. Moonlit Rooftops (two-part words) | Rooftop Run, Word Forge, Pattern Pagoda, Moonlit Tales | Black Belt Trial |

- Missed words come back until they are mastered.
- A trial needs 9 of 10 to earn the belt. Finishing Level 1's trial unlocks Level 2.
- 10 collectible badges. Word scrolls and the Sensei guide are always one tap away.
- Keyboard: press 1 to 4 to choose an answer. Reduced-motion settings are respected.

## About the words

Every target word is a typical VCe word: one vowel, one consonant, then a silent e that makes the vowel long (a_e, i_e, o_e, u_e, plus the rare e_e in *these, theme, complete, compete*). The word bank was checked by script. It excludes:

- exception words (*have, give, love, some, come, done, one, gone, move, lose*)
- r-controlled endings (*care, fire, more, pure*)
- vowel teams and words with y
- ambiguous pronunciations (*vase, close*)

It also confirms each question has exactly one correct answer and that distractors never contain a second correct long vowel.

## Editing the words

The question lists live near the top of the `<script>` in `index.html` (search for `var L1 =`, `var L2 =`, `Q1`, `Q2`). Each line uses a small helper, for example:

```js
hear('a', 'cake', ['cat', 'kite', 'cup'])     // long A word + 3 distractors
sneak('cap', 'cape', ['cap', 'cone', 'cop'])  // short word, new word, distractors
```

Keep distractors simple (no silent e unless it is a different vowel) so there is only one right answer.
