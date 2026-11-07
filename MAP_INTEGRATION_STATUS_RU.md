# Naruto Shinobi Wars — Integrated Map Beta

## Integrated files
- Active HOI4 map assets are in `map/`.
- Raster size: 5632 × 2048 (24-bit RGB province bitmap; 8-bit indexed terrain/rivers/trees; 8-bit grayscale heightmap; 24-bit RGB normal map).
- Land provinces: 223 (IDs 1–223), preserving the stage-1 land IDs.
- Sea provinces: 233 (IDs 224–456), resegmented into compact connected water provinces.
- Total province IDs: 1–456; `max_provinces = 457`.
- Land states: 29; land strategic regions: 29; sea strategic regions: 8.
- Countries: KNO, SUN, IWA, NKU, KIR, OTO, AKA, and provisional MIN.
- Each land province is assigned to exactly one state and one land strategic region. Each sea province is assigned to one sea strategic region.
- Starting division locations, capitals, victory-point markers, building positions, weather positions, and supply nodes now use the new province IDs.

## Important provisional choices
- The original stage-1 map did not define ownership for 84 land provinces. These are provisionally grouped under `MIN` (Minor Shinobi Nations) until their individual country borders and tags are decided.
- The country borders and 29-state layout are generated from stage-1 territory candidate zones and centroid clustering. They are playable scaffolding, not a canon-verified political map.
- The rivers are two generated orthogonal river routes inferred from the reference-map river labels; exact river paths and branching are not manually traced yet.
- Village labels are implemented as state victory points. Mountain and river names are retained in `data/map_labels_draft.csv`; HOI4 does not provide a simple native arbitrary text-overlay layer in these map bitmaps, so they are not all rendered as floating labels in the 3D map.
- The map uses standard terrain bitmap palette indices and the game's existing terrain/colour atlas fallback; no custom DXT5 terrain atlas or world colourmap DDS has been generated. The visual result will therefore be functional map geometry with vanilla terrain rendering, not an exact pixel-perfect reproduction of the reference art.

## Validation performed
- All 11,534,336 province bitmap pixels map to a known RGB definition.
- IDs are consecutive and unique.
- Province bitmap is 24-bit RGB; terrain/rivers/trees are 8-bit indexed; heightmap is 8-bit greyscale; normal map is 24-bit RGB.
- Every land province is included once in state history and once in a strategic region.
- Every sea province is included once in a sea strategic region.
- State IDs and strategic-region IDs are consecutive.
- Capitals, starting OOB locations, victory points, building locations, weather positions, and supply nodes refer to existing province/state IDs.
- Coast flags are recalculated from raster land/sea contact.
- `definition.csv` is written with CRLF line endings.

## Still required before public release
1. Launch the mod with the user's exact HOI4 build and DLC set, using `-debug`; check the complete `error.log` after selecting a country.
2. Run Nudger to re-save/check the province database, sea areas, weather objects, buildings, unit stacks, and supply network.
3. Verify railway routes, ports, combat access and sea-zone connectivity in-game.
4. Replace or approve the provisional MIN country, the territorial ownership and state names.
5. Optionally replace the vanilla terrain atlas/colourmaps with a custom DXT5 atlas/colormap matching the reference's illustrated style.

This is an integrated map beta, not a claim of successful in-engine launch. The game executable is not available in this work environment, so the HOI4 parser and Nudger could not be run here.

## Изменение размера карты
- Все шесть растровых карт приведены к 5632 × 2048.
- provinces.bmp, terrain.bmp, rivers.bmp и trees.bmp масштабированы методом ближайшего соседа, чтобы не создавать новые ID провинций и индексы палитры.
- heightmap.bmp и world_normal.bmp масштабированы сглаживанием; в world_normal.bmp нормали повторно нормализованы.
- Координаты X/Y в buildings.txt, unitstacks.txt и weatherpositions.txt масштабированы коэффициентами 2.75 и 1.333333.
- Изменение соотношения сторон с 4:3 на 2.75:1 геометрически растягивает карту по горизонтали относительно вертикали.
