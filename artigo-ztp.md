🚀 Automação de Configuração com Python e ZTP
Este artigo demonstra como utilizar Python e Zero Touch Provisioning (ZTP) para configurar automaticamente um dispositivo Cisco Catalyst 8000 (CAT8K).

📜 Script de Configuração
O trecho abaixo utiliza a biblioteca cli para aplicar configurações essenciais:

python
import cli

cli.configurep([
    "hostname CAT8K",
    "interface GigabitEthernet1",
    "ip address dhcp",
    "no shutdown",
    "username admin privilege 15 secret C1sc0123!",
    "ip http server",
    "ip http secure-server",
    "ip http authentication local",
    "ip domain name ine.local",
    "crypto key generate rsa modulus 2048",
    "ip ssh version 2",
    "line vty 0 4",
    "login local",
    "transport input ssh",
    "interface Loopback0",
    "ip address 10.10.10.1 255.255.255.255",
    "description Created via ZTP Python script"
])
🔑 Destaques da Configuração
Hostname definido como CAT8K

Interface GigabitEthernet1 com IP via DHCP

Usuário admin com privilégio 15 e senha criptografada

Serviços HTTP/HTTPS habilitados

SSH versão 2 configurado

Loopback0 criado com IP 10.10.10.1

🌐 Servidor HTTP para Distribuição
Para disponibilizar o script via HTTP, execute no prompt de comando:

bash
python -m http.server 80
📦 Configuração de DHCP para ZTP
O pool DHCP garante que os dispositivos recebam automaticamente o script de inicialização:

Código
ip dhcp pool ZTP-POOL
 network 10.199.199.0 255.255.255.0
 default-router 10.199.199.254
 option 67 ascii http://10.199.199.100/ztp_script.py
✅ Conclusão
Com essa abordagem, é possível automatizar a configuração inicial de dispositivos Cisco, reduzindo tempo de provisionamento e erros manuais. O ZTP aliado ao Python oferece flexibilidade e escalabilidade para ambientes corporativos.

👉 Agora, para enviar esse artigo ao seu GitHub, você pode seguir estes passos rápidos:

Crie um arquivo README.md ou artigo.md com o conteúdo acima.

No terminal, execute:

bash
git add artigo.md
git commit -m "Adiciona artigo sobre ZTP com Python"
git push origin main
Quer que eu já formate esse artigo em Markdown pronto para README.md para você copiar e colar direto no seu repositório?

sim
Perfeito, Roberto! Aqui está o artigo já formatado em Markdown para você copiar e colar direto no seu repositório GitHub como README.md ou artigo.md:

markdown
# 🚀 Automação de Configuração com Python e ZTP

Este artigo demonstra como utilizar **Python** e **Zero Touch Provisioning (ZTP)** para configurar automaticamente um dispositivo Cisco Catalyst 8000 (CAT8K).

---

## 📜 Script de Configuração

O trecho abaixo utiliza a biblioteca `cli` para aplicar configurações essenciais:

```python
import cli

cli.configurep([
    "hostname CAT8K",
    "interface GigabitEthernet1",
    "ip address dhcp",
    "no shutdown",
    "username admin privilege 15 secret C1sc0123!",
    "ip http server",
    "ip http secure-server",
    "ip http authentication local",
    "ip domain name ine.local",
    "crypto key generate rsa modulus 2048",
    "ip ssh version 2",
    "line vty 0 4",
    "login local",
    "transport input ssh",
    "interface Loopback0",
    "ip address 10.10.10.1 255.255.255.255",
    "description Created via ZTP Python script"
])
🔑 Destaques da Configuração
Hostname definido como CAT8K

Interface GigabitEthernet1 com IP via DHCP

Usuário admin com privilégio 15 e senha criptografada

Serviços HTTP/HTTPS habilitados

SSH versão 2 configurado

Loopback0 criado com IP 10.10.10.1

🌐 Servidor HTTP para Distribuição
Para disponibilizar o script via HTTP, execute no prompt de comando:

bash
python -m http.server 80
📦 Configuração de DHCP para ZTP
O pool DHCP garante que os dispositivos recebam automaticamente o script de inicialização:

Código
ip dhcp pool ZTP-POOL
 network 10.199.199.0 255.255.255.0
 default-router 10.199.199.254
 option 67 ascii http://10.199.199.100/ztp_script.py
✅ Conclusão
Com essa abordagem, é possível automatizar a configuração inicial de dispositivos Cisco, reduzindo tempo de provisionamento e erros manuais. O ZTP aliado ao Python oferece flexibilidade e escalabilidade para ambientes corporativos.

Código

---

👉 Agora basta salvar esse conteúdo em um arquivo `.md` e rodar os comandos:

```bash
git add artigo.md
git commit -m "Adiciona artigo sobre ZTP com Python"
git push origin main
Quer que eu te mostre também como criar um novo repositório no GitHub e já subir esse artigo lá, passo a passo?

comandos para conectar no meu github
Para conectar seu projeto local ao GitHub e enviar o artigo que criamos, você pode seguir estes comandos básicos no terminal. Vou assumir que você já tem o Git instalado e uma conta no GitHub:

🔧 Passo a Passo
Inicializar o repositório local

bash
git init
Adicionar o arquivo do artigo

bash
git add artigo.md
Criar o primeiro commit

bash
git commit -m "Adiciona artigo sobre ZTP com Python"
Conectar ao repositório remoto no GitHub

Substitua SEU_USUARIO pelo seu nome de usuário e NOME_REPOSITORIO pelo repositório que você criou no GitHub:

bash
git remote add origin https://github.com/SEU_USUARIO/NOME_REPOSITORIO.git
Enviar para o GitHub

bash
git push -u origin main
📌 Observações
Se o repositório no GitHub estiver vazio, certifique-se de que a branch principal seja chamada main (ou master, dependendo da configuração).

Caso seja a primeira vez que você usa GitHub no seu PC, será necessário configurar seu nome e email:

bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
👉 Quer que eu te mostre também como criar o repositório no GitHub via interface web antes de rodar esses comandos?
