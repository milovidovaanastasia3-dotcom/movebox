window.MOVEBOX_CONFIG = {
  googleScriptUrl: ""
};

const surveyQuestions = [
  {
    id: 1,
    text: "Сколько вам лет?",
    type: "radio",
    required: true,
    options: [
      "До 14 лет",
      "14–17 лет",
      "18–24 года",
      "25–34 года",
      "35–44 года",
      "45 лет и старше"
    ]
  },
  {
    id: 2,
    text: "Как вы себя идентифицируете?",
    type: "radio",
    required: false,
    options: [
      "Женский пол",
      "Мужской пол",
      "Предпочитаю не отвечать"
    ]
  },
  {
    id: 3,
    text: "Чем вы сейчас занимаетесь?",
    type: "radio",
    required: false,
    options: [
      "Учусь в школе",
      "Учусь в колледже или университете",
      "Работаю",
      "Совмещаю учёбу и работу",
      "Другое"
    ]
  },
  {
    id: 4,
    text: "Насколько вам интересны танцы?",
    type: "radio",
    required: true,
    options: [
      "Очень интересны",
      "Скорее интересны",
      "Нейтрально отношусь",
      "Скорее не интересны",
      "Совсем не интересны"
    ]
  },
  {
    id: 5,
    text: "Занимаетесь ли вы танцами сейчас?",
    type: "radio",
    required: true,
    options: [
      "Да, профессионально",
      "Да, в танцевальной студии",
      "Да, самостоятельно дома",
      "Раньше занимался(-ась), но сейчас нет",
      "Никогда не занимался(-ась)"
    ]
  },
  {
    id: 6,
    text: "Хотели бы вы научиться танцевать или улучшить свои навыки?",
    type: "radio",
    required: true,
    options: [
      "Да, очень хочу",
      "Скорее да",
      "Пока не знаю",
      "Скорее нет",
      "Нет"
    ]
  },
  {
    id: 7,
    text: "Какие танцевальные направления вам интересны?",
    type: "checkbox",
    required: false,
    options: [
      "Hip-hop",
      "Commercial dance",
      "Jazz-funk",
      "Contemporary",
      "K-pop",
      "Street dance",
      "Dancehall",
      "Другие"
    ]
  },
  {
    id: 8,
    text: "Пробовали ли вы когда-нибудь учить танцевальные движения по видео из интернета?",
    type: "radio",
    required: false,
    options: [
      "Да, часто",
      "Иногда",
      "Только несколько раз",
      "Нет, но хотел(-а) бы попробовать",
      "Нет, мне это неинтересно"
    ]
  },
  {
    id: 9,
    text: "Что может мешать вам заниматься танцами?",
    type: "checkbox",
    required: true,
    options: [
      "Нет времени",
      "Дорого посещать танцевальные студии",
      "Нет подходящих студий рядом",
      "Стесняюсь заниматься перед другими людьми",
      "Не хватает мотивации",
      "Сложно самостоятельно разучивать движения",
      "Ничего не мешает",
      "Другое"
    ]
  },
  {
    id: 10,
    text: "Насколько вам удобно было бы учиться танцевать самостоятельно через онлайн-платформу?",
    type: "radio",
    required: true,
    options: [
      "Очень удобно",
      "Скорее удобно",
      "Зависит от качества обучения",
      "Скорее неудобно",
      "Совсем неудобно"
    ]
  },
  {
    id: 11,
    text: "Какие возможности вы хотели бы видеть на танцевальной платформе?",
    type: "checkbox",
    required: true,
    options: [
      "Обучающие видео с разбором движений по шагам",
      "Простые хореографии для начинающих",
      "Хореографии разного уровня сложно��ти",
      "Возможность отслеживать свой прогресс",
      "Персональные рекомендации",
      "Обучение под популярную музыку",
      "Челленджи и танцевальные задания",
      "Обратная связь от преподавателей"
    ]
  },
  {
    id: 12,
    text: "Какой формат обучения вам больше нравится?",
    type: "radio",
    required: false,
    options: [
      "Короткие видео (до 5 минут)",
      "Подробные уроки (10–20 минут)",
      "Полноценные занятия (30–60 минут)",
      "Комбинация разных форматов"
    ]
  },
  {
    id: 13,
    text: "Как часто вы готовы заниматься на такой платформе?",
    type: "radio",
    required: false,
    options: [
      "Каждый день",
      "3–4 раза в неделю",
      "1–2 раза в неделю",
      "Несколько раз в месяц",
      "По настроению"
    ]
  },
  {
    id: 14,
    text: "Сколько вы готовы платить за доступ к такой платформе в месяц?",
    type: "radio",
    required: true,
    options: [
      "Предпочитаю полностью бесплатный доступ",
      "До 199 рублей",
      "200–399 рублей",
      "400–599 рублей",
      "600–999 рублей",
      "Более 1000 рублей"
    ]
  },
  {
    id: 15,
    text: "Насколько вероятно, что вы воспользовались бы платформой MOVEBOX?",
    type: "radio",
    required: true,
    options: [
      "Определённо воспользовался(-ась) бы",
      "Скорее воспользовался(-ась) бы",
      "Пока не уверен(-а)",
      "Скорее не воспользовался(-ась) бы",
      "Точно не воспользовался(-ась) бы"
    ]
  }
];

function addRevealAnimations() {
  const items = document.querySelectorAll('.reveal');

  if (!items.length || !('IntersectionObserver' in window)) {
    items.forEach((item) => item.classList.add('visible'));
    return;
  }

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    },
    { threshold: 0.18 }
  );

  items.forEach((item) => observer.observe(item));
}

