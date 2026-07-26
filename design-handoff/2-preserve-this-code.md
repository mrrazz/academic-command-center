# Code to Preserve Exactly

Do not change any function names, data keys, or data content in these blocks.
Restyle the containers and surfaces. Keep everything below intact.

---

## KEY_TERMS (new — add this structure)

Add this array to the file. Mirror the QUIZ_BANK shape. Populate 3 placeholder terms per course. Real terms get added later.

```js
const KEY_TERMS = [
  { course: 'POL 211', terms: [
    { term: 'Federalism', definition: 'A system of government where power is divided between a central authority and constituent units.' },
    { term: 'Cloture', definition: 'A Senate procedure requiring 60 votes to end debate and force a vote on legislation.' },
    { term: 'Gerrymandering', definition: 'Drawing electoral district boundaries to favor a particular party or group.' }
  ]},
  { course: 'ECO 101', terms: [
    { term: 'Knowledge Capital', definition: 'The accumulated knowledge in a society generated through R&D and education that drives long-run growth.' },
    { term: 'Secular Stagnation', definition: 'A prolonged period of slow economic growth caused by chronically weak private demand.' },
    { term: 'Real GDP', definition: 'Gross domestic product adjusted for inflation, measuring actual changes in output.' }
  ]},
  { course: 'SOC 205', terms: [
    { term: 'Social Problem', definition: 'A condition that a significant number of people believe to be a problem requiring collective action.' },
    { term: 'Structural Racism', definition: 'Systemic policies and practices that produce racially disparate outcomes across institutions.' },
    { term: 'Conflict Theory', definition: 'A sociological perspective that views society as defined by conflict over scarce resources.' }
  ]},
  { course: 'BIO 109', terms: [
    { term: 'Homeostasis', definition: 'The tendency of a system to maintain internal stability despite external changes.' },
    { term: 'Mitosis', definition: 'Cell division producing two genetically identical daughter cells.' },
    { term: 'Ecosystem', definition: 'A community of living organisms interacting with their physical environment.' }
  ]},
  { course: 'PSY 240', terms: [
    { term: 'DSM-5', definition: 'The Diagnostic and Statistical Manual of Mental Disorders, 5th edition — the standard classification system for mental disorders.' },
    { term: 'Comorbidity', definition: 'The simultaneous presence of two or more disorders in a single individual.' },
    { term: 'Etiology', definition: 'The cause or origin of a disease or condition.' }
  ]}
];
```

---

## QUIZ_BANK (existing — do not change)

