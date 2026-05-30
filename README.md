# PELYUSTKA — Jewelry

Лендинг ювелирного магазина: бегущая строка, шапка с навигацией, hero-слайдер на 3 фото и блок преимуществ. Чистый HTML/CSS/JS, без сборки.

## Структура

```
pelyustka/
├── index.html        ← сама страница
├── netlify.toml       ← настройки Netlify (кеш, заголовки)
├── .gitignore
├── README.md
└── images/
    ├── slide1.jpg     ← набор-сердечки в коробочке
    ├── slide2.jpg     ← кольцо / браслет / серьги
    └── slide3.jpg     ← золотые ласточки
```

Чтобы заменить фото в слайдере — просто положи новые файлы с теми же именами в папку `images/` (или поменяй пути в `index.html` в блоке `<section class="hero">`).

---

## Заливка на GitHub

### Вариант А — через сайт GitHub (без терминала)
1. Зайди на https://github.com/new, создай репозиторий, например `pelyustka`.
2. На странице репозитория нажми **Add file → Upload files**.
3. Перетащи `index.html`, `netlify.toml`, `.gitignore`, `README.md` и папку `images/` целиком.
4. Нажми **Commit changes**.

### Вариант Б — через терминал
```bash
cd pelyustka
git init
git add .
git commit -m "init: PELYUSTKA landing"
git branch -M main
git remote add origin https://github.com/ТВОЙ_ЛОГИН/pelyustka.git
git push -u origin main
```

---

## Подключение Netlify

1. Зайди на https://app.netlify.com → **Add new site → Import an existing project**.
2. Выбери **GitHub**, авторизуйся, укажи репозиторий `pelyustka`.
3. Настройки сборки оставь пустыми (это статический сайт):
   - **Build command** — пусто
   - **Publish directory** — `.` (точка)
   
   Эти же значения уже прописаны в `netlify.toml`, так что обычно Netlify подхватит их сам.
4. Нажми **Deploy**. Через ~30 секунд получишь адрес вида `https://имя.netlify.app`.

### Главное преимущество связки
Каждый раз, когда ты делаешь `git push` (или загружаешь новый файл на GitHub), Netlify **автоматически пересобирает и публикует** сайт. Менять фото или текст можно прямо в репозитории — деплой произойдёт сам.

---

## Свой домен (опционально)
В Netlify: **Domain settings → Add a custom domain**, дальше пропиши у регистратора домена записи, которые покажет Netlify. HTTPS-сертификат Netlify выдаёт бесплатно автоматически.

## Локальный просмотр
Достаточно открыть `index.html` двойным кликом. Если слайдер или шрифты не грузятся из-за ограничений браузера — запусти локальный сервер:
```bash
python3 -m http.server 8000
# затем открой http://localhost:8000
```
