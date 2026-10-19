AJMAL'S CSP RECALL REVISION — 25-QUESTION WEB APP / PWA

This is a SEPARATE app from the Domain 1–7 revision game. Use a new GitHub repository (or a separate folder with its own Pages setup) to keep your existing app available.

GITHUB PAGES
1. Extract this ZIP on your computer.
2. Create a new repository for this recall app, for example csp-recall-revision.
3. Upload everything INSIDE the extracted folder to the repository root. Do not upload the ZIP or an outer enclosing folder. Include the sources folder.
4. index.html, app.js, engine.js, questions.js, style.css, sw.js and the other files must sit directly in the root. The original guide belongs at sources/recall-guide.pdf.
5. Commit the files. In Settings > Pages, deploy from your main branch and /(root).
6. Open the published HTTPS website URL. On a phone, use your browser's Install / Add to Home Screen option. On iPhone Safari, use Share > Add to Home Screen.

HOW TO PLAY
New Game selects up to 25 unanswered questions from this cycle. Topic coverage is balanced by choosing questions from topics visited least, with random choice among tied topics. All 206 guide questions, including its calculation questions, are included. The app preserves the guide's question wording and original option order.
Answers remain hidden until you select an option. Your first answer is locked. Correct/Incorrect, selected and correct options, original full recall note, topic and PDF source link appear. Tap Next Question. At the end, see score, percentage, wrong count and Review Wrong Answers.
A cycle normally has eight rounds of 25, then a final round of six. No answered question repeats before all questions have been covered. Once complete, explicitly choose Start a New Cycle. Questions are newly randomized in each cycle.
Home preserves an unfinished round. Resume restores both the question and any locked answer. Starting a new round before finishing prompts you; answered items stay covered, while unanswered items remain available. This may change the number of rounds needed for that cycle.
Wrong-answer review only revisits the last completed attempt. It does not change its score or mark new coverage. There is no automatic wrong-question repetition in regular rounds.

SAVED PROGRESS
Progress is saved in localStorage under ajmal-csp-recall-v1. It is separate from your old app's storage. It stays on the same device, browser and website address. Laptop and mobile do not sync. Clearing site data, using private browsing, or changing the website address can reset access to that saved progress. If storage is unavailable, the app displays a message.

SOURCE AND DATA
Only CSP_Recent_Exam_Recall_Master_Revision_Guide.pdf was used: 206 questions, four options each, 103 topics. Correct option letters were extracted from the PDF's red text, not inferred from outside knowledge. Full Recall note text supplies the explanation. Existing reconstructed/recalled questions in the guide are presented as guide questions, not independently verified verbatim exam items. No question, answer or explanation has been silently corrected. PDF headers, footers and line wrapping are removed; content wording is preserved.
questions.json is the structured database. questions.js exposes the same object as globalThis.RECALL_DATA so the static app also opens from local files. Fields include id, number, topic_id, topic, question, options, answer (zero-based), correct_answer (source letter), explanation, page, source_file and sourcePath. The engine and UI are separate. Keep both data files consistent when editing, and bump the cache version in sw.js after a change.

OFFLINE
The app caches its shell and question database after the first online visit. The PDF is cached separately after being opened online. Installation and offline caching require HTTPS (or localhost for development); file:// use can play questions but cannot register the service worker.

VALIDATION
100 simulated complete cycles (20,600 answers) passed: round sizes, uniqueness, all-question/topic coverage, new-cycle behavior, answer locking, scoring, resume and unfinished-round replacement. UI controls passed a DOM harness, including hidden answers, feedback, review, last results, final six-question round and coverage counters. Service-worker harness passed offline shell/data behavior, PDF caching and cache isolation. All 206 questions, 824 options and full notes matched the extracted PDF text. All correct-answer letters came directly from red-option metadata.
Real mobile visual layout, home-screen installation and device offline behavior were not verified in a browser here. Responsive mobile styles, large touch targets, focus states, readable text and reduced-motion support are implemented. Check those device behaviors after hosting.