// ============================================
// QUIZ BANK
// ============================================
/*
  PROFESSOR-STYLE QUESTION RULES  (the "logic" EVERY quiz in this app follows)
  These are the universal tutor-testing guidelines — they apply to ALL courses
  (POL 211, SOC 205, ECO 101, BIO 109, PSY 240, and any added later), not just
  the course they were first modeled on. Originally derived from real POL 211
  (Prof. Shane Martin) quizzes. Whenever authoring or generating practice
  questions for ANY course, follow these rules so practice matches the real thing:

   0. ★ CARDINAL RULE — WORK FROM THE SOURCE, NO AD-LIBS. Whenever at all
      possible, draw BOTH the questions AND the answers from the provided
      textbook or supplied course material — not from general/background
      knowledge. The point of practice is to match the actual course, so the
      source text is the authority. Do NOT invent facts, questions, or answer
      choices. If the needed material isn't available, say so and mark the item
      as UNVERIFIED rather than guessing — an ad-libbed question is worse than
      no question. (Rules 7 and 9 are specific applications of this.)

   1. FIVE options (a–e), never four. Guessing odds are 20%, not 25%.
   2. Homogeneous distractors: every wrong answer is a real term from the
      SAME family as the right one (e.g. reapportionment / redistricting /
      gerrymandering / malapportionment all together). No throwaway options.
   3. Length-matched: the correct answer is NOT the longest / most detailed.
   4. Twin answers: include near-identical choices that differ by ONE precise
      word or a reordered phrase, to test exact recall.
   5. EXCEPT / negative stems on some items ("all of the following EXCEPT").
      Mark these with type:'except' so the UI can flag the word.
   6. Reasoning stems, not just definitions ("It is difficult to X because...").
   7. Textbook-anchored where possible ("According to the textbook, ...").
   8. Every item has a short `explain` so review teaches, not just scores.
   9. Grade to the COURSE'S OWN textbook/answer key, not outside nuance. (POL 211
      keys "racial" as the controversial gerrymandering answer even though racial
      gerrymandering is illegal — the textbook's answer wins.)

  DATA SHAPE — add more quizzes/courses by pushing objects with this shape:
   {
     id, course, name, topic,
     questions: [
       { q:'stem', type:'standard'|'except', options:[5 strings], answer:index0-4, explain:'why' }
     ]
   }
*/
const QUIZ_BANK = [
  {
    id: 'pol211-q5',
    course: 'POL 211',
    name: 'Quiz 5 — Congress',
    topic: 'The Legislative Branch',
    questions: [
      { q: 'The Constitution requires that all bills for raising revenue originate in:', type:'standard',
        options: ['The Senate', 'The House of Representatives', 'The Rules Committee', 'The Appropriations Committee', 'A joint session of Congress'],
        answer: 1, explain: '<strong>Article I, Section 7</strong> — revenue (tax) bills must begin in the House. The Senate may amend them, but cannot originate them.' },

      { q: 'Cloture, the procedure used to cut off a filibuster and end debate in the Senate, currently requires:', type:'standard',
        options: ['A simple majority of 51 votes', 'A two-thirds vote of those present', '60 votes (three-fifths of the full Senate)', 'A unanimous consent agreement', 'Approval of the Rules Committee'],
        answer: 2, explain: 'Under <strong>Senate Rule XXII</strong>, ending debate on legislation takes three-fifths of the full Senate = <strong>60 votes</strong>. Don\'t confuse with the two-thirds threshold used for treaties or overriding a veto.' },

      { q: 'Reapportionment refers to:', type:'standard',
        options: ['Redrawing district boundaries within a state', 'Reassigning members to new committees', 'The reallocation of House seats among the states after each census', 'Drawing districts to favor one political party', 'Adjusting the number of senators per state'],
        answer: 2, explain: '<strong>Reapportionment</strong> = redistributing the 435 House seats among the states by population every 10 years. Compare: <em>redistricting</em> (drawing the lines) and <em>gerrymandering</em> (drawing them to favor a group).' },

      { q: 'All of the following are powers exercised by the House of Representatives alone EXCEPT:', type:'except',
        options: ['Originating revenue bills', 'Bringing articles of impeachment', 'Choosing the president if no candidate wins an Electoral College majority', 'Confirming presidential appointments', 'Initiating the impeachment process'],
        answer: 3, explain: '<strong>Confirmation of appointments is a Senate power.</strong> Originating revenue bills, impeaching, and choosing the president in a deadlocked Electoral College all belong to the House.' },

      { q: 'The Speaker of the House is:', type:'standard',
        options: ['Elected by the full House and, by custom, the leader of the majority party', 'Appointed by the president', 'The longest-serving member of the majority party', 'Selected by the Rules Committee', 'Chosen by a joint session of Congress'],
        answer: 0, explain: 'The whole House formally elects the Speaker, but because the majority party has the votes, the Speaker is effectively the majority party\'s leader.' },

      { q: 'The "power of the purse" refers to Congress\'s constitutional authority to:', type:'standard',
        options: ['Declare war', 'Levy taxes and control federal spending', 'Confirm judicial appointments', 'Regulate interstate commerce', 'Override presidential vetoes'],
        answer: 1, explain: 'The <strong>power of the purse</strong> is Congress\'s control over taxing and spending — a central check on the executive branch.' },

      { q: 'A conference committee is best described as:', type:'standard',
        options: ['A standing committee that reviews the annual budget', 'A temporary joint committee that reconciles differing House and Senate versions of a bill', 'A committee that schedules debate on the floor', 'A select committee that investigates scandals', 'The Committee of the Whole'],
        answer: 1, explain: 'When the two chambers pass different versions of the same bill, a <strong>conference committee</strong> (members from both chambers) works out a single compromise version.' },

      { q: 'The advantages of incumbency in congressional elections are attributed to all of the following EXCEPT:', type:'except',
        options: ['Greater name recognition', 'Casework and constituency service', 'The franking privilege', 'Superior access to campaign funds', 'Constitutional term limits'],
        answer: 4, explain: 'There are <strong>no term limits</strong> on members of Congress — that would <em>reduce</em> incumbency, not cause it. The others all help incumbents win re-election.' },

      { q: 'According to the textbook, ______ gerrymandering has been struck down by the courts, while federal courts have declined to police ______ gerrymandering.', type:'standard',
        options: ['partisan; racial', 'racial; partisan', 'incumbent; geographic', 'geographic; incumbent', 'gender-based; racial'],
        answer: 1, explain: '<strong>Racial</strong> gerrymandering violates the 14th Amendment and Voting Rights Act. In <em>Rucho v. Common Cause</em> (2019) the Supreme Court held <strong>partisan</strong> gerrymandering claims are non-justiciable in federal court.' },

      { q: 'Congressional oversight is best defined as:', type:'standard',
        options: ['The power to declare laws unconstitutional', 'Congress\'s monitoring of the bureaucracy to ensure laws are carried out as intended', 'The Senate\'s review of treaties', 'The president\'s supervision of executive agencies', 'The Rules Committee\'s control over floor debate'],
        answer: 1, explain: '<strong>Oversight</strong> is Congress checking the executive branch and agencies — through hearings, investigations, and budget control — to make sure its laws are faithfully executed.' },

      { q: 'Giving each state two senators regardless of its population reflects the constitutional principle of:', type:'standard',
        options: ['Proportional representation', 'Equal representation of the states in the Senate', 'Descriptive representation', 'Substantive representation', 'Malapportionment'],
        answer: 1, explain: 'The <strong>Great (Connecticut) Compromise</strong> gave every state equal representation in the Senate and population-based representation in the House.' },

      { q: 'In the House, the committee that sets the terms of debate — time limits and whether amendments are allowed — is the:', type:'standard',
        options: ['Ways and Means Committee', 'Appropriations Committee', 'Rules Committee', 'Budget Committee', 'Committee of the Whole'],
        answer: 2, explain: 'The <strong>Rules Committee</strong> is powerful because it controls the conditions under which a bill reaches the floor — including how long it is debated and whether it can be amended.' },

      { q: 'A member of Congress who votes according to her own judgment of the national interest, even against constituents\' expressed wishes, is acting as a:', type:'standard',
        options: ['Delegate', 'Trustee', 'Whip', 'Politico', 'Partisan'],
        answer: 1, explain: 'A <strong>trustee</strong> uses independent judgment; a <strong>delegate</strong> mirrors constituents\' stated preferences; a <em>politico</em> blends both.' },

      { q: 'A treaty negotiated by the president takes effect only if it is approved by:', type:'standard',
        options: ['A simple majority of the House', 'A simple majority of the Senate', 'Two-thirds of the Senate', 'Two-thirds of both chambers', 'The Senate Foreign Relations Committee'],
        answer: 2, explain: '<strong>Article II</strong> — treaties require the advice and consent of <strong>two-thirds of the Senate</strong>. (Contrast the 60-vote cloture threshold and the simple majority for most legislation.)' },

      { q: 'The constitutional process for removing a federal official from office is:', type:'standard',
        options: ['The Senate impeaches and the House convicts', 'The House impeaches and the Senate tries and convicts', 'Either chamber may impeach and the Supreme Court convicts', 'The House impeaches and the Supreme Court convicts', 'A joint session votes to convict'],
        answer: 1, explain: 'The <strong>House impeaches</strong> (brings charges by majority vote); the <strong>Senate tries</strong> the case and convicts with a two-thirds vote.' },

      { q: 'The detailed work of gathering information, holding hearings, and revising legislation falls primarily to:', type:'standard',
        options: ['The Committee of the Whole', 'Standing committees', 'Conference committees', 'Party caucuses', 'The Rules Committee'],
        answer: 1, explain: '<strong>Standing committees</strong> are the permanent, subject-area workhorses of Congress where most bills are studied and marked up.' },

      { q: 'The single best explanation for the decline of bipartisan cooperation in Congress in recent decades is:', type:'standard',
        options: ['An increasing number of members who refuse to identify with either party', 'Rising party polarization and ideological sorting', 'The public paying less attention to Congress', 'The Supreme Court limiting congressional power', 'Recent reforms that weakened the filibuster'],
        answer: 1, explain: 'The parties have become more internally unified and further apart ideologically — <strong>polarization and hyperpartisanship</strong> — making cross-party deals harder.' },

      { q: 'The number of seats a state holds in the House of Representatives:', type:'standard',
        options: ['Is fixed at two per state', 'Is set by the state legislature', 'Is reapportioned according to population after each decennial census', 'Was permanently frozen by a constitutional amendment', 'Increases automatically at every election'],
        answer: 2, explain: 'Total House seats are capped at 435; how they are divided among the states is <strong>reapportioned every ten years</strong> based on the census.' },

      { q: 'The "necessary and proper" (elastic) clause gives Congress the power to:', type:'standard',
        options: ['Regulate commerce among the states', 'Make the laws needed to carry out its enumerated powers', 'Declare acts of the president unconstitutional', 'Override state constitutions at will', 'Levy any tax without limit'],
        answer: 1, explain: 'Article I, Section 8 — the <strong>elastic clause</strong> is the basis of Congress\'s <em>implied powers</em>, letting it pass laws needed to execute its listed powers.' },

      { q: 'The president\'s party usually loses seats in midterm elections; the size of that loss is most strongly associated with:', type:'standard',
        options: ['Whether the president campaigns nationally for candidates', 'The president\'s approval rating and the state of the economy', 'How the Supreme Court has ruled on the president\'s policies', 'Whether the president\'s party controls both chambers', 'The number of open (retirement) seats that cycle'],
        answer: 1, explain: 'Midterm losses track the <strong>president\'s standing with the public</strong> and <strong>the economy</strong> — the two dominate the size of the swing.' }
    ]
  },
  {
    id: 'eco101-ch21',
    course: 'ECO 101',
    name: 'Ch 21 Review — Economic Growth',
    topic: 'Long-Run Economic Growth (practice, source-grounded)',
    questions: [
      { q: 'In the theory of economic growth, "knowledge capital" is best defined as:', type:'standard',
        options: ['The accumulated knowledge available to a society, generated largely through research and development and education', 'The total value of a firm\'s patents and copyrights as recorded on its balance sheet', 'The physical machinery and equipment used to produce new technology', 'The financial capital firms raise specifically to fund research', 'The stock of skilled workers a single firm employs in a given year'],
        answer: 0, explain: 'In endogenous growth theory, <strong>knowledge capital</strong> is the accumulated knowledge from R&D and education, treated as a factor of production. Unlike physical capital it is <em>non-rival</em> — many firms can use the same idea at once — which is why it drives long-run growth.' },

      { q: 'Firms tend to invest LESS than the socially optimal amount in research and development mainly because:', type:'standard',
        options: ['Competing firms often capture much of the return from one firm\'s research, so private benefits fall short of social benefits', 'The private benefits of research usually exceed its social benefits', 'Patents let a single firm capture all of the returns from its research', 'Government subsidies make private research unnecessary', 'Corporate income taxes on research profits have been eliminated'],
        answer: 0, explain: 'R&D creates <strong>positive externalities (spillovers)</strong>: rivals imitate or build on new knowledge, so <strong>social benefit &gt; private benefit</strong>. Weighing only its private return, the firm underinvests.' },

      { q: 'Which set of government policies would most likely increase the accumulation of knowledge capital?', type:'standard',
        options: ['Protect intellectual property, subsidize R&D, and subsidize education', 'Protect intellectual property, subsidize R&D, and restrict the entry of foreign firms', 'Subsidize education, restrict foreign firms, and raise corporate taxes', 'Restrict foreign firms and eliminate patents to speed the spread of ideas', 'Subsidize R&D only, since education has no effect on knowledge capital'],
        answer: 0, explain: 'Patents/copyrights restore the incentive to innovate, R&D subsidies offset the underinvestment problem, and education subsidies build the human capital that produces new knowledge. <strong>Restricting foreign firms does NOT build knowledge capital</strong> — it cuts the flow of ideas and competition.' },

      { q: 'When economists describe secular stagnation as "structurally low private demand," they are pointing to:', type:'standard',
        options: ['A persistent shortfall of investment demand relative to saving', 'A temporary drop in consumer confidence following a recession', 'A shift of consumer spending from domestic goods toward imports', 'A decline in government spending on infrastructure', 'A rapid rise in demand for new consumer technology'],
        answer: 0, explain: '<strong>Secular stagnation</strong> is fundamentally a chronic <em>excess of saving over investment</em> — private demand stays weak because investment demand is structurally insufficient. It is not a confidence, imports, or government-spending story.' },

      { q: 'Why might structurally low private demand result in secular stagnation?', type:'standard',
        options: ['Persistently weak private demand keeps the economy below potential, producing sustained slow growth', 'Weak private demand raises inflation, which erodes future demand', 'Weak private demand forces exports down, reducing output', 'Weak private demand forces the government to cut spending', 'Weak private demand always triggers a financial crisis'],
        answer: 0, explain: '<strong>Secular stagnation literally means a prolonged period of slow growth.</strong> Chronically weak private demand keeps output below potential year after year — that sustained shortfall <em>is</em> the stagnation.' },

      { q: 'Which of the following are "deep structural factors" that could push the U.S. economy toward secular stagnation? I. People living longer and saving more for retirement. II. Slower population growth reducing investment demand. III. High-tech firms that require less physical capital.', type:'standard',
        options: ['I, II, and III', 'I and II only', 'I and III only', 'II and III only', 'I only'],
        answer: 0, explain: 'All three push saving up or investment demand down: longer lives → more saving; slower population growth → less need for new capital/housing; modern tech firms need <strong>less</strong> physical capital, driving down investment demand. Together they depress private demand.' },

      { q: 'The Roman Empire built aqueducts that lasted centuries yet had near-zero growth in income per capita. The precondition for sustained growth it most clearly lacked was:', type:'standard',
        options: ['Continuous technological change', 'Property rights', 'The rule of law', 'A stable currency', 'An educated elite'],
        answer: 0, explain: 'Rome\'s engineering feats were <strong>one-time</strong> achievements, not a process of <em>continuous</em> innovation. Sustained growth requires ongoing technological change that keeps raising productivity — episodic brilliance is not enough.' },

      { q: 'If the Roman Empire had achieved sustained economic growth beginning roughly 2,000 years ago, today\'s standard of living would most likely be:', type:'standard',
        options: ['Substantially higher, because growth compounds over time', 'Slightly higher than it is now', 'About the same as it is now', 'Lower, because natural resources would be exhausted', 'Impossible to compare in any way'],
        answer: 0, explain: 'Because growth <strong>compounds</strong>, even a modest sustained rate maintained over ~2,000 years would produce an enormous cumulative increase — living standards today would be <strong>substantially higher</strong>.' },

      { q: 'When a central bank forecasts that GDP will "grow by 2.3 percent this year," it is almost certainly referring to:', type:'standard',
        options: ['Real GDP, because growth figures are meant to capture changes in output, not prices', 'Nominal GDP, because readers care more about inflation than output', 'Real GDP, because nominal GDP cannot be forecast', 'Nominal GDP, because that is the convention among journalists', 'Either one, since they grow at the same rate'],
        answer: 0, explain: 'A GDP <em>growth</em> figure is meant to measure changes in actual <strong>output</strong>, so it strips out price changes — that is exactly what <strong>real GDP</strong> does.' },

      { q: 'If a country\'s real GDP is projected to grow 2.3% while its population is still growing, real GDP per capita will:', type:'standard',
        options: ['Grow more slowly than 2.3%', 'Grow more quickly than 2.3%', 'Grow at exactly 2.3%', 'Fall, regardless of the population growth rate', 'Be impossible to estimate without exact population figures'],
        answer: 0, explain: 'Per capita growth ≈ real GDP growth − population growth. As long as population is rising, per capita GDP expands <strong>more slowly</strong> than total real GDP. (You don\'t need the exact population to know the direction.)' },

      { q: 'With real GDP forecast to grow 2.3%, living standards — real GDP per capita — in that country:', type:'standard',
        options: ['Definitely fell if population grew faster than 2.3%, and definitely rose if population grew slower than 2.3%', 'Definitely rose as long as real GDP growth was positive', 'Definitely fell if the population grew at all that year', 'Definitely rose if population grew faster than 2.3%', 'Cannot be judged without knowing nominal GDP'],
        answer: 0, explain: 'Living standards = real GDP <strong>per capita</strong>. With real GDP up 2.3%: if population grew faster than 2.3%, per-capita growth is negative (fell); if slower, it is positive (rose). Positive real GDP growth alone is <em>not</em> enough.' },

      { q: 'When the volume of world trade declines, the people and industries hurt the MOST are likely to be:', type:'standard',
        options: ['Labor-intensive export industries in developing nations', 'Labor-intensive export industries in developed nations', 'Capital-intensive export industries in developing nations', 'Import-competing industries in developed nations', 'No one, since consumers simply buy domestic goods'],
        answer: 0, explain: 'Developing nations\' comparative advantage is in <strong>labor-intensive</strong> goods they export to developed nations. Shrinking trade removes the export markets those industries depend on, so they lose the most.' },

      { q: 'Which group tends to BENEFIT when world trade declines?', type:'standard',
        options: ['Domestic industries that compete with imports, because they face less foreign competition', 'Domestic industries that primarily export, because prices rise', 'All domestic firms, without exception', 'Foreign exporters, because scarcity raises their prices', 'No one benefits when trade declines'],
        answer: 0, explain: 'Trade always creates winners and losers. When trade falls, <strong>import-competing</strong> domestic industries gain from reduced foreign competition. Domestic <em>exporters</em>, by contrast, are hurt.' },

      { q: 'The personal benefit you get from a free Google search is generally NOT counted in GDP because:', type:'standard',
        options: ['GDP measures the market value of goods and services people pay for, and the search is free', 'Google keeps its search data proprietary', 'Google\'s advertising profit is excluded from GDP', 'Search benefits are counted, but under investment rather than consumption', 'The information has no real economic value'],
        answer: 0, explain: 'GDP captures only <strong>priced market transactions</strong>. Because you pay nothing for the search, the value you receive (consumer surplus) is diffused through the economy and goes largely uncounted — Manyika\'s point: "we have all these benefits but we\'re not paying for them."' },

      { q: 'The argument that the recent U.S. productivity slowdown "is really a measurement problem" is supported by the observation that:', type:'standard',
        options: ['Real but unpriced benefits from free digital services are hard to measure and go largely uncounted in GDP', 'Freed-up time from digital tools is already fully captured in productivity data', 'Google discloses all of its data, so nothing is missed', 'Productivity is measured perfectly, so the slowdown must be genuine', 'Digital services are counted twice, overstating productivity'],
        answer: 0, explain: 'If real gains from free/unpriced digital services aren\'t showing up in GDP, then measured productivity <strong>understates</strong> true productivity — so the slowdown may be mismeasurement. This is consistent with the free-search answer above.' },

      { q: 'Colaba plans to hire more workers to meet rising demand for its product. Christopher argues this will only raise the wage bill and cut profits. Which fact would MOST weaken his argument?', type:'standard',
        options: ['Colaba recently restructured its shop floor, shortening the production cycle and cutting defective units', 'Colaba already uses an efficient assembly-line method it adopted years ago', 'The distribution network for the product is highly fragmented', 'Turnover on Colaba\'s R&D team is above the industry average', 'Colaba\'s earnings growth has slowed over the last few quarters'],
        answer: 0, explain: 'Rising <strong>labor productivity</strong> is what makes added workers profitable rather than pure cost. Only the shop-floor improvement shows workers now producing more sellable output; the efficient assembly line is a pre-existing static fact, and the rest are neutral or strengthen his case.' }
    ]
  }
];

