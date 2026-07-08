
# Установка и запуск инвестиционного агента на macOS 

## Требования

- macOS (Apple Silicon или Intel)

- учётная запись на [OpenRouter](https://openrouter.ai/) (для API-ключа)

- учётная запись в Telegram

- доступ в интернет

## 1. Установка Lume (виртуальная машина)

Введите в терминале:

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/trycua/cua/main/libs/lume/scripts/install.sh)"

echo 'export PATH="$PATH:$HOME/.local/bin"' >> ~/.zshrc && source ~/.zshrc

## 2. Создание и запуск виртуальной машины

Введите в терминале:

lume create "ИМЯ" --os macos --ipsw latest

lume run "ИМЯ"

## 3. Установка OpenClaw внутри VM

Подключитесь к VM (через VNC или SSH) и выполните:

curl -fsSL https://openclaw.ai/install.sh | bash

openclaw onboard

## 4. Настройка Telegram-бота

В Telegram найдите @BotFather, создайте бота и получите токен.

В процессе openclaw onboard выберите Telegram и вставьте токен.


## 5. Настройка модели (OpenRouter)

Получите бесплатный ключ на openrouter.ai.

Установите плагин: npm install -g @zi.yi/openclaw-easy.

Запустите: openclaw-easy — он автоматически настроит модель.

## 6. Добавление навыков (Skills)

Скопируйте папки навыков (best-practices-researcher, investment-analyzer, document-preparer) в ~/.openclaw/skills/.

## 7. Запуск агента

В терминале выполните: openclaw gateway restart

Теперь напишите вашему боту в Telegram: привет, /help и т.п.