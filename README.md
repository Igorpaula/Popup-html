# Popup-html

<style>

/* 1. Estilos do Popup (Modal) e Sobreposição */

#popup-modal-elementor {
    display: none; 
    position: fixed; 
    z-index: 10000; 
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto; 
    background-color: rgba(0, 0, 0, 0.75); 
    backdrop-filter: blur(2px); 
}


/* 2. Conteúdo do Popup (TAMANHO FIXO) */

.popup-content-elementor {
    /* Centraliza o conteúdo */
    margin: 5% auto; 
    position: relative;
    padding: 0; 
    border: none;
    background-color: transparent; 
    
    /* DEFINIÇÃO DO TAMANHO DA LARGURA MÁXIMA PARA CONTROLAR A ALTURA (405px) */
    max-width: 400px; 
    
    /* Garante responsividade em telas menores que 405px */
    width: 90%; 
    
    border-radius: 8px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5); 
}


/* 3. Estilo da Imagem */

#popup-image-elementor {
    display: block; 
    width: 100%; 
    /* A altura será controlada pela largura do container, mantendo a proporção. */
    height: auto; 
    border-radius: 8px; 
}


/* 4. Estilo do Botão Fechar (X) */

.close-button-elementor {
    color: #444; 
    font-size: 32px;
    font-weight: bold;
    cursor: pointer;
    line-height: 28px;
    position: absolute; 
    top: -15px; 
    right: -15px; 
    z-index: 10001; 
    background: white; 
    border-radius: 50%;
    width: 35px;
    height: 35px;
    text-align: center;
    line-height: 32px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.close-button-elementor:hover {
    color: #c0392b; 
}

/* Estilo para telas menores para garantir que o X não saia da tela */
@media (max-width: 400px) {
    .close-button-elementor {
        top: -10px;
        right: -10px;
        font-size: 24px;
        width: 30px;
        height: 30px;
        line-height: 28px;
    }
    .popup-content-elementor {
        /* Ajuste a margem para telas muito pequenas */
        margin: 5% auto;
        /* Em telas menores que 405px, o width: 90% assume o controle */
    }
}
</style>



<div id="popup-modal-elementor">
    <div class="popup-content-elementor">
        <span class="close-button-elementor" onclick="fecharPopupElementor()">&times;</span>
        <img id="popup-image-elementor" src="https://greatlord.com.br/wp-content/uploads/2025/12/1337698663695534abe7e961.18826244-1.jpeg" alt="Aviso de Férias Coletivas">
    </div>
</div>


<script>
    // Funções JS
    
    function fecharPopupElementor() {
        document.getElementById('popup-modal-elementor').style.display = 'none';
    }

    function abrirPopupElementor() {
        var modal = document.getElementById('popup-modal-elementor');
        modal.style.display = 'block';
    }

    // Carregar o Popup Automaticamente
    document.addEventListener('DOMContentLoaded', function() {
        setTimeout(abrirPopupElementor, 500); 
    });

    // Fechar o Popup ao clicar na área escura
    document.getElementById('popup-modal-elementor').addEventListener('click', function(event) {
        if (event.target === this) {
            fecharPopupElementor();
        }
    });

    // Fechar ao apertar a tecla ESC
    document.addEventListener('keydown', function(event) {
        if (event.key === 'Escape') {
            fecharPopupElementor();
        }
    });
</script>
