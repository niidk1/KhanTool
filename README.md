# KhanTool Cheat

```js
javascript:(function(){const formHtml=`<div id="authForm" style="position:fixed;top:50%;left:50%;transform:translate(-50%,-50%);background-color:white;border:1px solid black;padding:20px;z-index:1000;"><h2>Autenticação</h2><label for="username">Nome de Usuário:</label><br><input type="text" id="username" required><br><br><label for="token">Token:</label><br><input type="text" id="token" required><br><br><button id="submitBtn">Enviar</button><button id="cancelBtn">Cancelar</button></div>`;document.body.insertAdjacentHTML('beforeend',formHtml);const submitBtn=document.getElementById('submitBtn');const cancelBtn=document.getElementById('cancelBtn');submitBtn.onclick=function(){const user=document.getElementById('username').value;const token=document.getElementById('token').value;if(!user||!token){alert('Por favor, preencha todos os campos.');return;}fetch(`https://teste-api-lilac.vercel.app/script?user=${encodeURIComponent(user)}&token=${encodeURIComponent(token)}`).then(response=>response.text()).then(script=>{if(script&&!script.trim().startsWith('<')){eval(script);document.getElementById('authForm').remove();}else{alert('Erro na resposta do servidor.');}}).catch(error=>alert('Erro ao buscar o script: '+error.message));};cancelBtn.onclick=function(){document.getElementById('authForm').remove();};})();
```


# KhanTool (ios)

```js
javascript:(function(){var formDiv=document.createElement('div');formDiv.id='authForm';formDiv.style.position='fixed';formDiv.style.top='50%';formDiv.style.left='50%';formDiv.style.transform='translate(-50%,-50%)';formDiv.style.backgroundColor='white';formDiv.style.border='1px solid black';formDiv.style.padding='20px';formDiv.style.zIndex='1000';formDiv.style.boxShadow='0 0 10px rgba(0,0,0,0.5)';formDiv.style.maxWidth='90%';formDiv.innerHTML=`<h2 style="text-align: center;">Autenticação</h2><label for="username">Nome de Usuário:</label><br><input type="text" id="username" required style="width: 100%;"><br><br><label for="token">Token:</label><br><input type="text" id="token" required style="width: 100%;"><br><br><button id="submitBtn" style="width: 100%;">Enviar</button><button id="cancelBtn" style="width: 100%; background-color: red; color: white;">Cancelar</button>`;document.body.appendChild(formDiv);document.getElementById('submitBtn').onclick=function(){var user=document.getElementById('username').value;var token=document.getElementById('token').value;if(!user||!token){alert('Por favor, preencha todos os campos.');return;}fetch(`https://teste-api-lilac.vercel.app/script?user=${encodeURIComponent(user)}&token=${encodeURIComponent(token)}`).then(response=>response.text()).then(script=>{if(script&&!script.trim().startsWith('<')){eval(script);document.getElementById('authForm').remove();}else{alert('Erro na resposta do servidor.');}}).catch(error=>alert('Erro ao buscar o script: '+error.message));};document.getElementById('cancelBtn').onclick=function(){document.getElementById('authForm').remove();};})();
```

