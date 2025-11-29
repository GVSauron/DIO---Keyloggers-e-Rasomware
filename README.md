# DIO-Keyloggers-e-Rasomware
# Funcionamento Prático de Ransomware e Keyloggers  
**Como esses malwares exploram vulnerabilidades técnicas e brechas humanas**

Este documento apresenta uma explicação detalhada, clara e segura sobre os mecanismos **conceituais** de funcionamento de *ransomware* e *keyloggers*, bem como as falhas humanas e técnicas que esses malwares exploram.  
O conteúdo é **educacional**, orientado à compreensão e à defesa — sem qualquer instrução operacional capaz de ser usada para criar malware.


# 📌 1. O que é Malware?
“Malware” é um termo que engloba qualquer software criado para causar danos, roubar dados ou obter algum tipo de vantagem indevida. Dois tipos bastante conhecidos são:

- **Ransomware** → Sequestra dados por meio de criptografia e exige pagamento.  
- **Keylogger** → Registra teclas digitadas para capturar senhas e informações sensíveis.

Ambos compartilham um ponto-chave: **exploram vulnerabilidades técnicas e, principalmente, brechas humanas.**

# 🕸️ 2. Funcionamento Prático de um Ransomware

## 2.1. Fases de atuação
Embora cada variante tenha suas particularidades, o funcionamento de um ransomware costuma seguir uma estrutura lógica:

### **1. Infecção inicial**
O malware precisa entrar na máquina da vítima. Isso costuma ocorrer por:
- anexos maliciosos enviados por e-mail (phishing);
- downloads de sites comprometidos;
- exploração de falhas em serviços expostos à internet;
- pendrives com arquivos parasitas.

### **2. Estabelecimento no sistema**
Uma vez executado, o ransomware:
- se copia para locais estratégicos do sistema;
- registra rotinas de inicialização automática;
- verifica o ambiente (ex.: se está em máquina virtual, sandbox ou SO específico);
- tenta elevar privilégios.

Nenhuma ação destrutiva ocorre ainda — essa fase é preparatória.

### **3. Comunicação com o servidor do atacante**
A maioria das famílias de ransomware:
- coleta informações básicas da máquina;
- obtém chaves criptográficas;
- registra a máquina como “infectada”.

Essa etapa permite que o atacante gerencie o sequestro de dados de forma individualizada.

### **4. Criptografia dos arquivos**
Ponto central do ataque.  
O malware percorre discos e servidores, criptografando arquivos usando algoritmos fortes (AES, RSA, etc.).  
Características comuns:
- ignorar arquivos críticos do sistema (para não inutilizar o computador completamente);
- excluir cópias de sombra (Shadow Copies);
- renomear arquivos ou alterar extensões;
- gerar uma chave única por máquina.

### **5. Mensagem de resgate**
Após criptografar os arquivos, o ransomware exibe instruções pedindo pagamento, normalmente via:
- criptomoedas;
- serviços de anonimização como Tor.

O objetivo é criar pressão psicológica, fazendo o usuário acreditar que **não há alternativa**.

# 🖥️ 3. Funcionamento Prático de um Keylogger

## 3.1. O que um keylogger faz conceitualmente
O propósito central é simples: **capturar o que o usuário digita**. Isso inclui:
- senhas;
- conversas;
- número de cartões de crédito;
- pesquisas realizadas;
- comandos de terminal.

## 3.2. Formas conceituais de operação

### **1. Captura de eventos de teclado**
Um keylogger pode:
- interceptar eventos de teclado da interface gráfica;  
- ler buffers internos do sistema;  
- monitorar APIs responsáveis por entrada de dados;  
- registrar texto escrito em aplicações específicas.

### **2. Registro das informações**
Os dados capturados podem ser armazenados:
- em arquivos locais;
- em memória;
- enviados em tempo real para servidores remotos.

### **3. Mecanismos de persistência**
Assim como outros malwares, keyloggers costumam:
- adicionar entradas em pastas de inicialização;
- modificar o registro (no Windows);
- criar tarefas agendadas;
- injetar código em processos de longa duração.

### **4. Exfiltração**
As informações coletadas são transmitidas para o atacante usando:
- conexões HTTP/HTTPS;
- sockets remotos;
- DNS tunneling;
- e outros métodos disfarçados.

# 🔍 4. Como Esses Malwares Exploram Vulnerabilidades Técnicas

## 4.1. Exploração de falhas no software
- **Vulnerabilidades de dia zero (zero-day)** aplicadas antes de correções serem disponibilizadas.  
- **Brechas em serviços expostos**, como RDP, SSH, servidores web, bancos de dados.  
- **Bibliotecas desatualizadas** usadas por aplicações corporativas.  
- **Drivers vulneráveis** que permitem execução privilegiada.

## 4.2. Má configuração dos sistemas
Malwares frequentemente se aproveitam de:
- permissões excessivas para usuários comuns;
- falta de controle de acesso baseado em função (RBAC);
- ausência de firewalls ou regras inadequadas;
- falta de logs e auditoria.

## 4.3. Falhas de atualização
Sistemas sem patching representam risco crítico:
- sistemas operacionais antigos;  
- serviços sem atualização;  
- antivírus desativados ou vencidos.  

Ransomware e keyloggers prosperam em ambientes assim.

# 🧠 5. Como Esses Malwares Exploram Brechas Humanas

Grande parte das infecções é causada **não por falhas técnicas**, mas por comportamento humano previsível.

## 👉 5.1. Engenharia social
Atacantes usam técnicas de persuasão para induzir a vítima a executar arquivos maliciosos. Exemplos:
- e-mails que se passam por bancos, empresas ou superiores hierárquicos;
- mensagens urgentes (“seu acesso será bloqueado”, “pagamento pendente”);
- anexos com nomes convincentes (“boleto.pdf.exe”, “currículo.docm”).

## 👉 5.2. Curiosidade e confiança
Arquivos maliciosos costumam ser disfarçados como:
- fotos;
- documentos importantes;
- atualizações falsas.

## 👉 5.3. Falta de conscientização
Usuários não percebem riscos como:
- permissões suspeitas solicitadas por programas;
- downloads de fontes não confiáveis;
- links encurtados;
- macros habilitadas em documentos Office.

## 👉 5.4. Fraqueza em senhas
Atacantes exploram:
- senhas fracas;
- reutilização de senhas em vários serviços;
- ausência de MFA (autenticação multifator).

## 👉 5.5. Negligência com backups
Ransomware depende disso:  
**se a vítima não tiver backups**, o pagamento parece ser a única solução.

# 🛡️ 6. Como se Proteger (Boas Práticas Essenciais)

## 6.1. Medidas técnicas
- Manter software atualizado.  
- Usar antivírus e EDR modernos.  
- Isolar máquinas críticas por VLAN.  
- Monitorar logs de execução de processos.  
- Restringir macros e plugins desconhecidos.  
- Configurar backups automáticos offline.

## 6.2. Medidas humanas
- Treinar usuários para reconhecer phishing.  
- Simular campanhas internas de segurança.  
- Verificar a autenticidade de anexos.  
- Evitar uso de pendrives desconhecidos.  
- Ativar MFA em todos os serviços.


