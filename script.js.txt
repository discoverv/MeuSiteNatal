const senhaCorreta = "cristiana1689";

// Função para entrar no painel
function entrarPainel() {
    const senhaInput = document.getElementById("senhaInput").value;
    const loginMensagem = document.getElementById("loginMensagem");
    const loginContainer = document.getElementById("loginContainer");
    const painelContainer = document.getElementById("painelContainer");

    if (senhaInput === senhaCorreta) {
        loginContainer.style.display = "none";
        painelContainer.style.display = "block";
        loginMensagem.innerText = "";
    } else {
        loginMensagem.innerText = "Senha incorreta. Tente novamente.";
        loginMensagem.className = "feedback-msg error";
    }
}

// Função para mostrar o formulário de reembolso
function mostrarReembolso() {
    const reembolsoForm = document.getElementById("reembolsoForm");
    reembolsoForm.style.display = reembolsoForm.style.display === "none" || reembolsoForm.style.display === "" ? "block" : "none";
}

// Função para processar reembolso
function processarReembolso() {
    const idCompra = document.getElementById("idCompraInput").value;
    const reembolsoMensagem = document.getElementById("reembolsoMensagem");

    if (idCompra) {
        reembolsoMensagem.innerText = "Reembolso enviado para o ID: " + idCompra;
        reembolsoMensagem.className = "feedback-msg success";
    } else {
        reembolsoMensagem.innerText = "Por favor, insira um ID de compra válido.";
        reembolsoMensagem.className = "feedback-msg error";
    }

    // Limpa o campo de entrada
    document.getElementById("idCompraInput").value = "";
}

// Função para mostrar o formulário de apoio técnico
function mostrarApoio() {
    const apoioForm = document.getElementById("apoioForm");
    apoioForm.style.display = apoioForm.style.display === "none" || apoioForm.style.display === "" ? "block" : "none";
}

// Função para processar apoio técnico
function processarApoio() {
    const nickUsuario = document.getElementById("nickUsuarioInput").value;
    const motivo = document.getElementById("motivoInput").value;
    const apoioMensagem = document.getElementById("apoioMensagem");

    if (nickUsuario && motivo) {
        apoioMensagem.innerText = "Apoio técnico enviado para o usuário: " + nickUsuario + " com motivo: " + motivo;
        apoioMensagem.className = "feedback-msg success";
    } else {
        apoioMensagem.innerText = "Por favor, preencha todos os campos.";
        apoioMensagem.className = "feedback-msg error";
    }

    // Limpa os campos de entrada
    document.getElementById("nickUsuarioInput").value = "";
    document.getElementById("motivoInput").value = "";
}
