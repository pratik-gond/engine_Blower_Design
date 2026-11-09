# Engine Blower — AutoCAD Backup Files

This repository contains AutoCAD backup files (.bak) for an engine blower assembly and its components. These are backup copies created by AutoCAD; they often contain binary DWG data and should be handled with CAD software.

## Files
- [assembly.bak](assembly.bak) — main assembly backup
- [bolt1.bak](bolt1.bak), [bolt2.bak](bolt2.bak) — fasteners
- [connecting rod.bak](connecting rod.bak) — connecting rod
- [Crankshaft.bak](Crankshaft.bak) — crankshaft
- [engine block.bak](engine block.bak) — engine block
- [engine mount.bak](engine mount.bak) — mounting bracket
- [Impeller Casing.bak](Impeller Casing.bak) — impeller housing
- [impeller.bak](impeller.bak) — impeller
- [piston.bak](piston.bak) — piston

## Quick recovery / preview steps
1. Make a copy of the .bak file you intend to inspect. Never operate on originals.
2. Rename the copy from `filename.bak` to `filename.dwg`.
   - Example: `cp assembly.bak assembly.dwg` (or use file explorer to rename).
3. Open `filename.dwg` in AutoCAD, BricsCAD, LibreCAD, or a DWG viewer.
4. If the file fails to open, use AutoCAD's `RECOVER` / `RECOVERALL` command or the DWG file recovery utility in your CAD package.
5. If data appears corrupted, try exporting partial geometry or use a commercial DWG repair tool.

## Notes
- These .bak files may contain binary data; do not edit them in a text editor.
- If you need to keep a revision history, keep renamed DWG copies in a separate folder or use your VCS on exported CAD-neutral formats (STEP/IGES/DXF) when possible.
- The repository contains raw backups only; drawing metadata and preview text in some .bak files may appear as non-text bytes.

## Suggested next steps
- Convert recovered DWG files to a neutral exchange format (DXF or STEP) for versioning.
- Add a small folder like `recovered/` containing exported, human-reviewable previews (PDF or PNG) for each major file.

License: Add a LICENSE file if you plan to publish these designs.

```// filepath: README.md
# Engine Blower — AutoCAD Backup Files

This repository contains AutoCAD backup files (.bak) for an engine blower assembly and its components. These are backup copies created by AutoCAD; they often contain binary DWG data and should be handled with CAD software.

## Files
- [assembly.bak](assembly.bak) — main assembly backup
- [bolt1.bak](bolt1.bak), [bolt2.bak](bolt2.bak) — fasteners
- [connecting rod.bak](connecting rod.bak) — connecting rod
- [Crankshaft.bak](Crankshaft.bak) — crankshaft
- [engine block.bak](engine block.bak) — engine block
- [engine mount.bak](engine mount.bak) — mounting bracket
- [Impeller Casing.bak](Impeller Casing.bak) — impeller housing
- [impeller.bak](impeller.bak) — impeller
- [piston.bak](piston.bak) — piston

## Quick recovery / preview steps
1. Make a copy of the .bak file you intend to inspect. Never operate on originals.
2. Rename the copy from `filename.bak` to `filename.dwg`.
   - Example: `cp assembly.bak assembly.dwg` (or use file explorer to rename).
3. Open `filename.dwg` in AutoCAD, BricsCAD, LibreCAD, or a DWG viewer.
4. If the file fails to open, use AutoCAD's `RECOVER` / `RECOVERALL` command or the DWG file recovery utility in your CAD package.
5. If data appears corrupted, try exporting partial geometry or use a commercial DWG repair tool.

## Notes
- These .bak files may contain binary data; do not edit them in a text editor.
- If you need to keep a revision history, keep renamed DWG copies in a separate folder or use your VCS on exported CAD-neutral formats (STEP/IGES/DXF) when possible.
- The repository contains raw backups only; drawing metadata and preview text in some .bak files may appear as non-text bytes.

## Suggested next steps
- Convert recovered DWG files to a neutral exchange format (DXF or STEP) for versioning.
- Add a small folder like `recovered/` containing exported, human-reviewable previews (PDF or PNG) for each major file.

License: Add a LICENSE file if you plan to publish these designs.
