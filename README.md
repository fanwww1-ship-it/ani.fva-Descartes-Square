# ani.fva-Descartes-Square
import React, { useEffect, useState } from "react";

const promptText = `Помоги мне принять решение через квадрат Декарта.

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
— покажи, какое решение выглядит наиболее честным по отношению ко мне.`;

const questions = [
  {
    number: "01",
    title: "Что будет, если я это сделаю?",
    text: "Плюсы, возможности, последствия, новые сценарии.",
    style: "from-violet-100 to-white",
    dot: "bg-violet-500",
  },
  {
    number: "02",
    title: "Что будет, если я этого НЕ сделаю?",
    text: "Цена бездействия, повторяющиеся сценарии, будущие сожаления.",
    style: "from-orange-100 to-white",
    dot: "bg-orange-500",
  },
  {
    number: "03",
    title: "Чего НЕ будет, если я это сделаю?",
    text: "От чего придётся отказаться: безопасность, привычное, одобрение.",
    style: "from-emerald-100 to-white",
    dot: "bg-emerald-500",
  },
  {
    number: "04",
    title: "Чего НЕ будет, если я этого НЕ сделаю?",
    text: "Какие возможности, версии себя и результаты так и не появятся.",
    style: "from-violet-100 via-orange-50 to-white",
    dot: "bg-violet-500",
  },
];

function Card({ children, className = "" }) {
  return <div className={`rounded-[2rem] border border-zinc-100 bg-white shadow-sm ${className}`}>{children}</div>;
}

function IconBadge({ children, className = "" }) {
  return (
    <span className={`inline-flex h-10 w-10 items-center justify-center rounded-2xl text-lg ${className}`}>
      {children}
    </span>
  );
}

function runSelfTests() {
  const tests = [
    {
      name: "promptText is not empty",
      pass: typeof promptText === "string" && promptText.length > 500,
    },
    {
      name: "contains four Descartes questions",
      pass: questions.length === 4,
    },
    {
      name: "all questions have titles and text",
      pass: questions.every((question) => question.title && question.text),
    },
    {
      name: "prompt includes final analysis instruction",
      pass: promptText.includes("В конце:") && promptText.includes("покажи главные паттерны"),
    },
  ];

  const failedTests = tests.filter((test) => !test.pass);

  if (failedTests.length > 0) {
    console.warn("Self-tests failed:", failedTests.map((test) => test.name).join(", "));
  }

  return failedTests.length === 0;
}

