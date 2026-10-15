# ae69-photos

Фото каталога для сайта AE69 B2B (Freon717/ae69-b2b-app). Сайт берёт их через
jsDelivr: `https://cdn.jsdelivr.net/gh/Freon717/ae69-photos@<коммит>/…`.
В сборку сайта эти файлы не входят (у Grok лимит сборки 30 МБ).

- `p/<id>.webp` — фото с ae69.ru (`/files/_docs/<id>.*`). Если в каталоге стоит
  миниатюра 256 px, здесь лежит фото карточки 512 px.
- `o/<имя>.webp` — фото владельца (бывшая папка `public/photos` сайта).

Обновление — `scripts/sync-photo-mirror.py` в репозитории сайта; после пуша
новый коммит этого репозитория вписывается в `PHOTO_MIRROR_REF`
(`src/lib/photo-src.ts`).
- `s/320/…`, `s/640/…` — уменьшенные копии фото шире 640 px (для плиток
  каталога), `scripts/photo-sizes.py` в репозитории сайта (2026-10-15). После
  пуша нового коммита — `node scripts/warm-photo-mirror.mjs <коммит>`, чтобы
  jsDelivr заранее взял все файлы, и только потом новый `PHOTO_MIRROR_REF`.
