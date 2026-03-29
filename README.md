!DOCTYPE html
html lang=pl
head
    meta charset=UTF-8
    meta name=viewport content=width=device-width, initial-scale=1.0
    title🧠 Test Mózgu 3000title
    style
        @import url('httpsfonts.googleapis.comcss2family=Poppinswght@400;600&display=swap');
        
        body {
            font-family 'Poppins', sans-serif;
            background linear-gradient(135deg, #1e1e2e, #2a2a40);
            color #fff;
            margin 0;
            padding 20px;
        }
        .container {
            max-width 800px;
            margin 40px auto;
            background #161622;
            border-radius 20px;
            padding 30px;
            box-shadow 0 20px 40px rgba(0,0,0,0.3);
        }
        h1 {
            text-align center;
            margin-bottom 30px;
            font-size 2.5rem;
        }
        .question {
            background #22223a;
            padding 20px;
            margin-bottom 25px;
            border-radius 15px;
        }
        .question h3 {
            margin-top 0;
            color #00ffcc;
        }
        .option {
            display block;
            padding 12px 15px;
            margin 8px 0;
            background #2a2a40;
            border-radius 10px;
            cursor pointer;
            transition all 0.2s;
        }
        .optionhover {
            background #00ffcc;
            color #161622;
            transform translateX(5px);
        }
        input[type=radio] {
            margin-right 10px;
        }
        button {
            width 100%;
            padding 18px;
            font-size 1.3rem;
            background #00ffcc;
            color #161622;
            border none;
            border-radius 15px;
            cursor pointer;
            font-weight 600;
            margin-top 20px;
        }
        buttonhover {
            background #00ccaa;
            transform scale(1.03);
        }
        #result {
            margin-top 30px;
            padding 25px;
            background #1e1e2e;
            border-radius 15px;
            text-align center;
            font-size 1.4rem;
            display none;
        }
        .score {
            font-size 3rem;
            font-weight 600;
            color #00ffcc;
        }
    style
head
body
    div class=container
        h1🧠 Test Mózgu 3000h1
        p style=text-aligncenter; opacity0.7;Edytuj pytania w kodzie – zero stresup
        
        div id=quiz-containerdiv
        
        button onclick=submitQuiz()🚀 Sprawdź wynik!button
        
        div id=resultdiv
    div

    script
         ←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←←
         TUTAJ EDYTUJESZ PYTANIA – super łatwo!
        const questions = [
            {
                question Jak nazywa się stolica Francji,
                options [A) Berlin, B) Madryt, C) Paryż, D) Rzym],
                correct 2    0 = A, 1 = B, 2 = C, 3 = D
            },
            {
                question Ile to jest 2 + 2,
                options [A) 3, B) 4, C) 5, D) 22],
                correct 1
            },
            {
                question Kto napisał 'Dziady',
                options [A) Adam Mickiewicz, B) Juliusz Słowacki, C) Henryk Sienkiewicz, D) Bolesław Prus],
                correct 0
            },
            {
                question Jaki jest największy ocean na Ziemi,
                options [A) Atlantycki, B) Spokojny, C) Indyjski, D) Arktyczny],
                correct 1
            },
            {
                question Ile planet jest w Układzie Słonecznym (od 2006 roku),
                options [A) 8, B) 9, C) 10, D) 7],
                correct 0
            }
             Dodajesz kolejne pytania tak samo ↓
             { question Twoje pytanie, options [A) ..., B) ..., C) ..., D) ...], correct 2 }
        ];

         Renderowanie pytań
        function renderQuiz() {
            const container = document.getElementById('quiz-container');
            container.innerHTML = '';
            
            questions.forEach((q, index) = {
                const div = document.createElement('div');
                div.className = 'question';
                div.innerHTML = `
                    h3${index + 1}. ${q.question}h3
                    ${q.options.map((opt, i) = `
                        label class=option
                            input type=radio name=q${index} value=${i}
                            ${opt}
                        label
                    `).join('')}
                `;
                container.appendChild(div);
            });
        }

         Obliczanie wyniku
        function submitQuiz() {
            let score = 0;
            
            questions.forEach((q, index) = {
                const selected = document.querySelector(`input[name=q${index}]checked`);
                if (selected && parseInt(selected.value) === q.correct) {
                    score++;
                }
            });

            const percentage = Math.round((score  questions.length)  100);
            
             Śmieszne komentarze w zależności od wyniku
            let message = '';
            if (score === questions.length) message = 🏆 Absolutny geniusz! Mózg level over 9000!;
            else if (score = questions.length  0.8) message = 🔥 Prawie perfekt! Brakuje Ci tylko kawy i spokoju.;
            else if (score = questions.length  0.6) message = 👍 Całkiem nieźle! Jak na Polaka w niedzielę – brawo!;
            else if (score = questions.length  0.4) message = 😐 No... mogło być gorzej. Następnym razem dasz radę!;
            else message = 😅 Okej, chyba czas na kawę i powtórkę z podstawówki 😂;

            const resultDiv = document.getElementById('result');
            resultDiv.style.display = 'block';
            resultDiv.innerHTML = `
                div class=score${score}  ${questions.length}div
                p${percentage}% poprawnych odpowiedzip
                p${message}p
                button onclick=location.reload() style=margin-top20px; background#ff00aa; colorwhite; padding12px 30px; bordernone; border-radius10px; cursorpointer;
                    🔄 Zrób test jeszcze raz
                button
            `;
        }

         Start
        window.onload = renderQuiz;
    script
body
html
