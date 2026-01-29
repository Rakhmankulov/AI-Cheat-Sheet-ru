# AI-Cheat-Sheet-ru  

Здесь я постарался отразить всю теоретическую выжимку про Искусственный интеллект на  русском языке  
> Есть чем дополнить? Жду ваш PR

- [Глоссарий](https://github.com/Rakhmankulov/AI-Cheat-Sheet-ru/blob/main/glossary_ai_llm_rag.md)
- [База LLM](#База-LLM)
- [LLM Leaderboards](#LLM-Leaderboards)


## База LLM
---
| Термин | Ссылка |
|--------|--------|
| Откуда брать модели? | https://huggingface.co/ |
| Ollama | https://ollama.com/ |
| vLLM | https://github.com/vllm-project/vllm |
| Triton | https://developer.nvidia.com/dynamo |
---
## LLM Leaderboards

Здесь я постараюсь отражать актуальные лидерборды (рейтинги) популярных LLM

| Критерии измерений | Ссылка | Комментарий |
|--------------------|--------|-------------|
| Chatbot Arena and Leaderboard | https://lmarena.ai/ | Самый популярный лидерборд от лиги плюща (Беркли)|
| Arena для сравнения моделей | https://arena.ai/c/019c0a4c-9805-72f6-a009-f028e5b3caa4 | Слепой тест 2 моделей, после выбота предпочтительного ответа сайт показывает какие модели отвечали |

| HuggingFace | https://huggingface.co/docs/leaderboards/en/leaderboards/finding_page | Математика/Производительность/Код/Безопасность |
| LLM Leaderboard от Vellum AI | https://www.vellum.ai/llm-leaderboard?utm_source=chatgpt.com | Красивая инфографика для домохозяек |
| Artificial Analysis LLM Performance Leaderboard | https://artificialanalysis.ai/leaderboards/models?utm_source=chatgpt.com | Сравнивают качество, цену, производительность и скорость |
| SEAL LLM Leaderboards от Scale AI | https://scale.com/leaderboard?utm_source=chatgpt.com | Предлагает экспертные, регулярно обновляемые оценки и ранжирование LLM в различных областях, таких как кодирование и следование инструкциям |
| hallucination-leaderboard | https://github.com/vectara/hallucination-leaderboard | |
| LLM Arena in Russian | https://huggingface.co/spaces/lmarena/chatbot-arena-leaderboard | Как Беркли, только модели русскоязычные |
| Vikhrmodels | https://huggingface.co/spaces/Vikhrmodels/arenahardlb | Эти ребята и сами дообучают модели |

---
## LLM Калькуляторы
https://huggingface.co/spaces/NyxKrage/LLM-Model-VRAM-Calculator
https://llm-calc.rayfernando.ai/
https://llm-inference-calculator-rki02.kinsta.page/

## NVIDIA MIG
Вводная и подробная статья: https://docs.nvidia.com/datacenter/tesla/mig-user-guide/index.html#supported-configurations

| Термин               | Определение                                                                                                  |
|----------------------|--------------------------------------------------------------------------------------------------------------|
| **Streaming Multiprocessor (SM)** | Потоковый мультипроцессор (SM) — исполняет вычислительные инструкции на GPU.                                   |
| **GPU Context**      | Контекст GPU — аналогичен процессу на CPU. Включает все ресурсы, необходимые для выполнения операций на GPU: отдельное адресное пространство, выделенная память и др. Свойства: <br>- Изоляция сбоев<br>- Индивидуальное планирование<br>- Отдельное адресное пространство |
| **GPU Engine**       | Движок GPU — исполняет задачи на GPU. Наиболее часто используется вычислительно-графический движок. Также существуют: <br>- Copy Engine (CE) — отвечает за DMA-операции<br>- NVDEC — декодирование видео<br>- NVENC — кодирование видео <br>Каждый движок можно планировать отдельно, и он может обслуживать разные контексты GPU. |
| **GPU Memory Slice** | Фрагмент памяти GPU — наименьшая доля памяти GPU, включая контроллеры памяти и кэш. Один фрагмент примерно равен 1/8 всех ресурсов памяти GPU (и по объёму, и по пропускной способности). |
| **GPU SM Slice**     | Фрагмент SM — наименьшая часть потоковых мультипроцессоров (SM) на GPU. Примерно равна 1/7 от общего числа SM, когда GPU работает в режиме MIG. |
| **GPU Slice**        | Фрагмент GPU — объединение одного фрагмента памяти GPU и одного фрагмента SM.                                   |
| **GPU Instance (GI)**| Экземпляр GPU — комбинация фрагментов GPU и движков (DMA, NVDEC и т.д.). Внутри GI: <br>- Память и движки — общие <br>- Фрагменты SM могут делиться на вычислительные экземпляры (CI). <br>Каждый фрагмент памяти ограничивает доступные ресурсы (объём и пропускную способность), обеспечивая QoS по памяти. |
| **Compute Instance (CI)** | Вычислительный экземпляр — подмножество экземпляра GPU. Содержит часть SM и других движков родительского GI. Делит память и движки с другими CI. |


Мой ТГ: https://t.me/itwithbugs