// ============================================
// STUDY RESOURCES  (reference material embedded in the app — non-quiz)
// ============================================
/*
  Study resources are read-only reference content shown on the Study page below
  the quizzes. Add PRACTICE material we author here with the shape:
  { id, course, name, kind, tag, chapters:[{ n, qs:[strings] }] }.

  IMPORTANT (privacy rule): real course-provided material — exam questions,
  the professor's actual assignment/chapter questions, anything literally from
  the course — must NOT live here, because this repo is PUBLIC. Keep that
  content LOCAL only (see ~/Downloads study folder). This array holds
  practice-only content. (SOC 205 chapter questions were removed 2026-07-02.)
*/
const STUDY_RESOURCES = [];

---

## Study + Quiz Functions (existing — do not change)

function renderStudy() {
  closeQuiz();
  const listEl = document.getElementById('quiz-list');
  document.getElementById('study-sub').textContent = "Practice quizzes & study resources";

  let html = '';

  // ---- Practice quizzes (interactive MC) ----
  html += `<div class="section-label">📝 Practice Quizzes</div>`;
  if (!QUIZ_BANK.length) {
    html += `<div class="card" style="text-align:center; color:var(--text2);">No practice quizzes yet.</div>`;
  } else {
    const byCourse = {};
    QUIZ_BANK.forEach(qz => { (byCourse[qz.course] = byCourse[qz.course] || []).push(qz); });
    Object.keys(byCourse).forEach(course => {
      byCourse[course].forEach(qz => {
        const best = state.quizScores?.[qz.id];
        const total = qz.questions.length;
        const bestPct = best != null ? Math.round((best / total) * 100) : null;
        const bestColor = bestPct == null ? 'var(--text3)' : bestPct >= 80 ? 'var(--green)' : bestPct >= 60 ? 'var(--yellow)' : 'var(--red)';
        html += `
          <div class="quiz-card" onclick="openQuiz('${qz.id}')" style="cursor:pointer; border-left:3px solid ${courseColor(course)};">
            <div class="quiz-card-head">
              <div>
                <div class="quiz-card-title">${course} · ${qz.name}</div>
                <div class="quiz-card-sub">${qz.topic}</div>
              </div>
              <div class="quiz-best" style="color:${bestColor};">${best != null ? best + '/' + total : '—'}</div>
            </div>
            <div class="quiz-meta">${total} questions · 5 options each${bestPct != null ? ' · best ' + bestPct + '%' : ' · not attempted'}</div>
          </div>`;
      });
    });
  }

  // ---- Study resources (read-only reference: chapter questions, guides) ----
  if (typeof STUDY_RESOURCES !== 'undefined' && STUDY_RESOURCES.length) {
    html += `<div class="section-label" style="margin-top:12px;">📄 Study Resources</div>`;
    STUDY_RESOURCES.forEach(r => {
      const nq = r.chapters.reduce((s, c) => s + c.qs.length, 0);
      html += `
        <div class="quiz-card" onclick="toggleResource('${r.id}')" style="cursor:pointer; border-left:3px solid ${courseColor(r.course)};">
          <div class="quiz-card-head">
            <div>
              <div class="quiz-card-title">${r.course} · ${r.name}</div>
              <div class="quiz-card-sub">${r.kind}${r.tag ? ' · ' + r.tag : ''}</div>
            </div>
            <div class="quiz-best" id="res-caret-${r.id}" style="color:var(--text3);">▸</div>
          </div>
          <div class="quiz-meta">${r.chapters.length} chapters · ${nq} questions</div>
          <div id="res-body-${r.id}" style="display:none; margin-top:10px;" onclick="event.stopPropagation()">${renderResourceBody(r)}</div>
        </div>`;
    });
  }

  listEl.innerHTML = html;
}

