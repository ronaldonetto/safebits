# Checklist de Segurança

Avalie rapidamente a segurança digital do seu negócio.
Marque os itens que já estão implementados e acompanhe sua pontuação.

---

# Avaliação de Segurança

---

<div style="margin-bottom:10px;">
  <strong>Pontuação:</strong>
  <span id="resultado">0%</span>
</div>

<div id="nivel" style="margin-bottom:10px;">
  🔴 Risco Alto
</div>

<div id="recomendacao" style="margin-top:10px;"></div>

<progress
  id="barra"
  value="0"
  max="100"
  style="width:100%; height:25px;">
</progress>

<style>
#barra::-webkit-progress-bar {
background-color: #e5e7eb;
border-radius: 100px;
}

#barra {
  width: 100%;
  height: 25px;
  border-radius: 8px;
}

.risco-alto::-webkit-progress-value {
background-color: #dc2626;
}

.risco-medio::-webkit-progress-value {
background-color: #eab308;
}

.boa-protecao::-webkit-progress-value {
background-color: #16a34a;
}

.risco-alto::-moz-progress-bar {
background-color: #dc2626;
}

.risco-medio::-moz-progress-bar {
background-color: #eab308;
}

.boa-protecao::-moz-progress-bar {
background-color: #16a34a;
}


</style>

## Contas e Senhas

- <label><input type="checkbox" class="item"> Utilizo senhas únicas para cada serviço.</label>
- <label><input type="checkbox" class="item"> Uso um gerenciador de senhas.</label>
- <label><input type="checkbox" class="item"> Tenho autenticação em dois fatores (2FA/MFA) ativada.</label>
- <label><input type="checkbox" class="item"> Removo acessos de funcionários que não trabalham mais na empresa.</label>

## Backup e Recuperação

- <label><input type="checkbox" class="item"> Faço backup dos arquivos importantes regularmente.</label>
- <label><input type="checkbox" class="item"> Testei a restauração dos backups.</label>
- <label><input type="checkbox" class="item"> Tenho pelo menos uma cópia offline ou em outro local.</label>
- <label><input type="checkbox" class="item"> Sei quanto tempo levaria para recuperar meus dados após um incidente.</label>

## Uso Seguro de Inteligência Artificial

- <label><input type="checkbox" class="item"> Não envio dados sensíveis de clientes para ferramentas de IA públicas.</label>
- <label><input type="checkbox" class="item"> Não compartilho documentos financeiros com IA.</label>
- <label><input type="checkbox" class="item"> Verifico informações geradas pela IA antes de utilizá-las.</label>
- <label><input type="checkbox" class="item"> Minha equipe sabe quais dados podem ou não ser enviados para ferramentas de IA.</label>


## Segurança de E-mail 

- <label><input type="checkbox" class="item"> Uso MFA no e-mail corporativo.</label>
- <label><input type="checkbox" class="item"> Minha equipe sabe identificar phishing.</label>
- <label><input type="checkbox" class="item"> Confirmo solicitações financeiras por outro canal.</label>
- <label><input type="checkbox" class="item"> Não clico em links suspeitos sem verificar a origem.</label>

## Dispositivos e Sistemas

- <label><input type="checkbox" class="item"> Todos os computadores possuem antivírus atualizado.</label>
- <label><input type="checkbox" class="item"> Os sistemas operacionais estão atualizados.</label>
- <label><input type="checkbox" class="item"> Programas sem uso são removidos.</label>
- <label><input type="checkbox" class="item"> Apenas pessoas autorizadas possuem acesso administrativo.</label>

## Aplicativos e Ferramentas Online

- <label><input type="checkbox" class="item"> Revisei as permissões dos aplicativos conectados.</label>
- <label><input type="checkbox" class="item"> Utilizo apenas ferramentas confiáveis.</label>
- <label><input type="checkbox" class="item"> Verifico as políticas de privacidade dos serviços utilizados.</label>
- <label><input type="checkbox" class="item"> Sei onde os dados dos clientes estão armazenados.</label>

## Conscientização da Equipe

- <label><input type="checkbox" class="item"> Minha equipe recebeu orientação sobre golpes digitais.</label>
- <label><input type="checkbox" class="item"> Existe um procedimento para reportar atividades suspeitas.</label>
- <label><input type="checkbox" class="item"> Os colaboradores sabem como proteger dados de clientes.</label>
- <label><input type="checkbox" class="item"> Realizamos revisões periódicas de segurança.</label>

--- 

<script>
document.addEventListener("DOMContentLoaded", () => {

  function atualizarPontuacao() {
const total = document.querySelectorAll('.item').length;
const marcados = document.querySelectorAll('.item:checked').length;

const porcentagem = Math.round((marcados / total) * 100);

document.getElementById('resultado').textContent =
porcentagem + '%';

document.getElementById('barra').value =
porcentagem;

const barra = document.getElementById('barra');
const nivel = document.getElementById('nivel');

barra.classList.remove(
'risco-alto',
'risco-medio',
'boa-protecao'
);

if (porcentagem <= 40) {
nivel.textContent = '🔴 Risco Alto';
barra.classList.add('risco-alto');

} else if (porcentagem <= 70) {
nivel.textContent = '🟡 Risco Médio';
barra.classList.add('risco-medio');

} else {
nivel.textContent = '🟢 Boa Proteção';
barra.classList.add('boa-protecao');
}

const recomendacao = document.getElementById('recomendacao');

if (porcentagem <= 40) {
  recomendacao.textContent =
    'Sua empresa apresenta vulnerabilidades significativas.';
} else if (porcentagem <= 70) {
  recomendacao.textContent =
    'Sua empresa possui algumas boas práticas, mas ainda há melhorias importantes.';
} else {
  recomendacao.textContent =
    'Bom trabalho! Continue revisando suas práticas regularmente.';
}

}

  document.querySelectorAll('.item').forEach(item => {
    item.addEventListener('change', atualizarPontuacao);
  });

  atualizarPontuacao();

});




</script>