function renderSurveyQuestions() {
  const questionsRoot = document.getElementById('questions');
  if (!questionsRoot) return;

  const html = surveyQuestions
    .map((question) => {
      const isRequired = question.required ? '<span class="required">*</span>' : '';
      const optionsHtml = question.options
        .map((option) => {
          const inputType = question.type === 'checkbox' ? 'checkbox' : 'radio';
          const name = `q${question.id}`;
          const requiredAttr = question.required && question.type === 'radio' ? 'required' : '';

          return `
            <label class="option">
              <input type="${inputType}" name="${name}" value="${option}" ${requiredAttr} />
              <span class="option-text">${option}</span>
            </label>
          `;
        })
        .join('');

      return `
        <fieldset class="question">
          <legend class="question-title">${question.id}. ${question.text} ${isRequired}</legend>
          <div class="option-list">${optionsHtml}</div>
        </fieldset>
      `;
    })
    .join('');

  questionsRoot.innerHTML = html;
}

function getAnsweredCount(form) {
  const controls = form.querySelectorAll('input[type="radio"], input[type="checkbox"]');
  return Array.from(controls).filter((input) => input.checked).length;
}

function updateProgress(form) {
  const total = surveyQuestions.length;
  const answered = getAnsweredCount(form);
  const progress = (answered / total) * 100;

  const progressBar = document.getElementById('progressBar');
  const progressPill = document.getElementById('progressPill');

  if (progressBar) {
    progressBar.style.width = `${progress}%`;
  }

  if (progressPill) {
    progressPill.textContent = `${Math.round((answered / total) * 15)} / 15`;
  }
}

function validateRequiredQuestions(form) {
  const seen = new Set();

  surveyQuestions.forEach((question) => {
    if (!question.required) return;

    const selected = form.querySelectorAll(`input[name="q${question.id}"]:checked`);
    if (selected.length === 0) {
      seen.add(question.id);
    }
  });

  if (seen.size) {
    const firstMissing = Math.min(...Array.from(seen));
    const target = form.querySelector(`input[name="q${firstMissing}"]`);
    target?.scrollIntoView({ behavior: 'smooth', block: 'center' });
    alert(`Пожалуйста, ответьте на обязательный вопрос ${firstMissing}.`);
    return false;
  }

  return true;
}

function buildAnswers(form) {
  const result = {};

  surveyQuestions.forEach((question) => {
    const selected = Array.from(form.querySelectorAll(`input[name="q${question.id}"]:checked`)).map(
      (input) => input.value
    );

    result[question.id] = selected.length > 1 || question.type === 'checkbox' ? selected : selected[0] || '';
  });

  return result;
}

function downloadCsv(payload) {
  const rows = [
    ['id', 'вопрос', 'ответ', 'время']
  ];

  Object.entries(payload).forEach(([key, value]) => {
    rows.push([
      key,
      surveyQuestions.find((question) => question.id === Number(key))?.text || '',
      Array.isArray(value) ? value.join('; ') : value,
      new Date().toISOString()
    ]);
  });

  const csv = rows
    .map((row) => row.map((cell) => `"${String(cell).replace(/"/g, '""')}"`).join(';'))
    .join('\n');

  const blob = new Blob(['\uFEFF' + csv], { type: 'text/csv;charset=utf-8;' });
  const url = URL.createObjectURL(blob);
  const link = document.createElement('a');
  link.href = url;
  link.download = 'movebox-answers.csv';
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
  URL.revokeObjectURL(url);
}

async function saveAnswersToGoogle(payload) {
  const scriptUrl = window.MOVEBOX_CONFIG?.googleScriptUrl;

  if (!scriptUrl || scriptUrl.includes('PASTE_')) {
    return false;
  }

  try {
    const response = await fetch(scriptUrl, {
      method: 'POST',
      mode: 'cors',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        source: 'movebox',
        submittedAt: new Date().toISOString(),
        answers: payload
      })
    });

    if (!response.ok) {
      throw new Error(`HTTP ${response.status}`);
    }

    return true;
  } catch (error) {
    console.warn('Google Apps Script save failed:', error);
    return false;
  }
}

function handleSurveySubmit(event) {
  event.preventDefault();
  const form = event.currentTarget;

  if (!validateRequiredQuestions(form)) {
    return;
  }

  const answers = buildAnswers(form);
  const payload = {
    submittedAt: new Date().toISOString(),
    answers
  };

  saveAnswersToGoogle(payload)
    .catch(() => false)
    .finally(() => {
      const thanks = document.getElementById('thankYou');
      const formBlock = document.getElementById('surveyForm');

      if (formBlock) formBlock.classList.add('hidden');
      if (thanks) thanks.classList.remove('hidden');

      localStorage.setItem('moveboxSurveyAnswers', JSON.stringify(payload));
      const csvButton = document.getElementById('downloadCsv');
      if (csvButton) {
        csvButton.addEventListener('click', () => downloadCsv(answers), { once: true });
      }
    });
}

function initSurveyPage() {
  const form = document.getElementById('surveyForm');
  if (!form) return;

  renderSurveyQuestions();
  updateProgress(form);

  form.addEventListener('change', () => updateProgress(form));
  form.addEventListener('submit', handleSurveySubmit);
}

document.addEventListener('DOMContentLoaded', () => {
  addRevealAnimations();
  initSurveyPage();
});

window.addEventListener('load', () => {
  const form = document.getElementById('surveyForm');
  if (form) {
    updateProgress(form);
  }
});

if (typeof window !== 'undefined') {
  window.MOVEBOX_CONFIG = window.MOVEBOX_CONFIG || {
    googleScriptUrl: ''
  };
}
