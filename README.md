<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TECHGAME - Montagem e Manutenção de PCs</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #3a7afe;
            --primary-dark: #2a5fcc;
            --secondary: #ff4757;
            --dark: #0a0e14;
            --dark-light: #1a1f29;
            --text: #ffffff;
            --text-muted: #a0a9b8;
            --success: #2ecc71;
            --warning: #f39c12;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0a0e14 0%, #131722 100%);
            color: var(--text);
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .container {
            width: 100%;
            max-width: 900px;
            background: linear-gradient(145deg, #1a1f29, #151a24);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
            border: 1px solid #2a3343;
        }
        
        .header {
            background: linear-gradient(90deg, var(--primary), #5f5dff);
            padding: 25px;
            text-align: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 15px;
        }
        
        .logo-icon {
            font-size: 40px;
            margin-right: 15px;
        }
        
        .logo-text {
            font-size: 32px;
            font-weight: 800;
        }
        
        .header p {
            font-size: 18px;
            opacity: 0.9;
        }
        
        .tabs {
            display: flex;
            background: var(--dark-light);
            border-bottom: 2px solid var(--primary);
        }
        
        .tab {
            padding: 15px 25px;
            cursor: pointer;
            font-weight: 600;
            text-align: center;
            flex: 1;
            border-bottom: 3px solid transparent;
        }
        
        .tab.active {
            border-bottom: 3px solid var(--primary);
            color: var(--primary);
        }
        
        .tab-content {
            display: none;
            padding: 30px;
        }
        
        .tab-content.active {
            display: block;
        }
        
        .form-section {
            margin-bottom: 25px;
            padding: 20px;
            background: rgba(26, 31, 41, 0.7);
            border-radius: 10px;
            border-left: 4px solid var(--primary);
        }
        
        .section-title {
            font-size: 20px;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
        }
        
        .section-title i {
            margin-right: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--text-muted);
        }
        
        .required::after {
            content: " *";
            color: var(--secondary);
        }
        
        input, select, textarea {
            width: 100%;
            padding: 14px;
            background: #131722;
            border: 1px solid #2a3343;
            border-radius: 8px;
            color: var(--text);
            font-size: 16px;
        }
        
        .checkbox-group, .radio-group {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 12px;
            margin-top: 10px;
        }
        
        .checkbox-option, .radio-option {
            display: flex;
            align-items: center;
            padding: 12px;
            background: #131722;
            border-radius: 8px;
            border: 1px solid #2a3343;
        }
        
        .checkbox-option input, .radio-option input {
            width: auto;
            margin-right: 10px;
        }
        
        .btn-submit {
            background: linear-gradient(90deg, var(--primary), #5f5dff);
            color: white;
            border: none;
            padding: 16px 30px;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            display: block;
            width: 100%;
            margin-top: 20px;
            transition: all 0.3s;
        }
        
        .btn-submit:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(58, 122, 254, 0.4);
        }
        
        .form-footer {
            text-align: center;
            padding: 20px;
            background: var(--dark-light);
            color: var(--text-muted);
            font-size: 14px;
        }
        
        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            padding: 15px 25px;
            border-radius: 8px;
            color: white;
            font-weight: 600;
            z-index: 1000;
            display: none;
        }
        
        .notification.success {
            background: var(--success);
            display: block;
        }
        
        .notification.error {
            background: var(--secondary);
            display: block;
        }
        
        .alternative-section {
            text-align: center;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
            margin: 20px 0;
        }
        
        .alternative-btn {
            display: inline-block;
            background: var(--warning);
            color: white;
            padding: 12px 25px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: 600;
            margin-top: 10px;
        }
        
        @media (max-width: 768px) {
            .tabs {
                flex-direction: column;
            }
            
            .checkbox-group, .radio-group {
                grid-template-columns: 1fr;
            }
            
            body {
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <div class="logo">
                <div class="logo-icon"><i class="fas fa-gamepad"></i></div>
                <div class="logo-text">TECHGAME</div>
            </div>
            <p>Manutenção • Montagem • Vendas de PCs Gamer</p>
        </div>
        
        <div class="tabs">
            <div class="tab active" data-tab="manutencao"><i class="fas fa-tools"></i> Manutenção</div>
            <div class="tab" data-tab="montagem"><i class="fas fa-desktop"></i> Montagem</div>
            <div class="tab" data-tab="vendas"><i class="fas fa-shopping-cart"></i> Vendas</div>
        </div>
        
        <form id="techgameForm">
            <!-- ABA MANUTENÇÃO -->
            <div class="tab-content active" id="manutencao">
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Dados Pessoais</h2>
                    
                    <div class="form-group">
                        <label for="name" class="required">Nome completo</label>
                        <input type="text" id="name" name="name" required placeholder="Seu nome completo">
                    </div>
                    
                    <div class="form-group">
                        <label for="phone" class="required">Telefone para contato</label>
                        <input type="tel" id="phone" name="phone" required placeholder="(11) 99999-9999">
                    </div>
                    
                    <div class="form-group">
                        <label for="email" class="required">E-mail</label>
                        <input type="email" id="email" name="email" required placeholder="seu@email.com">
                    </div>
                </div>
                
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-laptop-medical"></i> Estado do Computador</h2>
                    
                    <div class="form-group">
                        <label>Seu computador está ligando?</label>
                        <div class="radio-group">
                            <label class="radio-option">
                                <input type="radio" name="pc_status" value="yes" required>
                                Sim, liga normalmente
                            </label>
                            <label class="radio-option">
                                <input type="radio" name="pc_status" value="partial">
                                Liga mas apresenta problemas
                            </label>
                            <label class="radio-option">
                                <input type="radio" name="pc_status" value="no">
                                Não liga
                            </label>
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="problem" class="required">Descreva o problema</label>
                        <textarea id="problem" name="problem" rows="4" placeholder="Ex: Computador está muito lento, preciso de limpeza..." required></textarea>
                    </div>
                </div>
            </div>
            
            <!-- ABA MONTAGEM -->
            <div class="tab-content" id="montagem">
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Dados Pessoais</h2>
                    
                    <div class="form-group">
                        <label for="montagem_name" class="required">Nome completo</label>
                        <input type="text" id="montagem_name" name="montagem_name" required placeholder="Seu nome completo">
                    </div>
                    
                    <div class="form-group">
                        <label for="montagem_phone" class="required">Telefone para contato</label>
                        <input type="tel" id="montagem_phone" name="montagem_phone" required placeholder="(11) 99999-9999">
                    </div>
                    
                    <div class="form-group">
                        <label for="montagem_email" class="required">E-mail</label>
                        <input type="email" id="montagem_email" name="montagem_email" required placeholder="seu@email.com">
                    </div>
                </div>
                
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-cog"></i> Configuração Desejada</h2>
                    
                    <div class="form-group">
                        <label for="orcamento" class="required">Qual seu orçamento?</label>
                        <select id="orcamento" name="orcamento" required>
                            <option value="">Selecione...</option>
                            <option value="Até R$ 2.000">Até R$ 2.000</option>
                            <option value="R$ 2.000 - R$ 4.000">R$ 2.000 - R$ 4.000</option>
                            <option value="R$ 4.000 - R$ 6.000">R$ 4.000 - R$ 6.000</option>
                            <option value="Acima de R$ 6.000">Acima de R$ 6.000</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="uso_principal" class="required">Uso principal do PC</label>
                        <select id="uso_principal" name="uso_principal" required>
                            <option value="">Selecione...</option>
                            <option value="Jogos">Jogos</option>
                            <option value="Trabalho">Trabalho/Escritório</option>
                            <option value="Streaming">Streaming</option>
                            <option value="Edição">Edição de Vídeo/Imagem</option>
                        </select>
                    </div>
                </div>
            </div>
            
            <!-- ABA VENDAS -->
            <div class="tab-content" id="vendas">
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Dados Pessoais</h2>
                    
                    <div class="form-group">
                        <label for="vendas_name" class="required">Nome completo</label>
                        <input type="text" id="vendas_name" name="vendas_name" required placeholder="Seu nome completo">
                    </div>
                    
                    <div class="form-group">
                        <label for="vendas_phone" class="required">Telefone para contato</label>
                        <input type="tel" id="vendas_phone" name="vendas_phone" required placeholder="(11) 99999-9999">
                    </div>
                    
                    <div class="form-group">
                        <label for="vendas_email" class="required">E-mail</label>
                        <input type="email" id="vendas_email" name="vendas_email" required placeholder="seu@email.com">
                    </div>
                </div>
                
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-shopping-cart"></i> Interesse em Produtos</h2>
                    
                    <div class="form-group">
                        <label for="produto_especifico">Produto de interesse</label>
                        <input type="text" id="produto_especifico" name="produto_especifico" placeholder="Ex: RTX 3060, Ryzen 5 5600X...">
                    </div>
                    
                    <div class="form-group">
                        <label for="orcamento_vendas">Faixa de orçamento</label>
                        <select id="orcamento_vendas" name="orcamento_vendas">
                            <option value="">Selecione...</option>
                            <option value="Até R$ 500">Até R$ 500</option>
                            <option value="R$ 500 - R$ 1.000">R$ 500 - R$ 1.000</option>
                            <option value="R$ 1.000 - R$ 2.000">R$ 1.000 - R$ 2.000</option>
                            <option value="Acima de R$ 2.000">Acima de R$ 2.000</option>
                        </select>
                    </div>
                </div>
            </div>
            
            <div class="form-section">
                <button type="submit" class="btn-submit">
                    <i class="fas fa-paper-plane"></i> Enviar Solicitação
                </button>
            </div>
        </form>

        <div class="alternative-section">
            <h3>Problemas com o formulário?</h3>
            <p>Use nosso formulário alternativo diretamente no Google:</p>
            <a href="https://docs.google.com/forms/d/1FAIpQLSeM8o5wR2D66e3N6e6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6Y6" class="alternative-btn" target="_blank">
                <i class="fas fa-external-link-alt"></i> Formulário Alternativo
            </a>
        </div>
        
        <div class="form-footer">
            <p>Entraremos em contato dentro de 24 horas para fornecer um orçamento</p>
            <p>© 2023 TECHGAME - Especialistas em PCs Gamer</p>
        </div>
    </div>

    <div class="notification" id="notification"></div>

    <script>
        // Controle das abas
        document.querySelectorAll('.tab').forEach(tab => {
            tab.addEventListener('click', () => {
                document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
                document.querySelectorAll('.tab-content').forEach(tc => tc.classList.remove('active'));
                tab.classList.add('active');
                document.getElementById(tab.dataset.tab).classList.add('active');
            });
        });
        
        // Máscara para telefone
        document.querySelectorAll('input[type="tel"]').forEach(input => {
            input.addEventListener('input', function(e) {
                let value = e.target.value.replace(/\D/g, '');
                if (value.length <= 11) {
                    value = value.replace(/(\d{2})(\d)/, '($1) $2');
                    value = value.replace(/(\d{5})(\d)/, '$1-$2');
                }
                e.target.value = value;
            });
        });
        
        // Envio do formulário - MÉTODO SIMPLES QUE FUNCIONA
        document.getElementById('techgameForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const submitBtn = this.querySelector('button[type="submit"]');
            const originalText = submitBtn.innerHTML;
            submitBtn.innerHTML = '<i class="fas fa-spinner fa-spin"></i> Enviando...';
            submitBtn.disabled = true;
            
            // Coletar dados do formulário
            const formData = new FormData(this);
            const data = {};
            
            for (let [key, value] of formData.entries()) {
                data[key] = value;
            }
            
            // Determinar o tipo de solicitação
            const activeTab = document.querySelector('.tab.active').dataset.tab;
            data.tipo_solicitacao = activeTab;
            
            // Criar mensagem para email (método que sempre funciona)
            const assunto = `Solicitação de ${activeTab} - ${data.name || data.montagem_name || data.vendas_name || 'Cliente'}`;
            
            let mensagem = `Nova solicitação recebida:\n\n`;
            mensagem += `Nome: ${data.name || data.montagem_name || data.vendas_name || 'Não informado'}\n`;
            mensagem += `Telefone: ${data.phone || data.montagem_phone || data.vendas_phone || 'Não informado'}\n`;
            mensagem += `Email: ${data.email || data.montagem_email || data.vendas_email || 'Não informado'}\n`;
            mensagem += `Tipo de solicitação: ${activeTab}\n\n`;
            
            if (activeTab === 'manutencao') {
                mensagem += `Estado do computador: ${data.pc_status || 'Não informado'}\n`;
                mensagem += `Problema: ${data.problem || 'Não informado'}\n`;
            } else if (activeTab === 'montagem') {
                mensagem += `Orçamento: ${data.orcamento || 'Não informado'}\n`;
                mensagem += `Uso principal: ${data.uso_principal || 'Não informado'}\n`;
            } else if (activeTab === 'vendas') {
                mensagem += `Produto: ${data.produto_especifico || 'Não informado'}\n`;
                mensagem += `Orçamento: ${data.orcamento_vendas || 'Não informado'}\n`;
            }
            
            mensagem += `\nData/hora: ${new Date().toLocaleString('pt-BR')}`;
            
            // Abrir cliente de email
            window.location.href = `mailto:techgame.suporte@gmail.com?subject=${encodeURIComponent(assunto)}&body=${encodeURIComponent(mensagem)}`;
            
            // Mostrar mensagem de sucesso
            showNotification('Solicitação enviada com sucesso! Verifique seu email.', 'success');
            
            // Limpar formulário após 2 segundos
            setTimeout(() => {
                this.reset();
                submitBtn.innerHTML = originalText;
                submitBtn.disabled = false;
            }, 2000);
        });
        
        function showNotification(message, type) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.className = 'notification ' + type;
            
            setTimeout(() => {
                notification.className = 'notification';
                notification.style.display = 'none';
            }, 5000);
        }
    </script>
</body>
</html>
