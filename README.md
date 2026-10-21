<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plano de Aula - Instituto Politécnico Nº 7017</title>
    <style>
        :root {
            --primary: #1e3a8a;
            --secondary: #3b82f6;
            --bg: #f8fafc;
            --card: #ffffff;
            --text: #0f172a;
            --border: #cbd5e1;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background-color: var(--bg);
            color: var(--text);
            padding: 12px;
            max-width: 800px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            padding: 10px 0;
            background: var(--primary);
            color: white;
            border-radius: 8px;
            margin-bottom: 12px;
        }

        header h2 {
            font-size: 1.1rem;
            text-transform: uppercase;
        }

        .tabs {
            display: flex;
            gap: 8px;
            margin-bottom: 16px;
        }

        .tab-btn {
            flex: 1;
            padding: 12px;
            border: none;
            background: #e2e8f0;
            color: #475569;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.95rem;
        }

        .tab-btn.active {
            background: var(--secondary);
            color: white;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        .card {
            background: var(--card);
            padding: 16px;
            border-radius: 8px;
            border: 1px solid var(--border);
            margin-bottom: 16px;
        }

        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 10px;
        }

        .full-width {
            grid-column: span 2;
        }

        label {
            font-size: 0.85rem;
            font-weight: bold;
            display: block;
            margin-bottom: 4px;
        }

        input, select, textarea {
            width: 100%;
            padding: 8px 10px;
            border: 1px solid var(--border);
            border-radius: 6px;
            font-size: 0.9rem;
        }

        button.btn-generate {
            width: 100%;
            padding: 12px;
            background: #16a34a;
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: bold;
            margin-top: 10px;
            cursor: pointer;
        }

        .btn-print {
            width: 100%;
            padding: 12px;
            background: var(--primary);
            color: white;
            border: none;
            border-radius: 6px;
            font-size: 1rem;
            font-weight: bold;
            margin-top: 10px;
            cursor: pointer;
        }

        /* Estilo da folha gerada */
        .sheet-container {
            background: white;
            padding: 20px;
            border: 1px solid #000;
            margin-top: 16px;
        }

        .sheet-header {
            text-align: center;
            font-weight: bold;
            font-size: 0.95rem;
            margin-bottom: 15px;
            text-transform: uppercase;
        }

        .sheet-info-table {
            width: 100%;
            margin-bottom: 15px;
            font-size: 0.85rem;
        }

        .sheet-info-table td {
            padding: 3px 0;
            vertical-align: top;
        }

        .section-title {
            font-weight: bold;
            margin-top: 10px;
            margin-bottom: 5px;
            font-size: 0.9rem;
        }

        .quinzenal-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 10px;
            font-size: 0.8rem;
        }

        .quinzenal-table th, .quinzenal-table td {
            border: 1px solid #000;
            padding: 6px;
            text-align: left;
            vertical-align: top;
        }

        /* Ocultar elementos ao imprimir */
        @media print {
            body {
                padding: 0;
                background: white;
            }
            .tabs, .card, header, .btn-print, .btn-generate {
                display: none !important;
            }
            .tab-content {
                display: block !important;
            }
            .sheet-container {
                border: none;
                padding: 0;
            }
        }
    </style>
