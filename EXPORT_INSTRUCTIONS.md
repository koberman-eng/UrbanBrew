# Инструкции по экспорту графических активов

## Подготовка к экспорту

Все графические активы подготовлены в векторном формате SVG. Для использования на веб-сайте необходимо экспортировать их в различных форматах и размерах.

## 1. Логотип

### Файл: `assets/logo/urban-brew-logo.svg`

**Экспорт в PNG:**

1. Откройте файл в Adobe Illustrator, Inkscape или Figma
2. Установите размеры:
   - **1x версия:** 200x80px
   - **2x версия (Retina):** 400x160px
3. Экспортируйте в PNG с прозрачным фоном
4. Сохраните как:
   - `urban-brew-logo.png` (200x80px)
   - `urban-brew-logo@2x.png` (400x160px)

**Экспорт в SVG:**
- Файл уже готов: `urban-brew-logo.svg`
- Можно использовать напрямую в HTML

## 2. Иконки

### Файлы в папке: `assets/icons/`

**Все иконки уже в SVG формате (32x32px)**

Для экспорта в PNG (если требуется):

1. Откройте каждую иконку
2. Экспортируйте в PNG:
   - **1x версия:** 32x32px
   - **2x версия:** 64x64px
3. Сохраните с соответствующими именами:
   - `menu-icon.png` / `menu-icon@2x.png`
   - `contacts-icon.png` / `contacts-icon@2x.png`
   - и т.д.

**Рекомендация:** Используйте SVG напрямую для лучшего качества и меньшего размера файла.

## 3. Графические элементы

### Файлы в папке: `assets/graphics/`

**Все элементы уже в SVG формате**

Для экспорта в PNG (если требуется для фонов):

1. Откройте файл
2. Экспортируйте в PNG с прозрачным фоном:
   - `coffee-bean.png` (64x64px)
   - `coffee-cup.png` (80x100px)
   - `leaf.png` (60x80px)

## 4. Паттерны

### Файл: `assets/patterns/coffee-pattern.svg`

**Использование:**
- Можно использовать SVG напрямую как background-image в CSS
- Или экспортировать в PNG/JPG для фона:
  - Размер: 200x200px (повторяется)
  - Формат: PNG (с прозрачностью) или JPG

## 5. Баннеры для соцсетей

### Файл: `assets/banners/social-banner.html`

**Экспорт в изображения:**

1. Откройте `social-banner.html` в браузере
2. Используйте инструмент для скриншота или экспорта:
   - **Chrome DevTools:** Cmd/Ctrl + Shift + P → "Capture screenshot"
   - **Расширения браузера:** Full Page Screen Capture
   - **Figma/Photoshop:** Импортируйте HTML или создайте макет

3. Экспортируйте в форматы:
   - **JPG:** `social-banner.jpg` (1200x630px, качество 85-90%)
   - **WebP:** `social-banner.webp` (1200x630px) - для лучшего сжатия
   - **PNG:** `social-banner.png` (1200x630px) - если нужна прозрачность

**Альтернативный способ:**
- Создайте макет в Figma на основе HTML
- Экспортируйте напрямую из Figma

## 6. GIF анимация

### Файл: `assets/animations/logo-animation.html`

**Создание GIF в Photoshop:**

1. Откройте `logo-animation.html` в браузере
2. Запишите экран с помощью инструмента записи (OBS, QuickTime, etc.)
   - Длительность: 3-5 секунд (один цикл)
   - Размер: 200x80px (1x) или 400x160px (2x)
   - Формат: MP4

3. Импортируйте видео в Photoshop:
   - File → Import → Video Frames to Layers
   - Выберите "From Beginning to End"
   - Установите ограничение кадров (8-12 кадров)

4. Оптимизируйте GIF:
   - Window → Timeline (если не открыт)
   - File → Export → Save for Web (Legacy)
   - Настройки:
     - Format: GIF
     - Colors: 128-256 (оптимизировать)
     - Dither: 88%
     - Lossy: 0-5%
     - Loop: Forever
   - Размер файла должен быть < 500KB