function renderResourceBody(r) {
  return r.chapters.map(c => `
    <div style="margin-bottom:12px;">
      <div style="font-weight:700; font-size:13px; color:var(--text); margin-bottom:6px; font-family:'JetBrains Mono',monospace;">Chapter ${c.n}</div>
      <ol style="margin:0; padding-left:18px; color:var(--text2); font-size:13px; line-height:1.55;">
        ${c.qs.map(q => `<li style="margin-bottom:5px;">${q}</li>`).join('')}
      </ol>
    </div>`).join('');
}

function toggleResource(id) {
  const body = document.getElementById('res-body-' + id);
  const caret = document.getElementById('res-caret-' + id);
  if (!body) return;
  const open = body.style.display !== 'none';
  body.style.display = open ? 'none' : 'block';
  if (caret) caret.textContent = open ? '▸' : '▾';
}

function shuffle(arr) {
  for (let i = arr.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[j]] = [arr[j], arr[i]];
  }
  return arr;
}

function openQuiz(id) {
  activeQuiz = QUIZ_BANK.find(q => q.id === id);
  if (!activeQuiz) return;
  quizOrder = shuffle(activeQuiz.questions.map((_, i) => i));
  quizAnswers = quizOrder.map(() => null);
  quizGraded = false;

  document.getElementById('quiz-list').style.display = 'none';
  document.getElementById('quiz-runner').style.display = 'block';
  document.getElementById('quiz-back-btn').style.display = 'inline-block';
  document.getElementById('study-sub').textContent = activeQuiz.name;
  document.getElementById('quiz-result-wrap').innerHTML = '';
  document.getElementById('quiz-submit-wrap').style.display = 'flex';
  renderQuizQuestions();
  window.scrollTo(0, 0);
}

