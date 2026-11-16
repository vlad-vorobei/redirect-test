# In-app redirect test

Тестова сторінка для перевірки редіректу з in-app браузерів (LINE, Telegram, Instagram) у Safari або Chrome і роботи Autofill.

`index-ua.html` — українська версія, `index.html` — англійська (на GitHub Pages: `https://<username>.github.io/inapp-redirect-test/index-en.html`). Для англійської версії завантаж у репозиторій і `index.html`.

## Як підняти на GitHub Pages

1. На github.com створи новий **публічний** репозиторій, наприклад `inapp-redirect-test`. На безкоштовному акаунті Pages працює тільки з публічними репо.
2. Завантаж у нього `index-ua.html`:
   - через сайт: **Add file → Upload files**, перетягни файл, **Commit changes**;
   - або з терміналу в цій папці:
     ```
     git init
     git add index.html
     git commit -m "Add test page"
     git branch -M main
     git remote add origin https://github.com/<username>/inapp-redirect-test.git
     git push -u origin main
     ```
3. У репозиторії: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, гілка `main`, папка `/ (root)`, **Save**.
4. Через 1–2 хвилини сторінка буде за адресою `https://<username>.github.io/inapp-redirect-test/`. Посилання також з'явиться вгорі сторінки **Settings → Pages**.
5. Після змін у `index-ua.html` достатньо закомітити їх у `main`, Pages оновиться сам за хвилину.

## Як тестувати

1. Збережи тестову картку в Safari (iPhone) і в Chrome (Android).
2. Надішли посилання собі в LINE (Keep memo), Telegram (Saved Messages) та Instagram (Direct) і відкрий його звідти.
3. На сторінці по черзі:
   - **Скопіювати user agent** і надіслати собі;
   - тапнути в **Номер картки**: чи пропонує телефон збережену картку;
   - натиснути кнопку редіректу для своєї платформи;
   - натиснути **Перезавантажити з ?auto=1**: чи спрацює редірект без тапу.
4. Для LINE окремо: відкрити з чату посилання з `?openExternalBrowser=1` наприкінці.

Якщо редірект спрацював, у Safari чи Chrome вгорі буде зелений банер «Відкрито після редіректу: …». Усе, що відбувається, пишеться в блок **Лог** унизу сторінки.

Форма картки нікуди не відправляється.