export default function DescartesSquareLeadMagnet() {
  const [copied, setCopied] = useState(false);
  const [toastMessage, setToastMessage] = useState("");

  useEffect(() => {
    runSelfTests();
  }, []);

  const copyPrompt = async () => {
    setToastMessage("");

    try {
      if (typeof navigator !== "undefined" && navigator.clipboard?.writeText) {
        await navigator.clipboard.writeText(promptText);
      } else if (typeof document !== "undefined") {
        const textArea = document.createElement("textarea");
        textArea.value = promptText;
        textArea.setAttribute("readonly", "");
        textArea.style.position = "fixed";
        textArea.style.left = "-9999px";
        document.body.appendChild(textArea);
        textArea.select();
        const copiedSuccessfully = document.execCommand("copy");
        document.body.removeChild(textArea);

        if (!copiedSuccessfully) {
          throw new Error("Fallback copy command failed");
        }
      } else {
        throw new Error("Clipboard is unavailable in this environment");
      }

      setCopied(true);
      setTimeout(() => setCopied(false), 1800);
    } catch (error) {
      if (typeof document !== "undefined") {
        const hiddenTextArea = document.createElement("textarea");
        hiddenTextArea.value = promptText;
        hiddenTextArea.setAttribute("readonly", "true");
        hiddenTextArea.style.position = "absolute";
        hiddenTextArea.style.left = "-9999px";
        hiddenTextArea.style.fontSize = "16px";

        document.body.appendChild(hiddenTextArea);

        if (/ipad|iphone|ipod|android/i.test(navigator.userAgent)) {
          hiddenTextArea.contentEditable = "true";
          hiddenTextArea.readOnly = false;

          const range = document.createRange();
          range.selectNodeContents(hiddenTextArea);

          const selection = window.getSelection();
          selection?.removeAllRanges();
          selection?.addRange(range);

          hiddenTextArea.setSelectionRange(0, 999999);
        } else {
          hiddenTextArea.select();
        }

        const copied = document.execCommand("copy");
        document.body.removeChild(hiddenTextArea);

        if (copied) {
          setCopied(true);
          setToastMessage("Промпт скопирован");
          setTimeout(() => {
            setCopied(false);
            setToastMessage("");
          }, 1800);
          return;
        }
      }

      setToastMessage("Не удалось скопировать промпт");

      console.warn("Автокопирование недоступно.", error);
    }
  };

  return (
    <div className="min-h-screen bg-white text-zinc-950">
      <div className="pointer-events-none fixed inset-0 overflow-hidden">
        <div className="absolute -top-32 left-1/2 h-72 w-72 -translate-x-1/2 rounded-full bg-violet-200/50 blur-3xl" />
        <div className="absolute right-[-6rem] top-64 h-64 w-64 rounded-full bg-orange-200/40 blur-3xl" />
        <div className="absolute bottom-20 left-[-5rem] h-72 w-72 rounded-full bg-emerald-200/40 blur-3xl" />
      </div>

      <main className="relative mx-auto flex w-full max-w-6xl flex-col gap-14 px-5 py-8 sm:px-8 lg:py-12">
        <section className="grid animate-[fadeIn_0.6s_ease-out] items-center gap-10 lg:grid-cols-[1.08fr_0.92fr]">
          <div className="space-y-7">
            <div className="inline-flex items-center gap-2 rounded-full border border-violet-200 bg-white/80 px-4 py-2 text-sm font-medium text-violet-700 shadow-sm backdrop-blur">
              <span aria-hidden="true">✦</span>
              AI-промпт для сложных решений
            </div>

            <div className="space-y-5">
              <h1 className="max-w-3xl text-5xl font-semibold tracking-tight text-zinc-950 sm:text-6xl lg:text-7xl">
                Квадрат Декарта + ИИ
              </h1>
              <p className="max-w-2xl text-xl leading-8 text-zinc-600">
                Одностраничная техника, которая помогает увидеть не только плюсы и минусы, но и скрытые страхи, цену бездействия и честное решение.
              </p>
            </div>

            <div className="flex flex-col gap-3 sm:flex-row">
              <button
                type="button"
                onClick={copyPrompt}
                className="inline-flex h-12 items-center justify-center rounded-full bg-zinc-950 px-6 text-base font-medium text-white transition hover:bg-zinc-800"
              >
                <span className="mr-2" aria-hidden="true">{copied ? "✓" : "⧉"}</span>
                {copied ? "Промпт скопирован" : "Скопировать промпт"}
              </button>
              <a href="#technique" className="inline-flex h-12 items-center justify-center rounded-full border border-zinc-200 bg-white px-6 text-base font-medium text-zinc-800 shadow-sm transition hover:border-zinc-300 hover:bg-zinc-50">
                Посмотреть технику
                <span className="ml-2" aria-hidden="true">→</span>
              </a>
            </div>

            {toastMessage && (
              <div className="max-w-xl rounded-2xl border border-violet-100 bg-violet-50/80 px-4 py-3 text-sm text-violet-700 backdrop-blur transition-all duration-300">
                {toastMessage}
              </div>
            )}
          </div>

          <Card className="overflow-hidden bg-white/80 shadow-2xl shadow-violet-100/70 backdrop-blur">
            <div className="space-y-5 p-6 sm:p-8">
              <div className="flex items-center justify-between">
                <div className="flex items-center gap-3">
                  <IconBadge className="bg-violet-100 text-violet-700">🧠</IconBadge>
                  <div>
                    <p className="font-semibold">Решение</p>
                    <p className="text-sm text-zinc-500">через ясность, а не тревогу</p>
                  </div>
                </div>
                <div className="h-3 w-3 rounded-full bg-emerald-400" />
              </div>

              <div className="rounded-3xl bg-zinc-950 p-5 text-white">
                <p className="text-sm text-zinc-400">Вопрос к AI</p>
                <p className="mt-3 text-2xl font-medium leading-snug">
                  «Какое решение будет самым честным по отношению ко мне?»
                </p>
              </div>

              <div className="grid gap-3 sm:grid-cols-3">
                <div className="rounded-2xl bg-violet-50 p-4">
                  <p className="text-2xl font-semibold text-violet-700">4</p>
                  <p className="text-sm text-zinc-600">ключевых вопроса</p>
                </div>
                <div className="rounded-2xl bg-orange-50 p-4">
                  <p className="text-2xl font-semibold text-orange-700">3</p>
                  <p className="text-sm text-zinc-600">горизонта: 1/3/5 лет</p>
                </div>
                <div className="rounded-2xl bg-emerald-50 p-4">
                  <p className="text-2xl font-semibold text-emerald-700">1</p>
                  <p className="text-sm text-zinc-600">честный вывод</p>
                </div>
              </div>
            </div>
          </Card>
        </section>

        <section id="technique" className="space-y-7">
          <div className="flex flex-col justify-between gap-4 sm:flex-row sm:items-end">
            <div>
              <div className="mb-3 inline-flex items-center gap-2 rounded-full bg-emerald-50 px-4 py-2 text-sm font-medium text-emerald-700">
                <span aria-hidden="true">⌖</span>
                Техника
              </div>
              <h2 className="text-3xl font-semibold tracking-tight sm:text-4xl">Квадрат Декарта</h2>
            </div>
            <p className="max-w-xl text-zinc-600">
              Запиши своё решение в одну фразу, а затем пройди 4 вопроса. Самые важные инсайты часто появляются не в ответах, а уже в моменте, когда ты читаешь вопрос.
            </p>
          </div>

          <div className="grid gap-4 md:grid-cols-2">
            {questions.map((item) => (
              <Card key={item.number} className={`bg-gradient-to-br ${item.style}`}>
                <div className="p-6">
                  <div className="mb-5 flex items-center justify-between">
                    <span className="text-sm font-semibold text-zinc-400">{item.number}</span>
                    <span className={`h-3 w-3 rounded-full ${item.dot}`} />
                  </div>
                  <h3 className="text-2xl font-semibold tracking-tight">{item.title}</h3>
                  <p className="mt-3 leading-7 text-zinc-600">{item.text}</p>
                </div>
              </Card>
            ))}
          </div>
        </section>

        <section className="grid gap-6 lg:grid-cols-[0.85fr_1.15fr]">
          <Card className="bg-zinc-950 text-white shadow-xl">
            <div className="space-y-5 p-7">
              <h2 className="text-3xl font-semibold tracking-tight">Как использовать</h2>
              <div className="space-y-4 text-zinc-300">
                <p>1. Выбери одно конкретное решение.</p>
                <p>2. Скопируй промпт и вставь его в ChatGPT.</p>
                <p>3. Отвечай честно, не красиво.</p>
                <p>4. Обрати внимание, где в ответах появляется облегчение, страх или сопротивление.</p>
              </div>
              <div className="rounded-3xl bg-white/10 p-5">
                <p className="text-sm uppercase tracking-[0.2em] text-zinc-400">Главная мысль</p>
                <p className="mt-2 text-xl font-medium">ИИ не принимает решение за тебя. Он помогает увидеть то, что ты уже знаешь, но пока боишься признать.</p>
              </div>
            </div>
          </Card>

          <Card className="shadow-xl shadow-orange-100/60">
            <div className="p-6 sm:p-8">
              <div className="mb-5 flex flex-col justify-between gap-4 sm:flex-row sm:items-center">
                <div>
                  <p className="text-sm font-semibold uppercase tracking-[0.2em] text-violet-600">Готовый промпт</p>
                  <h2 className="mt-2 text-3xl font-semibold tracking-tight">Скопируй и вставь в AI</h2>
                </div>
                <button
                  type="button"
                  onClick={copyPrompt}
                  className="inline-flex h-11 items-center justify-center rounded-full bg-violet-600 px-5 font-medium text-white transition hover:bg-violet-700"
                >
                  <span className="mr-2" aria-hidden="true">{copied ? "✓" : "⧉"}</span>
                  {copied ? "Скопировано" : "Копировать"}
                </button>
              </div>

              {toastMessage && (
              <div className="max-w-xl rounded-2xl border border-violet-100 bg-violet-50/80 px-4 py-3 text-sm text-violet-700 backdrop-blur transition-all duration-300">
                {toastMessage}
              </div>
            )}

              <div id="prompt-content" className="max-h-[560px] overflow-auto rounded-3xl border border-zinc-100 bg-zinc-50 p-5 text-sm leading-6 text-zinc-700 sm:text-base select-text">
                <pre className="whitespace-pre-wrap font-sans">{promptText}</pre>
              </div>
            </div>
          </Card>
        </section>

        <footer className="flex flex-col items-center justify-between gap-4 border-t border-zinc-100 py-8 text-sm text-zinc-500 sm:flex-row">
          <p>Квадрат Декарта + AI • Мини-инструмент для честных решений</p>
          <p>Сохрани страницу и используй перед важным выбором</p>
        </footer>
      </main>
    </div>
  );
}