5. Сохраните как:
   - `logo-animation.gif` (200x80px)
   - `logo-animation@2x.gif` (400x160px)

**Альтернативные инструменты:**
- **GIMP:** Создание анимации из кадров
- **Online инструменты:** Ezgif.com, CloudConvert
- **After Effects:** Export → Render Queue → Format: Animated GIF

## 7. Видео анимация

### Файл: `assets/animations/hero-banner-animation.html`

**Создание MP4:**

1. Откройте `hero-banner-animation.html` в браузере
2. Запишите экран:
   - **Chrome DevTools:** 
     - Cmd/Ctrl + Shift + P
     - "Show Rendering"
     - Включите "Frame Rendering Stats"
     - Используйте инструмент записи экрана
   - **OBS Studio:** Запись области экрана
   - **QuickTime (Mac):** File → New Screen Recording

3. Настройки записи:
   - Размер: 1200x630px
   - Длительность: 5-10 секунд (один цикл)
   - FPS: 30
   - Формат: MP4 (H.264)

4. Оптимизация видео:
   - **HandBrake:** Сжатие видео
     - Preset: Web/General
     - Quality: RF 23-28
     - Размер должен быть < 2MB
   - **FFmpeg:**
     ```bash
     ffmpeg -i input.mp4 -vcodec h264 -crf 23 -preset slow output.mp4
     ```

5. Сохраните как:
   - `hero-banner.mp4` (1200x630px)

**Альтернатива - Lottie JSON:**

1. Используйте After Effects + Bodymovin plugin:
   - Создайте анимацию в After Effects
   - Установите плагин Bodymovin
   - Export → Bodymovin
   - Сохраните как JSON

2. Или используйте онлайн конвертер:
   - LottieFiles.com
   - Конвертируйте из видео или создайте в редакторе

3. Сохраните как:
   - `hero-banner.json` (Lottie файл)

## 8. Структура папок для экспорта

После экспорта структура должна выглядеть так:

```
assets/
├── logo/
│   ├── urban-brew-logo.svg
│   ├── urban-brew-logo.png (200x80px)
│   └── urban-brew-logo@2x.png (400x160px)
├── icons/
│   ├── *.svg (все иконки)
│   └── (опционально) *.png версии
├── graphics/
│   ├── *.svg (все элементы)
│   └── (опционально) *.png версии
├── patterns/
│   └── coffee-pattern.svg
├── banners/
│   ├── social-banner.html
│   ├── social-banner.jpg (1200x630px)
│   └── social-banner.webp (1200x630px)
└── animations/
    ├── logo-animation.html
    ├── logo-animation.gif (200x80px)
    ├── logo-animation@2x.gif (400x160px)
    ├── hero-banner-animation.html
    ├── hero-banner.mp4 (1200x630px)
    └── hero-banner.json (Lottie, опционально)
```

## 9. Проверка качества

После экспорта проверьте:

- [ ] Все PNG файлы имеют правильные размеры
- [ ] Retina версии (@2x) в 2 раза больше
- [ ] GIF анимация зациклена (Forever)
- [ ] Видео имеет autoplay, loop, muted атрибуты
- [ ] Размеры файлов оптимизированы
- [ ] Все файлы имеют правильные имена

## 10. Упаковка для передачи разработчику

Создайте архив со следующей структурой:

```
urban-brew-assets.zip
├── README.md (инструкции)
├── style-guide.html (стиль-гайд)
├── demo-page.html (демо-страница)
└── assets/ (все экспортированные файлы)
```

**Включите в архив:**
- Все SVG файлы (оригиналы)
- PNG версии (1x и 2x где необходимо)
- GIF анимации
- Видео файлы
- Баннеры (JPG/WebP)
- HTML файлы для справки

**Размер архива должен быть:**
- Без видео: < 5MB
- С видео: < 10MB (после оптимизации)

