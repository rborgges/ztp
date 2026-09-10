
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
