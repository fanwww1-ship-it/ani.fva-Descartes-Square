<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Квадрат Декарта + AI</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
      background: #ffffff;
    }

    .glass {
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
    }

    .gradient-text {
      background: linear-gradient(135deg, #7c3aed, #f97316, #10b981);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .card-hover {
      transition: all 0.35s ease;
    }

    .card-hover:hover {
      transform: translateY(-6px);
      box-shadow: 0 25px 60px rgba(0,0,0,0.08);
    }

    .fade-up {
      animation: fadeUp 0.8s ease forwards;
    }

    @keyframes fadeUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .blob {
      position: absolute;
      border-radius: 9999px;
      filter: blur(80px);
      opacity: 0.35;
      z-index: 0;
    }

    .prompt-box::-webkit-scrollbar {
      width: 6px;
    }

    .prompt-box::-webkit-scrollbar-thumb {
      background: rgba(124, 58, 237, 0.25);
      border-radius: 999px;
    }
  </style>
</head>
<body class="text-zinc-900">

  <div class="blob bg-violet-300 w-[420px] h-[420px] top-[-120px] left-[10%]"></div>
  <div class="blob bg-orange-200 w-[360px] h-[360px] top-[320px] right-[-80px]"></div>
  <div class="blob bg-emerald-200 w-[360px] h-[360px] bottom-[0px] left-[-80px]"></div>

  <main class="relative z-10 max-w-7xl mx-auto px-5 py-8 lg:py-14">

    <section class="grid lg:grid-cols-2 gap-12 items-center fade-up">

      <div>
        <div class="inline-flex items-center gap-2 border border-violet-200 bg-white/80 glass rounded-full px-4 py-2 text-sm font-medium text-violet-700 shadow-sm mb-7">
          ✦ AI-инструмент для сложных решений
        </div>

        <h1 class="text-5xl lg:text-7xl font-black tracking-tight leading-[0.95] max-w-3xl">
          Квадрат
          <span class="gradient-text">Декарта + AI</span>
        </h1>

        <p class="mt-8 text-xl leading-9 text-zinc-600 max-w-2xl">
          Техника, которая помогает увидеть скрытые страхи, цену бездействия и принять решение не из тревоги — а из ясности.
        </p>

        <div class="flex flex-col sm:flex-row gap-4 mt-10">
          <button
            onclick="copyPrompt()"
            class="h-14 px-7 rounded-full bg-zinc-950 text-white text-base font-semibold hover:scale-[1.02] transition-all shadow-xl shadow-zinc-300/40"
          >
            ⧉ Скопировать промпт
          </button>

          <a
            href="#prompt"
            class="h-14 px-7 rounded-full border border-zinc-200 bg-white text-zinc-800 text-base font-semibold flex items-center justify-center hover:bg-zinc-50 transition-all"
          >
            Посмотреть технику →
          </a>
        </div>

        <div
          id="toast"
          class="hidden mt-5 rounded-2xl border border-violet-100 bg-violet-50 px-4 py-3 text-sm text-violet-700 w-fit"
        ></div>
      </div>

      <div class="bg-white/70 glass rounded-[36px] border border-zinc-100 shadow-2xl shadow-violet-100/60 p-7 lg:p-9 card-hover">

        <div class="flex items-center justify-between">
          <div class="flex items-center gap-3">
            <div class="w-12 h-12 rounded-2xl bg-violet-100 flex items-center justify-center text-xl">
              🧠
            </div>
            <div>
              <div class="font-semibold">Решение</div>
              <div class="text-sm text-zinc-500">через ясность, а не тревогу</div>
            </div>
          </div>

          <div class="w-3 h-3 rounded-full bg-emerald-400"></div>
        </div>

        <div class="mt-7 rounded-3xl bg-zinc-950 text-white p-6">
          <div class="text-sm text-zinc-400 mb-3">Главный вопрос</div>
          <div class="text-3xl font-semibold leading-tight">
            «Какое решение будет самым честным по отношению ко мне?»
          </div>
        </div>

        <div class="grid grid-cols-3 gap-3 mt-5">
          <div class="rounded-2xl bg-violet-50 p-4">
            <div class="text-3xl font-bold text-violet-700">4</div>
            <div class="text-sm text-zinc-600 mt-1">ключевых вопроса</div>
          </div>

          <div class="rounded-2xl bg-orange-50 p-4">
            <div class="text-3xl font-bold text-orange-700">3</div>
            <div class="text-sm text-zinc-600 mt-1">горизонта: 1/3/5 лет</div>
          </div>

          <div class="rounded-2xl bg-emerald-50 p-4">
            <div class="text-3xl font-bold text-emerald-700">1</div>
            <div class="text-sm text-zinc-600 mt-1">честный вывод</div>
          </div>
        </div>
      </div>
    </section>

    <section class="mt-28 fade-up">
      <div class="flex flex-col lg:flex-row lg:items-end lg:justify-between gap-5 mb-10">
        <div>
          <div class="inline-flex items-center gap-2 rounded-full bg-emerald-50 px-4 py-2 text-sm font-medium text-emerald-700 mb-5">
            ⌖ Техника
          </div>

          <h2 class="text-4xl lg:text-5xl font-black tracking-tight">
            Квадрат Декарта
          </h2>
        </div>

        <p class="max-w-2xl text-zinc-600 text-lg leading-8">
          Самые важные инсайты часто появляются не в ответах — а в моменте, когда ты впервые честно читаешь вопрос.
        </p>
      </div>

      <div class="grid md:grid-cols-2 gap-5">

        <div class="rounded-[32px] p-8 bg-gradient-to-br from-violet-100 to-white border border-violet-100 card-hover">
          <div class="flex items-center justify-between mb-5">
            <div class="text-sm font-bold text-zinc-400">01</div>
            <div class="w-3 h-3 rounded-full bg-violet-500"></div>
          </div>

          <h3 class="text-3xl font-bold tracking-tight leading-tight">
            Что будет,
            если я это сделаю?
          </h3>

          <p class="mt-4 text-zinc-600 leading-8 text-lg">
            Возможности, новые сценарии, рост, последствия и изменения.
          </p>
        </div>

        <div class="rounded-[32px] p-8 bg-gradient-to-br from-orange-100 to-white border border-orange-100 card-hover">
          <div class="flex items-center justify-between mb-5">
            <div class="text-sm font-bold text-zinc-400">02</div>
            <div class="w-3 h-3 rounded-full bg-orange-500"></div>
          </div>

          <h3 class="text-3xl font-bold tracking-tight leading-tight">
            Что будет,
            если я этого НЕ сделаю?
          </h3>

          <p class="mt-4 text-zinc-600 leading-8 text-lg">
            Цена бездействия, повторяющиеся сценарии и будущие сожаления.
          </p>
        </div>

        <div class="rounded-[32px] p-8 bg-gradient-to-br from-emerald-100 to-white border border-emerald-100 card-hover">
          <div class="flex items-center justify-between mb-5">
            <div class="text-sm font-bold text-zinc-400">03</div>
            <div class="w-3 h-3 rounded-full bg-emerald-500"></div>
          </div>

          <h3 class="text-3xl font-bold tracking-tight leading-tight">
            Чего НЕ будет,
            если я это сделаю?
          </h3>

          <p class="mt-4 text-zinc-600 leading-8 text-lg">
            От чего придётся отказаться: привычное, стабильность, одобрение.
          </p>
        </div>

        <div class="rounded-[32px] p-8 bg-gradient-to-br from-violet-100 via-orange-50 to-white border border-zinc-100 card-hover">
          <div class="flex items-center justify-between mb-5">
            <div class="text-sm font-bold text-zinc-400">04</div>
            <div class="w-3 h-3 rounded-full bg-violet-500"></div>
          </div>

          <h3 class="text-3xl font-bold tracking-tight leading-tight">
            Чего НЕ будет,
            если я этого НЕ сделаю?
          </h3>

          <p class="mt-4 text-zinc-600 leading-8 text-lg">
            Какие версии тебя, возможности и результаты так и не появятся.
          </p>
        </div>
      </div>
    </section>

    <section id="prompt" class="mt-28 grid lg:grid-cols-[0.85fr_1.15fr] gap-6 fade-up">

      <div class="rounded-[36px] bg-zinc-950 text-white p-8 lg:p-10 shadow-2xl">
        <h2 class="text-4xl font-black tracking-tight">
          Как использовать
        </h2>

        <div class="space-y-5 text-zinc-300 mt-8 text-lg leading-8">
          <p>1. Выбери одно конкретное решение.</p>
          <p>2. Скопируй промпт и вставь его в ChatGPT.</p>
          <p>3. Отвечай честно, а не «правильно».</p>
          <p>4. Замечай, где появляется сопротивление, страх или облегчение.</p>
        </div>

        <div class="mt-8 rounded-3xl bg-white/10 p-6">
          <div class="uppercase tracking-[0.2em] text-zinc-400 text-sm mb-3">
            Главная мысль
          </div>

          <div class="text-2xl leading-10 font-semibold">
            ИИ не принимает решение за тебя.
            Он помогает увидеть то, что ты уже знаешь,
            но пока боишься признать.
          </div>
        </div>
      </div>

      <div class="rounded-[36px] bg-white border border-zinc-100 p-6 lg:p-8 shadow-2xl shadow-orange-100/40">

        <div class="flex flex-col sm:flex-row sm:items-center sm:justify-between gap-5 mb-6">
          <div>
            <div class="uppercase tracking-[0.2em] text-violet-600 text-sm font-semibold">
              Готовый промпт
            </div>

            <h2 class="text-4xl font-black tracking-tight mt-2">
              Скопируй и вставь в AI
            </h2>
          </div>

          <button
            onclick="copyPrompt()"
            class="h-12 px-6 rounded-full bg-violet-600 text-white font-semibold hover:bg-violet-700 transition-all"
          >
            ⧉ Копировать
          </button>
        </div>

        <div
          id="promptBox"
          class="prompt-box max-h-[680px] overflow-auto rounded-[28px] border border-zinc-100 bg-zinc-50 p-6 text-[15px] leading-8 text-zinc-700 whitespace-pre-wrap"
        >Помоги мне принять решение через квадрат Декарта.

Я хочу, чтобы ты был не просто помощником, а стратегом, психологом и человеком, который видит мои слепые зоны.

Проведи меня глубоко через 4 вопроса квадрата Декарта:

1. Что произойдет, если я это сделаю?
2. Что произойдет, если я этого НЕ сделаю?
3. Чего НЕ произойдет, если я это сделаю?
4. Чего НЕ произойдет, если я этого НЕ сделаю?

Но НЕ отвечай поверхностно.

Твоя задача:
— задавать неудобные вопросы
— замечать самообман
— показывать скрытые страхи
— выявлять эмоциональные искажения
— подсвечивать долгосрочные последствия
— отделять реальные риски от тревоги
— показывать цену бездействия
— обращать внимание на то, где я выбираю безопасность вместо роста
— замечать, где решение продиктовано страхом осуждения, а не моими настоящими желаниями

Если увидишь внутренний конфликт — раскрой его глубже.

После каждого моего ответа:
— анализируй его
— замечай противоречия
— задавай следующий точный вопрос
— не спеши давать вывод

Особенно помоги мне понять:
— чего я на самом деле боюсь потерять
— что я уже давно знаю, но избегаю признать
— какое решение выбрала бы версия меня без страха
— как будет выглядеть моя жизнь через 1/3/5 лет в каждом сценарии
— что станет моей самой большой болью в будущем
— о чем я скорее пожалею

В конце:
— собери все мои ответы
— покажи главные паттерны
— назови мои настоящие мотивы
— скажи, где говорит страх, а где — мои реальные ценности
— покажи, какое решение выглядит наиболее честным по отношению ко мне.</div>
      </div>
    </section>

    <footer class="mt-20 border-t border-zinc-100 py-8 flex flex-col sm:flex-row gap-3 items-center justify-between text-sm text-zinc-500">
      <div>Квадрат Декарта + AI • Мини-инструмент для честных решений</div>
      <div>Сохрани страницу и используй перед важным выбором</div>
    </footer>
  </main>

  <script>
    async function copyPrompt() {
      const text = document.getElementById('promptBox').innerText;
      const toast = document.getElementById('toast');

      try {
        await navigator.clipboard.writeText(text);

        toast.innerText = '✓ Промпт скопирован';
        toast.classList.remove('hidden');

        setTimeout(() => {
          toast.classList.add('hidden');
        }, 2200);

      } catch (err) {
        const textarea = document.createElement('textarea');
        textarea.value = text;
        textarea.style.position = 'fixed';
        textarea.style.opacity = '0';

        document.body.appendChild(textarea);
        textarea.focus();
        textarea.select();

        try {
          document.execCommand('copy');

          toast.innerText = '✓ Промпт скопирован';
          toast.classList.remove('hidden');

          setTimeout(() => {
            toast.classList.add('hidden');
          }, 2200);

        } catch (e) {
          toast.innerText = 'Не удалось скопировать';
          toast.classList.remove('hidden');
        }

        document.body.removeChild(textarea);
      }
    }
  </script>
</body>
</html>
