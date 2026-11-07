Naruto Shinobi Wars — temporary vanilla research diagnostic
================================================================
Purpose: test the mod with the original Hearts of Iron IV technology and doctrine trees.

Disabled temporarily (original files preserved verbatim in _disabled_research_backup/):
- All files in common/technologies/
- common/doctrines/ninja_doctrines.txt
- common/scientific_research/KNO_special_projects.txt
- common/scientific_research/KNO_facilities.txt
- interface/technologies.gfx (custom tech icons)

Adjusted dependencies of disabled technology IDs:
- Removed KNO AI research_priority entries for the removed custom technologies.
- Bypassed AI template/equipment gates that required removed custom technologies.
- Disabled the council idea bonus for the custom ninjutsu research category.

The descriptor name and replace_path entries were not changed. No vanilla game files were modified.
To restore the Naruto-specific research later, restore the original files from _disabled_research_backup/
and reverse the three dependency adjustments described above.
This archive has not been launched in the HOI4 game executable; in-game validation is still required.