function closeQuiz() {
  activeQuiz = null; quizGraded = false;
  const runner = document.getElementById('quiz-runner');
  const list = document.getElementById('quiz-list');
  const back = document.getElementById('quiz-back-btn');
  if (runner) runner.style.display = 'none';
  if (list) list.style.display = 'block';
  if (back) back.style.display = 'none';
}

const LETTERS = ['a', 'b', 'c', 'd', 'e'];

function renderQuizQuestions() {
  let html = '';
  quizOrder.forEach((qi, displayIdx) => {
    const item = activeQuiz.questions[qi];
    const sel = quizAnswers[displayIdx];
    let stem = item.q;
    if (item.type === 'except') stem = stem.replace(/\bEXCEPT\b/, '<span class="except">EXCEPT</span>');

    html += `<div class="q-block">
      <div class="q-num">QUESTION ${displayIdx + 1}</div>
      <div class="q-stem">${stem}</div>`;

    item.options.forEach((opt, oi) => {
      let cls = 'opt';
      if (quizGraded) {
        cls += ' locked';
        if (oi === item.answer) cls += ' correct';
        else if (oi === sel) cls += ' wrong';
      } else if (oi === sel) {
        cls += ' selected';
      }
      const click = quizGraded ? '' : ` onclick="selectOption(${displayIdx}, ${oi})"`;
      html += `<div class="${cls}"${click}>
          <span class="opt-letter">${LETTERS[oi]}</span>
          <span>${opt}</span>
        </div>`;
    });

    if (quizGraded) {
      html += `<div class="q-explain"><strong>${sel === item.answer ? '✓ Correct.' : (sel == null ? '○ Skipped.' : '✕ Not quite.')}</strong> ${item.explain}</div>`;
    }
    html += `</div>`;
  });
  document.getElementById('quiz-questions').innerHTML = html;
  updateQuizProgress();
}

