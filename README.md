<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calendário Anual de Jovens</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
            color: #333;
        }

        header {
            background-color: #3f51b5;
            color: #fff;
            text-align: center;
            padding: 20px 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        header h1 {
            margin: 0;
        }

        .container {
            padding: 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .month {
            background-color: #ffffff;
            margin-bottom: 20px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            overflow: hidden;
        }

        .month-header {
            background-color: #3f51b5;
            color: white;
            padding: 10px 15px;
            font-size: 1.2em;
        }

        .month-body {
            padding: 15px;
            line-height: 1.6;
        }

        .event {
            margin: 10px 0;
            padding: 10px;
            background-color: #e8f0fe;
            border-left: 5px solid #3f51b5;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
            text-decoration: none;
            color: inherit;
            display: block;
        }

        .event:hover {
            background-color: #d3e2fd;
        }

        .event-title {
            font-weight: bold;
            margin-bottom: 5px;
        }

        .event-date {
            font-size: 0.9em;
            color: #555;
        }

        footer {
            text-align: center;
            margin: 20px 0;
            font-size: 0.8em;
            color: #777;
        }
    </style>
</head>
<body>
    <header>
        <h1>Calendário Anual de Jovens</h1>
    </header>
    <div class="container" id="calendar-container">
        <!-- O conteúdo será adicionado dinamicamente pelo JavaScript -->
    </div>
    <footer>
        &copy; 2025 Ministério Jovem
    </footer>

    <script>
        // Dados do calendário
        const calendarData = {
            "Janeiro": [
                { title: "Encontro de Líderes", date: "18 de Janeiro", link: "#" },
                { title: "Culto de Jovens (Concentração de Jovens)", date: "Último Sábado", link: "#" }
            ],
            "Fevereiro": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: '"Aquece Graça" – Preparação para o evento "Graça Brasil"', date: "Último Sábado", link: "#" }
            ],
            "Março": [
                { title: 'Evento "Graça Brasil"', date: "1 a 3 de Março", link: "#" },
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Culto de Jovens (Concentração de Jovens)", date: "Último Sábado", link: "#" }
            ],
            "Abril": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Evento: Lava Jato Beneficente", date: "Data a definir", link: "#" }
            ],
            "Maio": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Culto de Jovens (Concentração de Jovens)", date: "Último Sábado", link: "#" }
            ],
            "Junho": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Evento: Tropeiro Beneficente (pode ser em formato de Arraiá)", date: "Data a definir", link: "#" }
            ],
            "Julho": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Culto de Jovens (Concentração de Jovens)", date: "Último Sábado", link: "#" },
                { title: "Evento: Cine Pipoca", date: "Data a definir", link: "#" }
            ],
            "Agosto": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Evento: Workshop de Capacitação", date: "Data a definir", link: "#" }
            ],
            "Setembro": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Culto de Jovens (Concentração de Jovens)", date: "Último Sábado", link: "#" },
                { title: "Evento: Festival de Churrasco", date: "Data a definir", link: "#" }
            ],
            "Outubro": [
                { title: "Consagração", date: "1º Sábado", link: "#" }
            ],
            "Novembro": [
                { title: "Consagração", date: "1º Sábado", link: "#" },
                { title: "Festa Regional de Jovens", date: "Último Sábado", link: "#" }
            ],
            "Dezembro": [
                { title: "Consagração", date: "1º Sábado", link: "#" }
            ]
        };

        // Renderiza o calendário no container
        const calendarContainer = document.getElementById("calendar-container");

        Object.keys(calendarData).forEach(month => {
            const monthDiv = document.createElement("div");
            monthDiv.className = "month";

            const monthHeader = document.createElement("div");
            monthHeader.className = "month-header";
            monthHeader.textContent = month;

            const monthBody = document.createElement("div");
            monthBody.className = "month-body";

            calendarData[month].forEach(event => {
                const eventLink = document.createElement("a");
                eventLink.href = event.link;
                eventLink.className = "event";

                const eventTitle = document.createElement("div");
                eventTitle.className = "event-title";
                eventTitle.textContent = event.title;

                const eventDate = document.createElement("div");
                eventDate.className = "event-date";
                eventDate.textContent = event.date;

                eventLink.appendChild(eventTitle);
                eventLink.appendChild(eventDate);
                monthBody.appendChild(eventLink);
            });

            monthDiv.appendChild(monthHeader);
            monthDiv.appendChild(monthBody);
            calendarContainer.appendChild(monthDiv);
        });
    </script>
</body>
</html>
