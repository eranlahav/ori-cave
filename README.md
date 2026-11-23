# ori-cave — המערה של אורי

Ori's handwriting app (cursive, pen or finger). https://eranlahav.github.io/ori-cave/
Saved data: localStorage["ori.write.v1"] (same origin as ori-tablet, so it carries over).

## Adding a letter family
Everything is driven by the `FAMILIES` array at the top of the script in `index.html`.
Add one object with: `name`, `color`, mascot `sprite`/`spriteMove` (pixel maps), `order`,
`letters` (width, name, strokes in units: ceiling y=0, floor y=100, pit y=150),
`words` (practice words built only from known letters) and `pictures` (everyday word + emoji
for "בְּמָה זֶה מַתְחִיל?"). The letter practice, word practice, both games and the cave room
pick the new family up automatically. `room` picks the family's spot in the cave room:
`ceiling` (bats), `air` (butterflies), anything else = the pond (frogs). The browser console warns about config mistakes.

## Games (same for every family)
- **בְּמָה זֶה מַתְחִיל?** picture → tap the first letter (auto-checked) → write it on the board
  (path-checked from the start dot, or over a faint model if the letter was not learned yet).
- **אִיקְס עִיגּוּל** Ori vs a parent on one tablet; each picks a family letter and writes it in a cell.
  Not graded (the opponent is watching); a cell locks ~1.2s after the pen lifts; ↩️ undoes the last move.

## Families
- Bats (קְבוּצַת הָעֲטַלֵּפִים): י ו ן נ מ
- Frogs (קְבוּצַת הַצְּפַרְדְּעִים): ר ה ק ח ת ב, workbook pp.20–29
- Butterflies (קְבוּצַת הַפַּרְפָּרִים): ס כ ז ם פ צ ד ך, workbook pp.35–39. Every letter starts at the top left
  (by the butterfly's body) and goes right first. ס = the wing on p.37; ז ם פ צ ד traced from p.39;
  כ and ך only appear in the p.35 grid, so their start follows the same rule.