function selectOption(displayIdx, oi) {
  if (quizGraded) return;
  quizAnswers[displayIdx] = oi;
  renderQuizQuestions();
}

function updateQuizProgress() {
  const answered = quizAnswers.filter(a => a != null).length;
  const pct = Math.round((answered / quizAnswers.length) * 100);
  document.getElementById('quiz-progress-fill').style.width = pct + '%';
}

function submitQuiz() {
  const unanswered = quizAnswers.filter(a => a == null).length;
  if (unanswered > 0 && !quizGraded) {
    if (!confirm(`${unanswered} question${unanswered > 1 ? 's' : ''} still blank. Grade anyway?`)) return;
  }
  quizGraded = true;

  let correct = 0;
  quizOrder.forEach((qi, displayIdx) => {
    if (quizAnswers[displayIdx] === activeQuiz.questions[qi].answer) correct++;
  });
  const total = quizOrder.length;
  const pct = Math.round((correct / total) * 100);

  // persist best score
  if (!state.quizScores) state.quizScores = {};
  if (state.quizScores[activeQuiz.id] == null || correct > state.quizScores[activeQuiz.id]) {
    state.quizScores[activeQuiz.id] = correct;
    saveState();
  }

  const color = pct >= 80 ? 'var(--green)' : pct >= 60 ? 'var(--yellow)' : 'var(--red)';
  const msg = pct >= 80 ? 'Solid — you\'re quiz-ready.' : pct >= 60 ? 'Getting there. Review the misses below.' : 'Keep drilling — read the explanations under each miss.';
  document.getElementById('quiz-submit-wrap').style.display = 'none';
  document.getElementById('quiz-result-wrap').innerHTML = `
    <div class="quiz-result">
      <div class="quiz-score-big" style="color:${color};">${correct}/${total}</div>
      <div class="quiz-score-pct">${pct}% · ${msg}</div>
    </div>
    <div class="quiz-actions">
      <button class="btn" onclick="openQuiz('${activeQuiz.id}')">↻ Retake (reshuffle)</button>
      <button class="btn btn-primary" onclick="renderStudy()">✓ Done</button>
    </div>`;

  renderQuizQuestions();
  window.scrollTo(0, 0);
}

loadState();
initFiles();
renderDashboard();
updateClock();
setInterval(updateClock, 60000);
if(document.getElementById("all-grades-list")) renderGrades();
updateGradeCategories();

if ('serviceWorker' in navigator) {
  navigator.serviceWorker.register('/sw.js');
}
</script>
</body>
</html>
