# Bite — резервные загрузки компонентов

Здесь лежат копии архивов, которые приложение **Байт** (Base-версия) докачивает
при первом запуске. Сначала программа пробует официальный источник; если он
недоступен или файл оттуда удалён — берёт архив отсюда.

## Релизы

- `components-b12376` — движок llama.cpp b12376 (CPU и CUDA 12.4), Python 3.11.9
  embed, модель Vosk для русского, python-пакеты голоса, Silero, `univer-cli`.
- `model-qwen3-1.7b` — файл модели `qwen3-1.7b-q4km.gguf` (Qwen3-1.7B Q4_K_M).

## Что это за файлы

| Файл | Что внутри | Официальный источник |
| --- | --- | --- |
| `engine-cpu.zip` | llama.cpp b12376, сборка под процессор | github.com/ggml-org/llama.cpp |
| `engine-cuda.zip` | llama.cpp b12376, сборка под CUDA 12.4 | github.com/ggml-org/llama.cpp |
| `cudart-cuda.zip` | библиотеки CUDA (cublas, cudart) | github.com/ggml-org/llama.cpp |
| `python-3.11.9-embed-amd64.zip` | встроенный Python | python.org |
| `vosk-model-small-ru-0.22.zip` | модель распознавания речи | alphacephei.com/vosk |
| `voice-pkgs.zip` | python-пакеты для голоса (torch, vosk, numpy…) | собран из PyPI |
| `silero-hub.zip` | модель нейроголоса Silero | собран из репозитория Silero |
| `univer-cli.zip` | офисные инструменты Univer | собран из npm-пакета univer-cli |

Контрольные суммы (sha256) частей перечислены в `launcher/components.json`
внутри приложения; при докачке они проверяются, битый архив скачивается заново.

Архивы не изменяются: это точные копии того, что отдают официальные источники
или что собрано из свободно распространяемых пакетов.
