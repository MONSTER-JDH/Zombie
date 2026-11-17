# Арена зомби: сборка APK

## Способ 1. Без установки Android Studio (GitHub)
1. Создайте пустой репозиторий на github.com и загрузите в него все файлы из этой папки
   (включая скрытую папку .github).
2. Откройте вкладку Actions, запустите «Build APK» (Run workflow) или просто сделайте commit.
3. Через 3–5 минут скачайте файл zombie-arena-apk из раздела Artifacts внутри выполненного запуска.
4. Распакуйте архив, перенесите app-debug.apk на телефон и установите (разрешите установку из неизвестных источников).

## Способ 2. Локально
Нужны Node.js 20, JDK 17 и Android Studio (Android SDK).
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk

## Важно
В APK работают игра, музыка, магазин, достижения и сохранение в памяти приложения.
Облачные аккаунты и онлайн-мультиплеер завязаны на среду Claude и в APK недоступны:
для них нужен собственный сервер (например, WebSocket).