</head>
<body>

    <header>
        <h2>Instituto Politécnico Nº 7017</h2>
        <p style="font-size: 0.8rem;">CNO - Chico Mendeliev - Cambambe</p>
    </header>

    <div class="tabs">
        <button class="tab-btn active" onclick="switchTab('diario')">Plano Diário</button>
        <button class="tab-btn" onclick="switchTab('quinzenal')">Plano Quinzenal</button>
    </div>

    <!-- ABA 1: PLANO DIÁRIO -->
    <div id="diario" class="tab-content active">
        <div class="card">
            <form id="formDiario" class="form-grid">
                <div>
                    <label>Nome do Professor:</label>
                    <input type="text" id="d_nome" placeholder="Ex: Prof. Pedro Mankenda" required>
                </div>
                <div>
                    <label>Data:</label>
                    <input type="date" id="d_data" required>
                </div>
                <div>
                    <label>Disciplina:</label>
                    <input type="text" id="d_disciplina" placeholder="Ex: Desenho Técnico" required>
                </div>
                <div>
                    <label>Classe:</label>
                    <input type="text" id="d_classe" placeholder="Ex: 10ª Classe" required>
                </div>
                <div>
                    <label>Lição nº:</label>
                    <input type="number" id="d_licao" placeholder="Ex: 12" required>
                </div>
                <div>
                    <label>Curso(s):</label>
                    <input type="text" id="d_curso" placeholder="Ex: Construção Civil" required>
                </div>
                <div>
                    <label>Tempo(s):</label>
                    <input type="text" id="d_tempo" placeholder="Ex: 2 Tempos" required>
                </div>
                <div>
                    <label>Duração da Aula:</label>
                    <input type="text" id="d_duracao" placeholder="Ex: 90 min" required>
                </div>
                <div>
                    <label>Tipo de Aula:</label>
                    <input type="text" id="d_tipo" placeholder="Ex: Teórica / Prática" required>
                </div>
                <div>
                    <label>Nº de Alunos:</label>
                    <input type="number" id="d_alunos" placeholder="Ex: 35" required>
                </div>
                <div class="full-width">
                    <label>Tema:</label>
                    <input type="text" id="d_tema" placeholder="Ex: Projeções Ortogonais" required>
                </div>
                <div class="full-width">
                    <label>Subtema:</label>
                    <input type="text" id="d_subtema" placeholder="Ex: Representação de vistas principais" required>
                </div>
                <div class="full-width">
                    <label>Referências Bibliográficas:</label>
                    <input type="text" id="d_biblio" placeholder="Ex: Manual de Desenho Técnico 10ª Classe">
                </div>
                <div class="full-width">
                    <button type="button" class="btn-generate" onclick="gerarPlanoDiario()">Gerar Plano Diário</button>
                </div>
            </form>
        </div>

        <div id="resultadoDiario" class="sheet-container" style="display:none;">
            <div class="sheet-header">
                INSTITUTO POLITÉCNICO Nº 7017 CNO - CHICO MENDELIEV - CMBAMBE<br>
                PLANO DE AULA
            </div>
            <table class="sheet-info-table">
                <tr>
                    <td width="60%"><strong>Nome:</strong> <span id="out_d_nome"></span></td>
                    <td width="40%"><strong>Data:</strong> <span id="out_d_data"></span></td>
                </tr>
                <tr>
                    <td><strong>Disciplina:</strong> <span id="out_d_disciplina"></span></td>
                    <td><strong>Classe:</strong> <span id="out_d_classe"></span></td>
                </tr>
                <tr>
                    <td><strong>Lição nº:</strong> <span id="out_d_licao"></span></td>
                    <td><strong>Cursos:</strong> <span id="out_d_curso"></span></td>
                </tr>
                <tr>
                    <td><strong>Tema:</strong> <span id="out_d_tema"></span></td>
                    <td><strong>Tempo:</strong> <span id="out_d_tempo"></span></td>
                </tr>
                <tr>
                    <td><strong>Subtema:</strong> <span id="out_d_subtema"></span></td>
                    <td><strong>Duração:</strong> <span id="out_d_duracao"></span></td>
                </tr>
                <tr>
                    <td><strong>Tipo de aula:</strong> <span id="out_d_tipo"></span></td>
                    <td><strong>Nº de alunos:</strong> <span id="out_d_alunos"></span></td>
                </tr>
                <tr>
                    <td colspan="2"><strong>Referencias bibliográfica:</strong> <span id="out_d_biblio"></span></td>
                </tr>
            </table>

            <div class="section-title">Objectivos:</div>
            <div style="margin-left: 15px; font-size: 0.85rem;">
                <p><strong>Geral:</strong> <span id="out_d_obj_geral"></span></p>
                <p><strong>Específicos:</strong></p>
                <ul id="out_d_obj_especificos" style="margin-left: 20px;"></ul>
            </div>

            <div style="font-size: 0.85rem; margin-top: 10px;">
                <p><strong>Métodos:</strong> <span id="out_d_metodos"></span></p>
                <p><strong>Meios de Ensino:</strong> <span id="out_d_meios"></span></p>
            </div>

            <div class="sheet-header" style="margin-top: 15px; margin-bottom: 5px;">Síntese do Conteúdo</div>

            <div style="font-size: 0.85rem;">
                <p><strong>INTRODUÇÃO:</strong></p>
                <p id="out_d_introducao" style="margin-left: 10px; margin-bottom: 8px;"></p>

                <p><strong>DESENVOLVIMENTO:</strong></p>
                <p id="out_d_desenvolvimento" style="margin-left: 10px; margin-bottom: 8px;"></p>

                <p><strong>CONCLUSÃO:</strong></p>
                <p id="out_d_conclusao" style="margin-left: 10px; margin-bottom: 8px;"></p>

                <p><strong>EXERCÍCIO PRÁTICO / TAREFA:</strong></p>
                <p id="out_d_tarefa" style="margin-left: 10px;"></p>
            </div>

            <button class="btn-print" onclick="window.print()">Imprimir / Guardar PDF</button>
        </div>
    </div>

    <!-- ABA 2: PLANO QUINZENAL -->
    <div id="quinzenal" class="tab-content">
        <div class="card">
            <form id="formQuinzenal" class="form-grid">
                <div>
                    <label>Especialidade:</label>
                    <input type="text" id="q_especialidade" placeholder="Ex: Construção Civil" required>
                </div>
                <div>
                    <label>Classe:</label>
                    <input type="text" id="q_classe" placeholder="Ex: 11ª Classe" required>
                </div>
                <div>
                    <label>Disciplina:</label>
                    <input type="text" id="q_disciplina" placeholder="Ex: Tecnologia dos Materiais" required>
                </div>
                <div>
                    <label>Datas Prováveis:</label>
                    <input type="text" id="q_datas" placeholder="Ex: 01/11 a 15/11/2026" required>
                </div>
                <div class="full-width">
                    <label>Unidade(s) Temática(s):</label>
                    <input type="text" id="q_unidade" placeholder="Ex: Unidade II - Propriedades dos Materiais" required>
                </div>
                <div class="full-width">
                    <label>Subtemas (separe por vírgula para várias linhas):</label>
                    <textarea id="q_subtemas" rows="2" placeholder="Ex: Propriedades físicas, Propriedades mecânicas, Ensaio de materiais" required></textarea>
                </div>
                <div class="full-width">
                    <button type="button" class="btn-generate" onclick="gerarPlanoQuinzenal()">Gerar Plano Quinzenal</button>
                </div>
            </form>
        </div>

        <div id="resultadoQuinzenal" class="sheet-container" style="display:none;">
            <div class="sheet-header">
                Instituto Politécnico Nº 7017 CNO - Chico Mendeliev - Cambambe<br>
                Plano Quinzenal
            </div>

            <table style="width:100%; font-size:0.85rem; margin-bottom:10px;">
                <tr>
                    <td><strong>Especialidade:</strong> <span id="out_q_especialidade"></span></td>
                    <td><strong>Classe:</strong> <span id="out_q_classe"></span></td>
                    <td text-align="right"><strong>Disciplina:</strong> <span id="out_q_disciplina"></span></td>
                </tr>
                <tr>
                    <td colspan="3"><strong>Datas Prováveis:</strong> <span id="out_q_datas"></span></td>
                </tr>
            </table>

            <table class="quinzenal-table">
                <thead>
                    <tr>
                        <th width="20%">Unidade(s) Temática(s)</th>
                        <th width="20%">Subtemas</th>
                        <th width="25%">Objectivos Gerais</th>
                        <th width="25%">Actividades</th>
                        <th width="10%">OBS</th>
                    </tr>
                </thead>
                <tbody id="out_q_tbody">
                </tbody>
            </table>

            <div style="margin-top: 30px; text-align: right; font-size: 0.85rem;">
                <p>____________________________________</p>
                <p style="margin-right: 50px;">O Professor</p>
            </div>

            <button class="btn-print" onclick="window.print()">Imprimir / Guardar PDF</button>
        </div>
    </div>

    <script>
        function switchTab(tabId) {
            document.querySelectorAll('.tab-content').forEach(el => el.classList.remove('active'));
            document.querySelectorAll('.tab-btn').forEach(el => el.classList.remove('active'));
            document.getElementById(tabId).classList.add('active');
            event.currentTarget.classList.add('active');
        }

        // GERADOR AUTOMÁTICO - PLANO DIÁRIO
        function gerarPlanoDiario() {
            const tema = document.getElementById('d_tema').value;
            const subtema = document.getElementById('d_subtema').value;
            const disciplina = document.getElementById('d_disciplina').value;

            // Preenchimento dos dados básicos
            document.getElementById('out_d_nome').innerText = document.getElementById('d_nome').value;
            document.getElementById('out_d_data').innerText = document.getElementById('d_data').value;
            document.getElementById('out_d_disciplina').innerText = disciplina;
            document.getElementById('out_d_classe').innerText = document.getElementById('d_classe').value;
            document.getElementById('out_d_licao').innerText = document.getElementById('d_licao').value;
            document.getElementById('out_d_curso').innerText = document.getElementById('d_curso').value;
            document.getElementById('out_d_tempo').innerText = document.getElementById('d_tempo').value;
            document.getElementById('out_d_duracao').innerText = document.getElementById('d_duracao').value;
            document.getElementById('out_d_tipo').innerText = document.getElementById('d_tipo').value;
            document.getElementById('out_d_alunos').innerText = document.getElementById('d_alunos').value;
            document.getElementById('out_d_tema').innerText = tema;
            document.getElementById('out_d_subtema').innerText = subtema;
            document.getElementById('out_d_biblio').innerText = document.getElementById('d_biblio').value || 'Manual escolar recomendado.';

            // Geração Automática do Conteúdo Pedagógico
            document.getElementById('out_d_obj_geral').innerText = `Compreender os conceitos fundamentais de ${subtema} no âmbito de ${tema}.`;
            
            const especList = document.getElementById('out_d_obj_especificos');
            especList.innerHTML = `
                <li>Definir e caracterizar os conceitos principais de ${subtema}.</li>
                <li>Identificar as aplicações práticas de ${subtema} em ${disciplina}.</li>
                <li>Demonstrar autonomia na resolução dos exercícios propostos na aula.</li>
            `;

            document.getElementById('out_d_metodos').innerText = 'Expositivo, Elaboração Conjunta e Trabalho Independente.';
            document.getElementById('out_d_meios').innerText = 'Quadro, Giz/Marcadores, Livro de texto, Esquadros e Material multimédia.';

            document.getElementById('out_d_introducao').innerText = `Acolhimento dos alunos, controlo de presenças e breve revisão da lição anterior. Apresentação do tema (${subtema}) e articulação com os objectivos da aula.`;
            document.getElementById('out_d_desenvolvimento').innerText = `Exposição detalhada do conteúdo relativo a ${subtema}. Apresentação de exemplos práticos no contexto de ${disciplina}. Esclarecimento de dúvidas e interação com a turma.`;
            document.getElementById('out_d_conclusao').innerText = `Sintetização dos pontos essenciais abordados na aula sobre ${subtema} e avaliação sumativa rápida através de perguntas de verificação.`;
            document.getElementById('out_d_tarefa').innerText = `Resolver o exercício da página do manual referente a ${subtema} para apresentação na próxima aula.`;

            document.getElementById('resultadoDiario').style.display = 'block';
        }

        // GERADOR AUTOMÁTICO - PLANO QUINZENAL
        function gerarPlanoQuinzenal() {
            const especialidade = document.getElementById('q_especialidade').value;
            const classe = document.getElementById('q_classe').value;
            const disciplina = document.getElementById('q_disciplina').value;
            const datas = document.getElementById('q_datas').value;
            const unidade = document.getElementById('q_unidade').value;
            const subtemasRaw = document.getElementById('q_subtemas').value;

            document.getElementById('out_q_especialidade').innerText = especialidade;
            document.getElementById('out_q_classe').innerText = classe;
            document.getElementById('out_q_disciplina').innerText = disciplina;
            document.getElementById('out_q_datas').innerText = datas;

            const listSubtemas = subtemasRaw.split(',').map(s => s.trim()).filter(s => s.length > 0);
            const tbody = document.getElementById('out_q_tbody');
            tbody.innerHTML = '';

            listSubtemas.forEach((st, idx) => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    ${idx === 0 ? `<td rowspan="${listSubtemas.length}"><strong>${unidade}</strong></td>` : ''}
                    <td>${st}</td>
                    <td>Proporcionar o domínio concep
