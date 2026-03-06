<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mulheres à Frente - Canal de Acolhimento</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #faf7f2;
            --bg-secondary: #ffffff;
            --sidebar-bg: #fae9e9;
            --text-primary: #2c3e50;
            --text-secondary: #5d6d7e;
            --border-color: #eed9d9;
            --accent-primary: #c44545;
            --accent-secondary: #a33c3c;
            --accent-emergency: #b03a3a;
            --accent-success: #2e7d5e;
            --card-shadow: 0 10px 30px -10px rgba(0,0,0,0.08);
            --font-serif: 'Playfair Display', serif;
            --font-sans: 'Inter', sans-serif;
        }

        .dark-mode {
            --bg-primary: #1a1a1a;
            --bg-secondary: #2d2d2d;
            --sidebar-bg: #3d2e2e;
            --text-primary: #f0f0f0;
            --text-secondary: #c0c0c0;
            --border-color: #404040;
            --accent-primary: #c46b6b;
            --accent-secondary: #a14d4d;
            --accent-emergency: #b04a4a;
            --card-shadow: 0 10px 30px -10px rgba(0,0,0,0.3);
        }

        body {
            background-color: var(--bg-primary);
            color: var(--text-primary);
            font-family: var(--font-sans);
            transition: background-color 0.3s, color 0.3s;
            min-height: 100vh;
            line-height: 1.6;
        }

        h1, h2, h3, h4, h5, h6 {
            font-family: var(--font-serif);
            font-weight: 600;
            letter-spacing: -0.02em;
        }

        .container {
            display: flex;
            min-height: 100vh;
        }

        /* Sidebar */
        .sidebar {
            width: 300px;
            background: var(--sidebar-bg);
            padding: 2.5rem 1.8rem;
            position: fixed;
            height: 100vh;
            overflow-y: auto;
            transition: all 0.3s ease;
            box-shadow: 2px 0 25px rgba(0,0,0,0.05);
            border-right: 1px solid var(--border-color);
            z-index: 100;
        }

        .logo-area {
            margin-bottom: 3rem;
            padding-bottom: 1.5rem;
            border-bottom: 2px solid var(--border-color);
        }

        .logo {
            font-family: var(--font-serif);
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent-primary);
            line-height: 1.2;
            margin-bottom: 0.5rem;
        }

        .logo-subtitle {
            font-size: 0.9rem;
            color: var(--text-secondary);
            font-weight: 300;
            letter-spacing: 0.5px;
        }

        .theme-toggle {
            background: var(--bg-secondary);
            border: 1px solid var(--border-color);
            cursor: pointer;
            padding: 0.6rem;
            border-radius: 30px;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            color: var(--text-primary);
            transition: all 0.3s;
            font-size: 0.9rem;
            margin-top: 1.5rem;
        }

        .theme-toggle:hover {
            background: var(--accent-primary);
            color: white;
            border-color: var(--accent-primary);
        }

        .nav-menu {
            list-style: none;
            margin-top: 2rem;
        }

        .nav-item {
            margin-bottom: 0.5rem;
        }

        .nav-link {
            display: flex;
            align-items: center;
            gap: 1rem;
            padding: 1rem 1.2rem;
            color: var(--text-primary);
            text-decoration: none;
            border-radius: 16px;
            transition: all 0.3s ease;
            font-weight: 500;
            cursor: pointer;
            border: none;
            background: none;
            width: 100%;
            text-align: left;
            font-size: 1rem;
            position: relative;
        }

        .nav-link:hover {
            background: var(--bg-secondary);
            color: var(--accent-primary);
            transform: translateX(5px);
        }

        .nav-link.active {
            background: var(--accent-primary);
            color: white;
            box-shadow: 0 4px 15px rgba(196, 69, 69, 0.2);
        }

        .nav-icon {
            font-size: 1.2rem;
            opacity: 0.8;
        }

        /* Main Content */
        .main-content {
            flex: 1;
            margin-left: 300px;
            padding: 2.5rem;
            background-color: var(--bg-primary);
            min-height: 100vh;
        }

        /* Animações */
        .section {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .section.active-section {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .page-title {
            font-family: var(--font-serif);
            font-size: 2.5rem;
            margin-bottom: 2.5rem;
            color: var(--text-primary);
            position: relative;
            display: inline-block;
            font-weight: 700;
        }

        .page-title::after {
            content: '';
            position: absolute;
            bottom: -12px;
            left: 0;
            width: 80px;
            height: 3px;
            background: var(--accent-primary);
            border-radius: 2px;
        }

        /* Cards */
        .card {
            background: var(--bg-secondary);
            border-radius: 24px;
            padding: 2.5rem;
            margin-bottom: 2rem;
            box-shadow: var(--card-shadow);
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
        }

        .card:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px -10px rgba(0,0,0,0.1);
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px dashed var(--border-color);
        }

        .card-title {
            font-family: var(--font-serif);
            font-size: 1.5rem;
            font-weight: 600;
            color: var(--text-primary);
        }

        .badge {
            background: var(--accent-primary);
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 500;
            letter-spacing: 0.3px;
        }

        /* Mapa e Delegacias */
        .map-container {
            width: 100%;
            height: 450px;
            border-radius: 20px;
            overflow: hidden;
            margin-bottom: 2rem;
            border: 3px solid var(--border-color);
        }

        .map-container iframe {
            width: 100%;
            height: 100%;
            border: 0;
        }

        .map-info {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 2rem;
            padding: 1rem;
            background: var(--bg-primary);
            border-radius: 16px;
        }

        .btn-map {
            background: linear-gradient(135deg, var(--accent-primary), var(--accent-secondary));
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            border: none;
            cursor: pointer;
        }

        .btn-map:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px rgba(196, 69, 69, 0.3);
        }

        .delegacias-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .delegacia-card {
            background: var(--bg-primary);
            border-radius: 20px;
            padding: 1.8rem;
            border-left: 5px solid;
            transition: all 0.3s ease;
            border: 1px solid var(--border-color);
            border-left-width: 5px;
        }

        .delegacia-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }

        .delegacia-card h3 {
            font-family: var(--font-serif);
            font-size: 1.3rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .delegacia-card .endereco {
            color: var(--text-secondary);
            margin: 1rem 0;
            line-height: 1.6;
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }

        .delegacia-card .contato {
            background: var(--bg-secondary);
            padding: 1rem;
            border-radius: 12px;
            margin: 1rem 0;
        }

        .delegacia-card .contato p {
            color: var(--text-secondary);
            margin: 0.5rem 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .delegacia-card .horario {
            color: var(--accent-success);
            font-weight: 600;
            margin: 1rem 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .delegacia-card .badge-local {
            display: inline-block;
            background: var(--accent-success);
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-top: 0.5rem;
        }

        .delegacia-card .badge-local.urgente {
            background: var(--accent-emergency);
        }

        .btn-localizar {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            background: var(--bg-secondary);
            color: var(--accent-primary);
            text-decoration: none;
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            margin-top: 1rem;
            border: 2px solid var(--accent-primary);
            transition: all 0.3s;
            font-weight: 600;
            width: 100%;
            justify-content: center;
        }

        .btn-localizar:hover {
            background: var(--accent-primary);
            color: white;
        }

        .emergencia-card {
            background: linear-gradient(135deg, var(--accent-emergency), #c0392b);
            color: white;
        }

        .emergencia-card h3,
        .emergencia-card .endereco,
        .emergencia-card .contato p {
            color: white;
        }

        .emergencia-card .btn-localizar {
            background: white;
            border: none;
            color: var(--accent-emergency);
        }

        .emergency-numbers {
            display: flex;
            gap: 1rem;
            justify-content: center;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .emergency-number {
            background: var(--bg-primary);
            border-radius: 30px;
            padding: 0.8rem 1.5rem;
            font-weight: 600;
            color: var(--accent-primary);
            border: 1px solid var(--border-color);
            font-size: 1.2rem;
        }

        /* Formulários */
        .form-group {
            margin-bottom: 2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.6rem;
            color: var(--text-secondary);
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.3px;
            text-transform: uppercase;
        }

        .form-group input,
        .form-group textarea,
        .form-group select {
            width: 100%;
            padding: 1rem 1.2rem;
            border: 2px solid var(--border-color);
            border-radius: 16px;
            background: var(--bg-primary);
            color: var(--text-primary);
            font-family: var(--font-sans);
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--accent-primary);
            box-shadow: 0 0 0 4px rgba(196, 69, 69, 0.1);
        }

        .btn {
            background: var(--accent-primary);
            color: white;
            border: none;
            padding: 1.2rem 2rem;
            border-radius: 16px;
            font-family: var(--font-sans);
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            width: 100%;
            letter-spacing: 0.5px;
            text-transform: uppercase;
        }

        .btn:hover {
            background: var(--accent-secondary);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(196, 69, 69, 0.3);
        }

        .btn-emergency {
            background: var(--accent-emergency);
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.02); box-shadow: 0 0 30px rgba(176, 58, 58, 0.3); }
            100% { transform: scale(1); }
        }

        /* Chat */
        .chat-container {
            background: var(--bg-primary);
            border-radius: 24px;
            height: 500px;
            display: flex;
            flex-direction: column;
            border: 1px solid var(--border-color);
            overflow: hidden;
        }

        .chat-header {
            background: var(--accent-primary);
            color: white;
            padding: 1.2rem 1.8rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .chat-avatar {
            width: 45px;
            height: 45px;
            border-radius: 50%;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--accent-primary);
            font-weight: 600;
            font-size: 1.2rem;
        }

        .chat-info h3 {
            font-family: var(--font-serif);
            font-size: 1.1rem;
            margin-bottom: 0.2rem;
        }

        .chat-info p {
            font-size: 0.8rem;
            opacity: 0.9;
        }

        .chat-messages {
            flex: 1;
            overflow-y: auto;
            padding: 1.8rem;
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .message {
            padding: 1rem 1.5rem;
            border-radius: 20px;
            max-width: 70%;
            word-wrap: break-word;
            animation: messageSlide 0.3s ease;
            position: relative;
        }

        @keyframes messageSlide {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .message.received {
            background: var(--accent-primary);
            color: white;
            align-self: flex-start;
            border-bottom-left-radius: 5px;
        }

        .message.sent {
            background: var(--accent-secondary);
            color: white;
            align-self: flex-end;
            border-bottom-right-radius: 5px;
        }

        .message-time {
            font-size: 0.7rem;
            opacity: 0.7;
            margin-top: 0.3rem;
        }

        .chat-input-area {
            display: flex;
            gap: 0.8rem;
            padding: 1.5rem;
            border-top: 1px solid var(--border-color);
            background: var(--bg-secondary);
        }

        .chat-input-area input {
            flex: 1;
            padding: 1rem 1.2rem;
            border: 2px solid var(--border-color);
            border-radius: 30px;
            background: var(--bg-primary);
            color: var(--text-primary);
            font-family: var(--font-sans);
            transition: all 0.3s ease;
        }

        .chat-input-area input:focus {
            border-color: var(--accent-primary);
            outline: none;
        }

        .chat-send-btn {
            width: auto;
            padding: 1rem 2.5rem;
            border-radius: 30px;
            background: var(--accent-primary);
        }

        /* Grid de recursos */
        .resources-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .resource-card {
            background: var(--bg-primary);
            border-radius: 20px;
            padding: 2rem;
            border: 1px solid var(--border-color);
            transition: all 0.3s ease;
            text-align: left;
        }

        .resource-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-primary);
        }

        .resource-title {
            font-family: var(--font-serif);
            font-size: 1.2rem;
            margin-bottom: 1rem;
            color: var(--text-primary);
        }

        .resource-text {
            color: var(--text-secondary);
            font-size: 0.95rem;
            line-height: 1.6;
        }

        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
            backdrop-filter: blur(5px);
        }

        .modal-content {
            background: var(--bg-secondary);
            max-width: 450px;
            margin: 100px auto;
            padding: 2.5rem;
            border-radius: 30px;
            text-align: center;
            animation: slideUp 0.5s ease;
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .modal-icon {
            width: 80px;
            height: 80px;
            background: var(--accent-emergency);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1.5rem;
            color: white;
            font-size: 2rem;
        }

        /* Toast */
        .toast {
            position: fixed;
            bottom: 20px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--accent-success);
            color: white;
            padding: 1rem 2rem;
            border-radius: 50px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.2);
            z-index: 3000;
            font-weight: 500;
        }

        /* Progress bar */
        .progress-bar {
            width: 100%;
            height: 4px;
            background: var(--border-color);
            border-radius: 2px;
            overflow: hidden;
            margin: 1.5rem 0;
        }

        .progress-fill {
            height: 100%;
            background: var(--accent-success);
            width: 0%;
            transition: width 0.3s ease;
        }

        /* Loading */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(255,255,255,.3);
            border-radius: 50%;
            border-top-color: white;
            animation: spin 1s ease-in-out infinite;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Círculo de respiração */
        .breathing-circle {
            width: 220px;
            height: 220px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-primary), var(--accent-secondary));
            margin: 2rem auto;
            transition: transform 8s ease-in-out;
        }

        .breathing-text {
            text-align: center;
            color: var(--text-secondary);
            margin: 1.5rem 0;
            font-size: 1.1rem;
        }

        /* Acessibilidade */
        .accessibility-btn {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 60px;
            height: 60px;
            border-radius: 50%;
            background: var(--accent-primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            cursor: pointer;
            border: none;
            z-index: 1000;
            box-shadow: 0 5px 20px rgba(196, 69, 69, 0.3);
            transition: all 0.3s ease;
        }

        .accessibility-btn:hover {
            transform: scale(1.1) rotate(5deg);
        }

        /* Support text */
        .support-text {
            color: var(--text-secondary);
            font-size: 1rem;
            line-height: 1.8;
            margin-bottom: 1rem;
        }

        /* Audio player */
        audio {
            width: 100%;
            border-radius: 30px;
            margin-top: 1rem;
        }

        /* Responsividade */
        @media (max-width: 768px) {
            .sidebar {
                width: 100%;
                height: auto;
                position: relative;
                padding: 1.5rem;
            }

            .main-content {
                margin-left: 0;
                padding: 1.5rem;
            }

            .container {
                flex-direction: column;
            }

            .message {
                max-width: 85%;
            }

            .modal-content {
                margin: 50px 20px;
            }

            .page-title {
                font-size: 2rem;
            }

            .map-container {
                height: 300px;
            }

            .delegacias-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Sidebar -->
        <aside class="sidebar">
            <div class="logo-area">
                <div class="logo">Mulheres à Frente</div>
                <div class="logo-subtitle">Acolhimento e apoio</div>
                
                <button class="theme-toggle" onclick="toggleDarkMode()" id="themeToggle">
                    <span>🌙</span>
                    <span>Modo escuro</span>
                </button>
            </div>

            <ul class="nav-menu">
                <li class="nav-item">
                    <button class="nav-link" onclick="showSection('denuncia')">
                        <span class="nav-icon">⚖️</span>
                        Denúncia
                    </button>
                </li>
                <li class="nav-item">
                    <button class="nav-link" onclick="showSection('chat')">
                        <span class="nav-icon">💭</span>
                        Acolhimento Psicológico
                        <span class="badge">Online</span>
                    </button>
                </li>
                <li class="nav-item">
                    <button class="nav-link" onclick="showSection('apoio')">
                        <span class="nav-icon">🧘‍♀️</span>
                        Bem-estar
                    </button>
                </li>
                <li class="nav-item">
                    <button class="nav-link" onclick="showSection('informativos')">
                        <span class="nav-icon">📖</span>
                        Informações
                    </button>
                </li>
                <li class="nav-item">
                    <button class="nav-link active" onclick="showSection('mapa')">
                        <span class="nav-icon">📍</span>
                        Rede de Apoio
                    </button>
                </li>
            </ul>
        </aside>

        <!-- Main Content -->
        <main class="main-content">
            <!-- Seção Denúncia -->
            <section id="denuncia" class="section">
                <h1 class="page-title">Canal de Denúncia</h1>
                
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Seu relato é importante</h2>
                        <span class="badge">Sigiloso</span>
                    </div>
                    
                    <div class="support-text">
                        Todas as informações são confidenciais e protegidas.
                    </div>
                    
                    <form id="denunciaForm">
                        <div class="form-group">
                            <label>Nome (opcional)</label>
                            <input type="text" placeholder="Como prefere ser chamada?" id="denunciaNome">
                        </div>
                        
                        <div class="form-group">
                            <label>Empresa ou instituição *</label>
                            <input type="text" required id="denunciaEmpresa" placeholder="Nome da empresa">
                        </div>
                        
                        <div class="form-group">
                            <label>Data do ocorrido *</label>
                            <input type="date" required id="denunciaData">
                        </div>
                        
                        <div class="form-group">
                            <label>Seu relato *</label>
                            <textarea rows="5" required id="denunciaRelato" placeholder="Descreva com detalhes o que aconteceu..."></textarea>
                        </div>
                        
                        <div class="form-group">
                            <label>Nível de urgência</label>
                            <select id="denunciaUrgencia">
                                <option value="orientacao">Necessito orientação</option>
                                <option value="delicada">Situação delicada</option>
                                <option value="emergencia">Emergência - Ajuda imediata</option>
                            </select>
                        </div>
                        
                        <button type="submit" class="btn" id="submitDenuncia">
                            Enviar denúncia
                        </button>
                    </form>
                </div>

                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Atendimento emergencial</h2>
                    </div>
                    
                    <button class="btn btn-emergency" onclick="emergencyAlert()">
                        Botão de emergência
                    </button>
                    
                    <div class="support-text" style="text-align: center; margin-top: 1rem;">
                        Ao acionar, nossa equipe será notificada imediatamente
                    </div>
                </div>
            </section>

            <!-- Seção Chat -->
            <section id="chat" class="section">
                <h1 class="page-title">Acolhimento Psicológico</h1>
                
                <div class="card">
                    <div class="chat-container">
                        <div class="chat-header">
                            <div class="chat-avatar">
                                <img src="imagem.jpg" alt="Dra. Ana Silva" style="width:40px; height:40px; border-radius:50%; object-fit:cover;">
                            </div>
                            <div class="chat-info">
                                <h3>Dra. Ana Silva</h3>
                                <p>Psicóloga disponível</p>
                            </div>
                            <span class="badge" style="margin-left: auto;">Online</span>
                        </div>
                        
                        <div class="chat-messages" id="chatMessages">
                            <div class="message received">
                                Olá, como posso ajudar você hoje?
                                <div class="message-time">09:00</div>
                            </div>
                        </div>
                        
                        <div class="chat-input-area">
                            <input type="text" id="chatInput" placeholder="Digite sua mensagem..." 
                                   onkeypress="if(event.key === 'Enter') sendMessage()">
                            <button class="btn chat-send-btn" onclick="sendMessage()" id="sendMessageBtn">
                                Enviar
                            </button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- Seção Bem-estar -->
            <section id="apoio" class="section">
                <h1 class="page-title">Práticas de Bem-estar</h1>
                
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Exercício de respiração</h2>
                    </div>
                    
                    <div class="breathing-circle" id="breathingCircle"></div>
                    <div class="breathing-text" id="breathingText">
                        Inspire (4s) • Segure (4s) • Expire (4s)
                    </div>
                    
                    <button class="btn" onclick="startBreathingExercise()" style="width: auto; margin: 0 auto; display: block; padding: 1rem 3rem;">
                        Iniciar exercício
                    </button>
                </div>

                <div class="resources-grid">
                    <div class="resource-card">
                        <h3 class="resource-title">Meditação guiada</h3>
                        <p class="resource-text">Sessões curtas para momentos de ansiedade</p>
                        <audio controls>
                            <source src="#" type="audio/mpeg">
                        </audio>
                    </div>
                    
                    <div class="resource-card">
                        <h3 class="resource-title">Música relaxante</h3>
                        <p class="resource-text">Ambiente sonoro para acalmar</p>
                        <audio controls>
                            <source src="#" type="audio/mpeg">
                        </audio>
                    </div>
                </div>
            </section>

            <!-- Seção Informações -->
            <section id="informativos" class="section">
                <h1 class="page-title">Informações de Apoio</h1>
                
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">Tipos de violência</h2>
                    </div>
                    
                    <div class="resources-grid">
                        <div class="resource-card">
                            <h3 class="resource-title">Assédio sexual</h3>
                            <p class="resource-text">Condutas de conotação sexual não desejadas, como cantadas, toques e insinuações.</p>
                        </div>
                        
                        <div class="resource-card">
                            <h3 class="resource-title">Assédio moral</h3>
                            <p class="resource-text">Humilhações, constrangimentos, isolamento e sobrecarga de trabalho.</p>
                        </div>
                        
                        <div class="resource-card">
                            <h3 class="resource-title">Discriminação</h3>
                            <p class="resource-text">Preconceito baseado em gênero, raça, orientação sexual ou outros fatores.</p>
                        </div>
                        
                        <div class="resource-card">
                            <h3 class="resource-title">Perseguição</h3>
                            <p class="resource-text">Stalking, ameaças e vigilância constante, causando medo e intimidação.</p>
                        </div>
                    </div>
                </div>

                <div class="card" style="background: linear-gradient(135deg, var(--accent-primary), var(--accent-secondary)); color: white;">
                    <h2 style="font-family: var(--font-serif); font-size: 2rem; margin-bottom: 1rem;">Você não está sozinha</h2>
                    <p style="font-size: 1.2rem; opacity: 0.95; line-height: 1.6;">Nós acreditamos em você. Sua voz é importante e será ouvida com respeito e acolhimento.</p>
                    
                    <div class="emergency-numbers">
                        <span class="emergency-number">180</span>
                        <span class="emergency-number">100</span>
                    </div>
                </div>
            </section>

            <!-- Seção Rede de Apoio (MAPA) -->
            <section id="mapa" class="section active-section">
                <h1 class="page-title">Rede de Apoio em Cuiabá</h1>
                
                <!-- Números de Emergência -->
                <div class="emergency-numbers">
                    <span class="emergency-number">📞 180</span>
                    <span class="emergency-number">🚓 190</span>
                    <span class="emergency-number">⚖️ 100</span>
                </div>

                <!-- Mapa Interativo Principal -->
                <div class="card">
                    <div class="card-header">
                        <h2 class="card-title">📍 Delegacias da Mulher em Cuiabá</h2>
                        <span class="badge">24h</span>
                    </div>
                    
                    <!-- Mapa Google Maps com todas as delegacias -->
                    <div class="map-container">
                        <iframe 
                            src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d30739.54218527431!2d-56.106781!3d-15.6014105!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1sdelegacia%20da%20mulher%20cuiaba!5e0!3m2!1spt-BR!2sbr!4v1700000000000!5m2!1spt-BR!2sbr" 
                            allowfullscreen="" 
                            loading="lazy" 
                            referrerpolicy="no-referrer-when-downgrade">
                        </iframe>
                    </div>
                    
                    <div class="map-info">
                        <div>
                            <h3 style="font-family: var(--font-serif);">📍 Todas as delegacias especializadas</h3>
                            <p style="color: var(--text-secondary);">Clique no mapa para ver rotas e mais detalhes</p>
                        </div>
                        <a href="https://www.google.com/maps/search/delegacia+da+mulher+cuiaba/@-15.6014105,-56.106781,14z" 
                           target="_blank" 
                           class="btn-map">
                            🗺️ Abrir no Google Maps
                        </a>
                    </div>

                    <!-- Lista de Delegacias -->
                    <div class="delegacias-grid">
                        
                        <!-- Delegacia Especializada - Jardim Paulista -->
                        <div class="delegacia-card" style="border-left-color: #8e44ad;">
                            <h3>👮 Delegacia Especializada da Mulher</h3>
                            <div class="endereco">
                                📍 <strong>Nova sede:</strong> Avenida Carmindo de Campos, 2.109 - Jardim Paulista<br>
                                <small>(esquina com a Rua Bahia, próximo ao Banco do Brasil)</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Telefone:</strong> (65) 3901-4277</p>
                                <p>📧 <strong>E-mail:</strong> dmulhercba@pjc.mt.gov.br</p>
                            </div>
                            <div class="horario">
                                ⏰ <strong>Atendimento:</strong> Segunda a sexta, horário comercial
                            </div>
                            <a href="https://www.google.com/maps/search/?api=1&query=Avenida+Carmindo+de+Campos+2109+Jardim+Paulista+Cuiaba" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>

                        <!-- Plantão 24h - Atendimento Emergencial -->
                        <div class="delegacia-card emergencia-card" style="border-left-color: #dc3545;">
                            <h3>🆘 Plantão 24h da Mulher</h3>
                            <div class="endereco">
                                📍 Av. Dante Martins de Oliveira, s/n - Bairro Planalto<br>
                                <small>(2ª Delegacia de Polícia do Carumbé - Complexo Pomeri)</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Plantão:</strong> (65) 3901-4254 | 3901-4226</p>
                                <p>⏰ <strong>Funcionamento:</strong> 24 horas, todos os dias</p>
                            </div>
                            <span class="badge-local urgente">🚨 Emergência - Atendimento imediato</span>
                            <p style="color: white; margin-top: 10px;">✅ Estrutura especial: sala psicossocial, brinquedoteca, equipe exclusiva</p>
                            <a href="https://www.google.com/maps/search/?api=1&query=Av+Dante+Martins+de+Oliveira+Planalto+Cuiaba" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>

                        <!-- Delegacia da Mulher - Centro -->
                        <div class="delegacia-card" style="border-left-color: #3498db;">
                            <h3>🏛️ Delegacia da Mulher - Centro</h3>
                            <div class="endereco">
                                📍 Rua Joaquim Murtinho, 789 - Centro Sul<br>
                                <small>CEP: 78020-290</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Telefone:</strong> (65) 3901-4277</p>
                                <p>ℹ️ <strong>Atendimento:</strong> Dias úteis, horário comercial</p>
                            </div>
                            <a href="https://www.google.com/maps/search/?api=1&query=Rua+Joaquim+Murtinho+789+Centro+Sul+Cuiaba" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>

                        <!-- Delegacia de Várzea Grande -->
                        <div class="delegacia-card" style="border-left-color: #9b59b6;">
                            <h3>🌉 Delegacia da Mulher de Várzea Grande</h3>
                            <div class="endereco">
                                📍 Avenida Dom Orlando Chaves, s/n - Ponte Nova<br>
                                <small>Várzea Grande - MT, CEP: 78118-000</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Central de Ocorrências:</strong> (65) 3614-6201</p>
                                <p>📞 <strong>Central de Flagrantes:</strong> (65) 3901-3375</p>
                            </div>
                            <div class="horario">
                                ⏰ <strong>Atendimento:</strong> 24h (flagrantes) / dias úteis (normal)
                            </div>
                            <a href="https://www.google.com/maps/search/?api=1&query=Av+Dom+Orlando+Chaves+Ponte+Nova+Várzea+Grande" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>

                        <!-- Núcleo de Atendimento à Pessoa Idosa -->
                        <div class="delegacia-card" style="border-left-color: #e67e22;">
                            <h3>👵 Núcleo da Pessoa Idosa</h3>
                            <div class="endereco">
                                📍 Av. Dante Martins de Oliveira, s/n - Bairro Planalto<br>
                                <small>(prédio da 2ª Delegacia - Complexo Pomeri)</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Telefone:</strong> (65) 98442-8757</p>
                            </div>
                            <a href="https://www.google.com/maps/search/?api=1&query=Complexo+Pomeri+Cuiaba" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>

                        <!-- Delegacia da Criança e Adolescente -->
                        <div class="delegacia-card" style="border-left-color: #2ecc71;">
                            <h3>👧 Delegacia da Criança</h3>
                            <div class="endereco">
                                📍 Av. Dante Martins de Oliveira, s/nº - Bairro Planalto<br>
                                <small>(anexo ao Complexo Pomeri)</small>
                            </div>
                            <div class="contato">
                                <p>📞 <strong>Telefone:</strong> (65) 3901-5700 | 3901-5696</p>
                            </div>
                            <a href="https://www.google.com/maps/search/?api=1&query=Complexo+Pomeri+Cuiaba" 
                               class="btn-localizar" 
                               target="_blank">
                                🗺️ Ver no mapa
                            </a>
                        </div>
                    </div>

                    <!-- Informações adicionais -->
                    <div style="margin-top: 2rem; padding: 1.5rem; background: var(--bg-primary); border-radius: 16px;">
                        <h3 style="font-family: var(--font-serif); margin-bottom: 1rem;">ℹ️ Serviços disponíveis</h3>
                        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1rem;">
                            <div>
                                <p style="color: var(--accent-success);">✅ Acolhimento humanizado</p>
                            </div>
                            <div>
                                <p style="color: var(--accent-success);">✅ Medidas Protetivas</p>
                            </div>
                            <div>
                                <p style="color: var(--accent-success);">✅ Atendimento Psicossocial</p>
                            </div>
                            <div>
                                <p style="color: var(--accent-success);">✅ Orientação Jurídica</p>
                            </div>
                        </div>
                        <p style="color: var(--text-secondary); margin-top: 1rem; text-align: center;">
                            💜 Todas as unidades oferecem atendimento sigiloso e acolhedor
                        </p>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <!-- Botão de acessibilidade -->
    <button class="accessibility-btn" onclick="activateAccessibility()">
        ♿
    </button>

    <!-- Modal de Emergência -->
    <div id="emergencyModal" class="modal">
        <div class="modal-content">
            <div class="modal-icon">!</div>
            <h2 style="font-family: var(--font-serif); margin-bottom: 1rem;">Alerta enviado</h2>
            <p style="margin-bottom: 1.5rem; color: var(--text-secondary);">
                Nossa equipe foi notificada e entrará em contato em instantes.
            </p>
            <div class="progress-bar">
                <div class="progress-fill" id="emergencyProgress"></div>
            </div>
            <button class="btn" onclick="closeModal()" style="margin-top: 1.5rem;">
                Compreendi
            </button>
        </div>
    </div>

    <script>
        // Controle de seções
        function showSection(sectionId) {
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active-section');
            });
            document.getElementById(sectionId).classList.add('active-section');
            
            document.querySelectorAll('.nav-link').forEach(btn => {
                btn.classList.remove('active');
            });
            
            event.target.classList.add('active');
        }

        // Modo escuro/claro
        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            const themeToggle = document.getElementById('themeToggle');
            
            if (document.body.classList.contains('dark-mode')) {
                themeToggle.innerHTML = '<span>☀️</span><span>Modo claro</span>';
            } else {
                themeToggle.innerHTML = '<span>🌙</span><span>Modo escuro</span>';
            }
        }

        // Chat
        function sendMessage() {
            const input = document.getElementById('chatInput');
            const message = input.value.trim();
            const sendBtn = document.getElementById('sendMessageBtn');
            
            if (!message) {
                showToast('Digite uma mensagem');
                return;
            }
            
            sendBtn.disabled = true;
            sendBtn.innerHTML = '<span class="loading"></span>';
            
            const chatMessages = document.getElementById('chatMessages');
            const time = new Date().toLocaleTimeString('pt-BR', { hour: '2-digit', minute: '2-digit' });
            
            const userMessage = document.createElement('div');
            userMessage.className = 'message sent';
            userMessage.innerHTML = `${message}<div class="message-time">${time}</div>`;
            chatMessages.appendChild(userMessage);
            
            input.value = '';
            chatMessages.scrollTop = chatMessages.scrollHeight;
            
            setTimeout(() => {
                sendBtn.disabled = false;
                sendBtn.innerHTML = 'Enviar';
                
                const responses = [
                    "Estou aqui com você. Pode continuar.",
                    "Compreendo como se sente.",
                    "Você é muito corajosa.",
                    "Como posso ajudar neste momento?",
                    "Estou ouvindo atentamente."
                ];
                
                const responseTime = new Date().toLocaleTimeString('pt-BR', { hour: '2-digit', minute: '2-digit' });
                const randomResponse = responses[Math.floor(Math.random() * responses.length)];
                
                const response = document.createElement('div');
                response.className = 'message received';
                response.innerHTML = `${randomResponse}<div class="message-time">${responseTime}</div>`;
                chatMessages.appendChild(response);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }, 1500);
        }

        // Toast
        function showToast(message) {
            const toast = document.createElement('div');
            toast.className = 'toast';
            toast.textContent = message;
            document.body.appendChild(toast);
            
            setTimeout(() => {
                toast.remove();
            }, 3000);
        }

        // Emergência
        function emergencyAlert() {
            const modal = document.getElementById('emergencyModal');
            modal.style.display = 'block';
            
            const progress = document.getElementById('emergencyProgress');
            let width = 0;
            const timer = setInterval(() => {
                if (width >= 100) {
                    clearInterval(timer);
                } else {
                    width += 2;
                    progress.style.width = width + '%';
                }
            }, 30);
        }

        function closeModal() {
            document.getElementById('emergencyModal').style.display = 'none';
            document.getElementById('emergencyProgress').style.width = '0%';
        }

        // Fechar modal ao clicar fora
        window.onclick = function(event) {
            const modal = document.getElementById('emergencyModal');
            if (event.target == modal) {
                closeModal();
            }
        }

        // Formulário de denúncia
        document.getElementById('denunciaForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const submitBtn = document.getElementById('submitDenuncia');
            const originalText = submitBtn.textContent;
            submitBtn.innerHTML = '<span class="loading"></span>';
            submitBtn.disabled = true;
            
            setTimeout(() => {
                showToast('Denúncia enviada com sucesso');
                this.reset();
                submitBtn.innerHTML = originalText;
                submitBtn.disabled = false;
            }, 2000);
        });

        // Exercício de respiração
        let breathingInterval;
        
        function startBreathingExercise() {
            const circle = document.getElementById('breathingCircle');
            const text = document.getElementById('breathingText');
            let phase = 'inspire';
            let timeLeft = 4;
            
            if (breathingInterval) {
                clearInterval(breathingInterval);
            }
            
            circle.style.animation = 'breathe 8s infinite ease-in-out';
            
            breathingInterval = setInterval(() => {
                timeLeft--;
                
                if (timeLeft <= 0) {
                    if (phase === 'inspire') {
                        phase = 'hold';
                        timeLeft = 4;
                        text.textContent = 'Segure (4s) • Prepare para expirar';
                    } else if (phase === 'hold') {
                        phase = 'expire';
                        timeLeft = 4;
                        text.textContent = 'Expire (4s) • Solte o ar lentamente';
                    } else {
                        phase = 'inspire';
                        timeLeft = 4;
                        text.textContent = 'Inspire (4s) • Encha seus pulmões';
                    }
                } else {
                    if (phase === 'inspire') {
                        text.textContent = `Inspire (${timeLeft}s) • Encha seus pulmões`;
                    } else if (phase === 'hold') {
                        text.textContent = `Segure (${timeLeft}s) • Mantenha o ar`;
                    } else {
                        text.textContent = `Expire (${timeLeft}s) • Solte o ar lentamente`;
                    }
                }
            }, 1000);
        }

        // Acessibilidade
        function activateAccessibility() {
            showToast('Recursos de acessibilidade ativados');
        }

        // Animação do círculo de respiração
        const style = document.createElement('style');
        style.textContent = `
            @keyframes breathe {
                0%, 100% { transform: scale(1); }
                50% { transform: scale(1.3); }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
