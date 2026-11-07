# Структура моделей юнитов

gfx/models/units/jinchuriki/
├── jinchuriki.mesh      ← 3D-меш
├── jinchuriki.anim      ← анимации (если не клонируешь)
├── jinchuriki_diffuse.dds   ← текстура
└── jinchuriki_normal.dds    ← нормаль-мапа

gfx/models/units/ninja/
├── ninja.mesh
├── ninja_diffuse.dds
└── ninja_normal.dds

gfx/models/units/anbu/
├── anbu.mesh
├── anbu_diffuse.dds
└── anbu_normal.dds

gfx/models/units/samurai/
├── samurai.mesh
├── samurai_diffuse.dds
└── samurai_normal.dds

Формат: .mesh — бинарный формат HOI4 (экспорт из Blender через Hoi4 Mesh Exporter).
Анимации берём из ванильных, если своих нет.