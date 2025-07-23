<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Infografía: Evaluación Formativa y Sumativa - Altamira International School</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;900&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #F1F5F9;
        }
        .chart-container {
            position: relative;
            margin: auto;
            height: 250px;
            width: 100%;
            max-width: 350px;
        }
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        .modal-overlay.show {
            opacity: 1;
            visibility: visible;
        }
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 1rem;
            max-width: 90%;
            max-height: 90%;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            transform: translateY(-20px);
            transition: transform 0.3s ease;
        }
        .modal-overlay.show .modal-content {
            transform: translateY(0);
        }
        .close-button {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #334155;
        }
        .loading-spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #36B1BF;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
            margin: 20px auto;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="text-slate-700">

    <div class="container mx-auto p-4 md:p-8">

        <header class="text-center mb-12">
            <h1 class="text-4xl md:text-5xl font-black text-slate-800">Evaluación en Altamira International School</h1>
            <p class="text-lg md:text-xl text-slate-600 mt-2">Comprendiendo la Evaluación Formativa y Sumativa</p>
        </header>

        <main class="grid grid-cols-1 lg:grid-cols-2 gap-8">

            <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8 border-l-8 border-[#F5A503]">
                <div class="flex justify-between items-center mb-4">
                    <h2 class="text-3xl font-bold text-[#F5A503]">Evaluación Formativa</h2>
                    <button class="bg-[#F5A503] text-white px-4 py-2 rounded-full font-bold hover:bg-[#F2385A] transition-colors" onclick="openModal('evaluacion-formativa')">Más Información ✨</button>
                </div>
                <p class="mb-6 text-lg">La evaluación formativa es el corazón de nuestro proceso de aprendizaje. Es la evaluación **PARA** el aprendizaje, un acompañamiento continuo que guía y mejora el progreso del estudiante.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="bg-slate-50 rounded-xl p-4">
                        <h3 class="text-xl font-bold mb-2">Propósito:</h3>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Acompañar y guiar el aprendizaje.</li>
                            <li>Proporcionar retroalimentación oportuna.</li>
                            <li>Identificar fortalezas y áreas de mejora.</li>
                        </ul>
                    </div>
                    <div class="bg-slate-50 rounded-xl p-4">
                        <h3 class="text-xl font-bold mb-2">Características:</h3>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Proceso continuo.</li>
                            <li>No tiene valor porcentual directo.</li>
                            <li>"Entrenamientos intencionales".</li>
                        </ul>
                    </div>
                </div>
                <h3 class="text-xl font-bold mt-6 mb-2">Ejemplos:</h3>
                <ul class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-base">
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Observaciones en clase</li>
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Debates y discusiones</li>
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Proyectos en curso</li>
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Quizzes cortos</li>
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Autoevaluaciones</li>
                    <li class="flex items-center"><span class="text-[#F5A503] mr-2">💡</span> Coevaluaciones</li>
                </ul>
            </div>

            <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8 border-l-8 border-[#36B1BF]">
                <div class="flex justify-between items-center mb-4">
                    <h2 class="text-3xl font-bold text-[#36B1BF]">Evaluación Sumativa</h2>
                    <button class="bg-[#36B1BF] text-white px-4 py-2 rounded-full font-bold hover:bg-[#4AD9D9] transition-colors" onclick="openModal('evaluacion-sumativa')">Más Información ✨</button>
                </div>
                <p class="mb-6 text-lg">La evaluación sumativa es la evaluación **DEL** aprendizaje. Se realiza al final de un período de instrucción para determinar el nivel de logro de los objetivos.</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <div class="bg-slate-50 rounded-xl p-4">
                        <h3 class="text-xl font-bold mb-2">Propósito:</h3>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Determinar el nivel de logro final.</li>
                            <li>Certificar el aprendizaje.</li>
                            <li>Informar sobre el progreso total.</li>
                        </ul>
                    </div>
                    <div class="bg-slate-50 rounded-xl p-4">
                        <h3 class="text-xl font-bold mb-2">Características:</h3>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Se realiza al final de una unidad/período.</li>
                            <li>Tiene valor porcentual en la calificación.</li>
                            <li>Se basa en comprensión y aplicación.</li>
                        </ul>
                    </div>
                </div>
                <h3 class="text-xl font-bold mt-6 mb-2">Ejemplos:</h3>
                <ul class="grid grid-cols-1 sm:grid-cols-2 gap-2 text-base">
                    <li class="flex items-center"><span class="text-[#36B1BF] mr-2">📝</span> Exámenes finales de unidad</li>
                    <li class="flex items-center"><span class="text-[#36B1BF] mr-2">📝</span> Presentaciones de proyectos terminados</li>
                    <li class="flex items-center"><span class="text-[#36B1BF] mr-2">📝</span> Ensayos finales</li>
                    <li class="flex items-center"><span class="text-[#36B1BF] mr-2">📝</span> Portafolios de trabajo</li>
                    <li class="flex items-center"><span class="text-[#36B1BF] mr-2">📝</span> Pruebas estandarizadas</li>
                </ul>
            </div>

            <div class="lg:col-span-2 bg-white rounded-2xl shadow-lg p-6 md:p-8 border-l-8 border-[#4AD9D9]">
                <div class="flex justify-between items-center mb-4">
                    <h2 class="text-3xl font-bold text-[#4AD9D9]">La Sinergia de la Evaluación</h2>
                    <button class="bg-[#4AD9D9] text-white px-4 py-2 rounded-full font-bold hover:bg-[#36B1BF] transition-colors" onclick="openModal('sinergia-evaluacion')">Más Información ✨</button>
                </div>
                <p class="mb-6 text-lg text-center">En Altamira International School, entendemos que la combinación de la evaluación formativa y sumativa es esencial para un proceso de aprendizaje integral y efectivo.</p>
                <div class="flex flex-col md:flex-row items-center justify-center gap-8">
                    <div class="chart-container">
                        <canvas id="evaluacionBalanceChart"></canvas>
                    </div>
                    <div class="text-lg max-w-md">
                        <p class="mb-4">La evaluación formativa alimenta y moldea el aprendizaje, mientras que la sumativa certifica los logros alcanzados. Ambas son indispensables para valorar no solo lo que los estudiantes saben, sino también cómo aplican y transforman ese conocimiento.</p>
                        <p class="font-bold text-[#4AD9D9]">Un equilibrio dinámico para el desarrollo integral de nuestros estudiantes.</p>
                    </div>
                </div>
            </div>

        </main>

        <footer class="text-center mt-12 text-slate-500 text-sm">
            <p>Esta infografía es un resumen de la Política de Evaluación de Altamira International School, alineada con el Decreto 1075 de 2015.</p>
            <p>Para detalles completos, consulte el documento oficial de la política.</p>
        </footer>

    </div>

    <!-- Modal Structure -->
    <div id="infoModal" class="modal-overlay">
        <div class="modal-content">
            <button class="close-button" onclick="closeModal()">×</button>
            <h3 id="modalTitle" class="text-2xl font-bold text-slate-800 mb-4"></h3>
            <div id="modalContent" class="text-lg text-slate-700">
                <div class="loading-spinner"></div>
            </div>
        </div>
    </div>

    <script>
        const ctxBalance = document.getElementById('evaluacionBalanceChart');

        new Chart(ctxBalance, {
            type: 'doughnut',
            data: {
                labels: ['Evaluación Formativa', 'Evaluación Sumativa'],
                datasets: [{
                    label: 'Balance de Evaluación',
                    data: [60, 40], /* Representación conceptual del peso */
                    backgroundColor: [
                        '#F5A503',
                        '#36B1BF'
                    ],
                    borderColor: [
                        '#FFFFFF',
                        '#FFFFFF'
                    ],
                    borderWidth: 4,
                    hoverOffset: 8
                }]
            },
            options: {
                responsive: true,
                maintainAspectRatio: false,
                cutout: '70%',
                plugins: {
                    legend: {
                        position: 'bottom',
                    },
                    tooltip: {
                        callbacks: {
                            title: function(tooltipItems) {
                                const item = tooltipItems[0];
                                let label = item.chart.data.labels[item.dataIndex];
                                if (Array.isArray(label)) {
                                  return label.join(' ');
                                } else {
                                  return label;
                                }
                            }
                        }
                    }
                }
            }
        });

        async function openModal(sectionId) {
            const modal = document.getElementById('infoModal');
            const modalTitle = document.getElementById('modalTitle');
            const modalContent = document.getElementById('modalContent');
            let prompt = '';
            let title = '';

            modalContent.innerHTML = '<div class="loading-spinner"></div>';
            modal.classList.add('show');

            switch (sectionId) {
                case 'evaluacion-formativa':
                    title = 'Evaluación Formativa';
                    prompt = 'Explica en detalle qué es la evaluación formativa en un contexto educativo. Incluye su propósito (evaluación PARA el aprendizaje, acompañamiento), sus características (continua, sin valor directo en calificación, entrenamientos) y ejemplos comunes (observaciones, debates, quizzes cortos, autoevaluaciones).';
                    break;
                case 'evaluacion-sumativa':
                    title = 'Evaluación Sumativa';
                    prompt = 'Explica en detalle qué es la evaluación sumativa en un contexto educativo. Incluye su propósito (evaluación DEL aprendizaje, determinar logro final), sus características (al final de un período, con valor porcentual, basada en comprensión y aplicación) y ejemplos comunes (exámenes finales, proyectos terminados, ensayos, pruebas estandarizadas).';
                    break;
                case 'sinergia-evaluacion':
                    title = 'La Sinergia de la Evaluación';
                    prompt = 'Explica por qué la combinación de evaluación formativa y sumativa es esencial para un proceso de aprendizaje integral y efectivo en un colegio. Destaca cómo una complementa a la otra y su importancia para el desarrollo completo del estudiante.';
                    break;
            }

            modalTitle.textContent = title;

            try {
                let chatHistory = [];
                chatHistory.push({ role: "user", parts: [{ text: prompt }] });
                const payload = { contents: chatHistory };
                const apiKey = "";
                const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent?key=${apiKey}`;
                const response = await fetch(apiUrl, {
                           method: 'POST',
                           headers: { 'Content-Type': 'application/json' },
                           body: JSON.stringify(payload)
                       });
                const result = await response.json();
                if (result.candidates && result.candidates.length > 0 &&
                    result.candidates[0].content && result.candidates[0].content.parts &&
                    result.candidates[0].content.parts.length > 0) {
                  const text = result.candidates[0].content.parts[0].text;
                  modalContent.innerHTML = text;
                } else {
                  modalContent.innerHTML = '<p class="text-red-500">No se pudo obtener la información. Inténtalo de nuevo más tarde.</p>';
                }
            } catch (error) {
                modalContent.innerHTML = '<p class="text-red-500">Error al cargar la información. Por favor, verifica tu conexión.</p>';
                console.error('Error fetching LLM response:', error);
            }
        }

        function closeModal() {
            document.getElementById('infoModal').classList.remove('show');
        }
    </script>

</body>
</html>
