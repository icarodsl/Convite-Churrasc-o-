<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Convite: Churrascão do Cabo Ícaro Lima</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* Estilização para a Fonte Inter */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap');
        body {
            font-family: 'Inter', sans-serif;
            /* Tema Marinha: Azul Marinho (Escuro) e Água (Claro) */
            background: linear-gradient(135deg, #e0f7fa 0%, #004d40 100%);
            min-height: 100vh;
        }
        /* Efeito de confete para celebração */
        .confetti-background {
            position: relative;
            overflow: hidden;
        }
        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            /* Cores de celebração (dourado e vermelho) */
            background-color: #fcd34d; 
            opacity: 0.7;
            border-radius: 50%;
            pointer-events: none;
            animation: fall linear infinite;
        }
        @keyframes fall {
            0% { transform: translateY(-100vh) rotate(0deg); opacity: 0; }
            10% { opacity: 0.7; }
            100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
        }
        /* Estilo do carrossel (ajustes finos para mobile) */
        .carousel-container {
            overflow: hidden;
            border-radius: 1rem;
            box-shadow: 0 10px 15px rgba(0, 0, 0, 0.15);
        }
        .carousel-track {
            display: flex;
            transition: transform 0.5s ease-in-out;
        }
        .carousel-slide {
            flex: 0 0 100%;
            width: 100%;
            height: 300px; /* Altura fixa para mobile */
            object-fit: cover;
        }

        /* Classes para o Modal */
        .modal {
            transition: opacity 0.3s ease, visibility 0.3s ease;
        }
        .modal-content {
            animation: slide-up 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        @keyframes slide-up {
            from { transform: translateY(20px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
    </style>
</head>
<body class="flex flex-col items-center pt-8 pb-12 p-4 min-h-screen">

    <!-- 
        =====================================================================================
        LINKS DAS FOTOS: 13 links do Google Drive fornecidos e um placeholder para a 14ª foto.
        Os links são convertidos automaticamente para exibição direta no carrossel.
        =====================================================================================
    -->
    <script>
        // Função que converte o link de compartilhamento do Google Drive para um link de imagem embutido.
        function getDirectDriveLink(shareLink) {
            const match = shareLink.match(/file\/d\/([a-zA-Z0-9_-]+)/);
            if (match && match[1]) {
                const fileId = match[1];
                return `https://drive.google.com/uc?export=download&id=${fileId}`;
            }
            // Retorna o link original ou um placeholder se não for um link de Drive válido
            return shareLink; 
        }

        const rawImageLinks = [
            "https://drive.google.com/file/d/1yce4NUNTO5XTwcw-qWG5sIpx_pIFFWdU/view?usp=drivesdk", // Foto 1
            "https://drive.google.com/file/d/1kIjTvbz8Kyr1fy_PCt6xwGS2O89xT9-B/view?usp=drivesdk", // Foto 2
            "https://drive.google.com/file/d/1R6Z7NXoeHyjUhsOgvtF2dmDEr7hTfbUR/view?usp=drivesdk", // Foto 3
            "https://drive.google.com/file/d/1ljwt39Zr8OUZ0eko-0HjxBeGcwfy68Zg/view?usp=drivesdk", // Foto 4
            "https://drive.google.com/file/d/1dE2EEDeiLj9u2Q0o2YMGj0yTsBDkeacu/view?usp=drivesdk", // Foto 5
            "https://drive.google.com/file/d/1ZwkO0KDtvfjIUatvM49Hht90KANSc1Ev/view?usp=drivesdk", // Foto 6
            "https://drive.google.com/file/d/19jL98gBIMe4h8pE17Q095O6l9Xv8t_fs/view?usp=drivesdk", // Foto 7
            "https://drive.google.com/file/d/18bOVG6nWjf7NrbeuB9TFEJkUB80eYoHd/view?usp=drivesdk", // Foto 8
            "https://drive.google.com/file/d/1-S0zVDW5Pos0mVztEv2tqh_3Xfz6b5Ob/view?usp=drivesdk", // Foto 9
            "https://drive.google.com/file/d/1eoEwCtjsm8oXwoxK905fCz6f3891N6cS/view?usp=drivesdk", // Foto 10
            "https://drive.google.com/file/d/1CiR32g8jqhSBa3dkf7w5LsN_tq4MjgIv/view?usp=drivesdk", // Foto 11
            "https://drive.google.com/file/d/1dX6htcHk7gaswJCZG-UhRFIU7Ik3x0oj/view?usp=drivesdk", // Foto 12
            "https://drive.google.com/file/d/1fg8L4PZbZ-o9rCW2uHE40lU_mG_bZz3s/view?usp=drivesdk", // Foto 13
            // A 14ª foto não foi fornecida, usando placeholder para completar o array
            "https://placehold.co/300x300/e5e7eb/4b5563?text=ADICIONAR+FOTO+14" 
        ];
        
        // A lista final de URLs convertidas para uso no carrossel.
        const images = rawImageLinks.map(link => getDirectDriveLink(link));

        let currentSlide = 0;
        
        const pixKey = "71981910268"; 
        const nomeConvidado = "Ícaro Lima"; 
        const cargo = "CABO DA MARINHA"; 
        const endereco = "Rua Benjamim de Souza, número 91 São Tomé de Paripe Praia de São Tomé"; 
        const dataLimite = "30/11/25"; 

    </script>

    <!-- Container Principal do Convite -->
    <div id="convite-card" class="bg-white p-6 sm:p-8 md:p-10 w-full max-w-lg shadow-2xl rounded-3xl text-center border-t-8 border-blue-800 transform transition-all duration-500 hover:shadow-3xl confetti-background">
        
        <!-- Título de Celebração (Azul Marinho e Dourado) -->
        <h1 class="text-4xl sm:text-5xl font-extrabold text-blue-800 mb-2 leading-tight">
            PROMOÇÃO & CHURRASCÃO! ⚓️
        </h1>
        <p class="text-lg text-gray-600 mb-6">Uma conquista de Categoria MÁXIMA para celebrar com a Família!</p>
        
        <div class="space-y-6 text-left">
            
            <!-- Notícia da Promoção -->
            <div class="bg-yellow-50 p-4 rounded-xl border border-yellow-200">
                <h2 class="text-xl font-bold text-yellow-700 mb-1">A Grande Novidade!</h2>
                <p class="text-gray-700">
                    Com muito orgulho, fui promovido(a) a:
                </p>
                <div class="mt-2 text-2xl font-black text-blue-900 bg-yellow-300 p-3 rounded-lg text-center shadow-inner uppercase">
                    <span id="cargo-display">CABO DA MARINHA</span>
                </div>
            </div>

            <!-- Carrossel de Fotos do Local -->
            <div class="carousel-container relative w-full">
                <div id="carousel-track" class="carousel-track">
                    <div id="loading-message" class="flex items-center justify-center w-full h-[300px] bg-gray-200 text-gray-600 font-semibold">
                        Carregando as fotos do local...
                    </div>
                </div>
                <!-- Botões de Navegação -->
                <button onclick="prevSlide()" class="absolute left-2 top-1/2 transform -translate-y-1/2 bg-black bg-opacity-30 p-2 rounded-full text-white z-10 hover:bg-opacity-60 transition">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7"></path></svg>
                </button>
                <button onclick="nextSlide()" class="absolute right-2 top-1/2 transform -translate-y-1/2 bg-black bg-opacity-30 p-2 rounded-full text-white z-10 hover:bg-opacity-60 transition">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path></svg>
                </button>
                <div id="carousel-dots" class="absolute bottom-2 left-1/2 transform -translate-x-1/2 flex space-x-2">
                    <!-- Dots são injetados via JavaScript -->
                </div>
            </div>
            <p class="text-center text-sm font-medium text-gray-600 -mt-4 mb-2">Nosso QG no dia 3 de Dezembro! (Churrascão com Piscina e Lazer)</p>

            <!-- Detalhes do Evento -->
            <div class="bg-blue-50 p-4 rounded-xl border border-blue-200">
                <h2 class="text-xl font-bold text-blue-600 mb-3 flex items-center">
                    <svg class="w-6 h-6 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                    Data e Local da Celebração
                </h2>
                <p class="text-gray-700 font-semibold mb-1">🗓️ Data:</p>
                <p class="text-xl font-extrabold text-gray-800">3 de Dezembro de 2025</p>

                <p class="text-gray-700 font-semibold mt-3 mb-1">📍 Endereço:</p>
                <p class="text-base font-medium text-gray-800 bg-white p-2 border rounded-lg shadow-sm">
                    <span id="local-display">Rua Benjamim de Souza, número 91 São Tomé de Paripe Praia de São Tomé</span>
                </p>
            </div>
            
            <!-- Opção de Contribuição PIX -->
            <div class="bg-red-50 p-4 rounded-xl border border-red-200 text-center">
                <h3 class="text-lg font-bold text-red-700 mb-2">Contribuição: Sua Ajuda é Bem-Vinda!</h3>
                <p class="text-sm text-gray-700 mb-4">
                    Para um churrasco mais farto, quem puder contribuir de alguma forma com o PIX, agradeço! Mas, lembre-se: **sua presença é o presente mais importante!**
                </p>
                <button onclick="showPixModal()"
                        class="w-full py-2 px-4 bg-red-600 text-white font-bold rounded-lg shadow-md hover:bg-red-700 transition duration-300 transform hover:scale-[1.02]">
                    CLIQUE AQUI PARA CONTRIBUIR VIA PIX
                </button>
            </div>
        </div>

        <!-- Botão de Confirmação e Assinatura -->
        <div class="mt-8">
            <p class="text-sm font-semibold text-red-600 mb-2">⚠️ Por favor, confirme até o dia: <span id="data-limite">30/11/25</span></p>
            <button onclick="showMessage('Obrigado(a)! Sua presença foi registrada! Conto com você. (Esta é uma confirmação de visualização. Por favor, envie sua confirmação oficial por mensagem ao Ícaro.)')"
                    class="w-full py-3 px-6 bg-blue-700 text-white font-bold text-lg rounded-xl shadow-lg hover:bg-blue-800 transition duration-300 transform hover:scale-[1.02] active:scale-100">
                CONFIRMAR MINHA PRESENÇA!
            </button>
            
            <p class="mt-6 text-xl font-semibold text-gray-800">
                Mal vejo a hora de estarmos juntos!
                <br>
                <span class="font-black text-3xl text-blue-900 mt-1" id="nome-display">Ícaro Lima</span>
            </p>
        </div>
    </div>
    
    <!-- Modal de Confirmação de Presença -->
    <div id="confirm-modal" class="modal hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
        <div class="modal-content bg-white p-6 rounded-xl shadow-2xl max-w-sm w-full text-center">
            <h3 class="text-xl font-bold text-green-700 mb-3">Confirmado!</h3>
            <p id="modal-message" class="text-gray-700 mb-4"></p>
            <button onclick="hideModal('confirm-modal')" class="bg-green-500 text-white py-2 px-4 rounded-lg font-semibold hover:bg-green-600 transition">Fechar</button>
        </div>
    </div>

    <!-- Modal PIX -->
    <div id="pix-modal" class="modal hidden fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50 p-4">
        <div class="modal-content bg-white p-6 rounded-xl shadow-2xl max-w-md w-full text-center">
            <h3 class="text-2xl font-bold text-red-700 mb-4">Contribuição Voluntária via PIX</h3>
            
            <p class="text-gray-700 mb-4">Obrigado(a) por querer ajudar o Churrascão de Promoção do Cabo Ícaro!</p>
            
            <!-- QR Code (Placeholder) -->
            <div class="mx-auto w-40 h-40 mb-4 p-2 border-4 border-blue-600 rounded-lg">
                <img id="qrcode-img" src="https://placehold.co/150x150/0d47a1/ffffff?text=PIX+71981910268" alt="QR Code PIX" class="w-full h-full object-cover">
            </div>
            
            <p class="text-sm font-semibold text-gray-600 mb-2">CÓDIGO COPIA E COLA (Telefone):</p>
            <div class="bg-gray-100 p-3 rounded-lg border border-gray-300 flex items-center justify-between">
                <span id="pix-code" class="text-base break-all text-gray-800 font-mono font-bold">71981910268</span>
                <button onclick="copyPixCode()" class="ml-3 p-1 bg-red-600 rounded text-white hover:bg-red-700 transition" title="Copiar Código">
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 5H6a2 2 0 00-2 2v10a2 2 0 002 2h2m0-10h8m-8 0V5h8v4m-4 5h4m-4 0v4m-4-4h4m-4 0v4"></path></svg>
                </button>
            </div>
            
            <button onclick="hideModal('pix-modal')" class="mt-6 bg-blue-700 text-white py-2 px-4 rounded-lg font-semibold hover:bg-blue-800 transition">Fechar</button>
        </div>
    </div>


    <script>
        // --- Funções de Modal ---
        function showMessage(message) {
            document.getElementById('modal-message').innerText = message;
            document.getElementById('confirm-modal').classList.remove('hidden');
        }

        function hideModal(id) {
            document.getElementById(id).classList.add('hidden');
        }
        
        function showPixModal() {
            document.getElementById('pix-modal').classList.remove('hidden');
        }

        function copyPixCode() {
            const pixCode = document.getElementById('pix-code').innerText;
            // Usando execCommand para garantir compatibilidade em iframes
            const tempInput = document.createElement('textarea');
            tempInput.value = pixCode;
            document.body.appendChild(tempInput);
            tempInput.select();
            document.execCommand('copy');
            document.body.removeChild(tempInput);

            // Muda o botão para indicar que copiou
            showMessage('Código PIX (Telefone) Copiado! Faça sua contribuição. 🥳');
            // Não escondemos o modal PIX automaticamente, mas o de confirmação aparece por cima
        }

        // --- Funções de Carrossel (Carousel) ---
        const track = document.getElementById('carousel-track');
        const dotsContainer = document.getElementById('carousel-dots');
        const loadingMessage = document.getElementById('loading-message');

        function generateCarousel() {
            // Remove a mensagem de carregamento
            if (loadingMessage) {
                loadingMessage.remove();
            }

            // Limpa slides e dots anteriores
            track.innerHTML = '';
            dotsContainer.innerHTML = '';

            images.forEach((src, index) => {
                // Adiciona o slide (imagem)
                const slide = document.createElement('img');
                slide.src = src;
                slide.alt = `Foto do local da festa ${index + 1}`;
                slide.classList.add('carousel-slide');
                slide.onerror = function() {
                    // Fallback se a imagem não carregar (muito útil para o placeholder da 14ª foto)
                    this.src = `https://placehold.co/300x300/e5e7eb/4b5563?text=FOTO+${index + 1}+INDISPONÍVEL`;
                    this.alt = "Imagem não carregada. Verifique se o link foi compartilhado publicamente.";
                };
                // Previne o CLS (Cumulative Layout Shift)
                slide.setAttribute('loading', 'lazy'); 
                track.appendChild(slide);

                // Adiciona o indicador (dot)
                const dot = document.createElement('span');
                dot.classList.add('w-2', 'h-2', 'rounded-full', 'bg-white', 'opacity-50', 'cursor-pointer', 'transition');
                dot.setAttribute('data-index', index);
                dot.onclick = () => goToSlide(index);
                dotsContainer.appendChild(dot);
            });
            updateCarousel();
        }

        function updateCarousel() {
            if (images.length === 0) return; // Não faz nada se não houver imagens
            
            const offset = -currentSlide * 100;
            track.style.transform = `translateX(${offset}%)`;

            // Atualiza os indicadores
            dotsContainer.querySelectorAll('span').forEach((dot, index) => {
                dot.classList.toggle('bg-opacity-100', index === currentSlide);
                dot.classList.toggle('opacity-50', index !== currentSlide);
                dot.classList.toggle('bg-blue-800', index === currentSlide);
            });
        }

        function nextSlide() {
            currentSlide = (currentSlide + 1) % images.length;
            updateCarousel();
        }

        function prevSlide() {
            currentSlide = (currentSlide - 1 + images.length) % images.length;
            updateCarousel();
        }

        function goToSlide(index) {
            currentSlide = index;
            updateCarousel();
        }
        
        // --- Chuva de Confetes ---
        function createConfetti() {
            const card = document.getElementById('convite-card');
            for (let i = 0; i < 50; i++) {
                const confetti = document.createElement('div');
                confetti.classList.add('confetti');
                
                confetti.style.left = Math.random() * 100 + '%';
                // Cores do tema (Dourado, Vermelho e Azul Marinho)
                confetti.style.backgroundColor = ['#fcd34d', '#dc2626', '#1e3a8a'][Math.floor(Math.random() * 3)];
                
                confetti.style.animationDuration = (Math.random() * 2 + 3) + 's';
                confetti.style.animationDelay = (Math.random() * 5) + 's'; 
                
                card.appendChild(confetti);
            }
        }

        // --- Inicialização ---
        window.onload = function() {
            generateCarousel();
            createConfetti();
            // Carrossel automático a cada 5 segundos
            if (images.length > 1) {
                setInterval(nextSlide, 5000); 
            }
        };
    </script>
</body>
</html>
