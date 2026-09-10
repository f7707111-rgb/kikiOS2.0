# kikiOS — сайт

Весь сайт = один файл `index.html` (362 КБ). Картинки вшиты внутрь в base64,
шрифты подтягиваются с Google Fonts. Отдельных файлов заливать не нужно.

## Как выложить (выбери один вариант)

### Netlify Drop — быстрее всего, ~30 секунд
1. Открой https://app.netlify.com/drop
2. Перетащи туда папку `kikios` (внутри должен быть `index.html`).
3. Ссылка появится сразу, вида `имя.netlify.app`. Переименовать: Site settings → Change site name.

### GitHub Pages (аккаунт f7707111-rgb)
1. Новый публичный репозиторий, например `kikios`.
2. Add file → Upload files → залей `index.html` в корень → Commit.
3. Settings → Pages → Source: Deploy from a branch → ветка `main`, папка `/ (root)` → Save.
4. Через 1-2 минуты: https://f7707111-rgb.github.io/kikios/
   Хочешь адрес без подпапки — назови репозиторий `f7707111-rgb.github.io`.

### Vercel
vercel.com → Add New → Project → загрузить папку → Deploy.

## Свой домен
Netlify: Domain management → Add a domain.
GitHub Pages: Settings → Pages → Custom domain.
Оба покажут нужные DNS-записи (обычно CNAME на их адрес).

## Что править в файле
- Ссылка на Discord встречается 6 раз: `https://discord.gg/HJmuzk6BMc`.
  Меняешь через «Найти и заменить» в редакторе (VS Code, Notepad++), чтобы не пропустить ни одну.
- Тексты RU/EN лежат в объекте переводов в `<script>` внизу файла, ключи вида `meta.title`.
  На странице они привязаны через атрибут `data-i18n`, так что правь именно в этом объекте,
  иначе перевод перезатрёт твою правку при переключении языка.
- Цвета и типографика: блок `:root` в самом начале `<style>` (`--clay` — акцентный оранжевый).

## Мелочь, которую стоит добавить
Фавиконки нет: во вкладке браузера будет пустой листок.
Закинь `favicon.ico` (или `.png`) рядом с `index.html` и добавь в `<head>`:

    <link rel="icon" href="/favicon.png">
