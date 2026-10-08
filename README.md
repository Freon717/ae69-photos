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
