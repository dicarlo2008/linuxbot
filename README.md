<div align="center">
  <kbd>
    <h1 style="color: #00ff41;">🛡️ LINUXBOT FORENSE | SECURITY ENGINE</h1>
  </kbd>
  <p><strong>Inteligência Forense e Automação de Defesa de Borda</strong></p>
</div>

<hr style="border: 0.5px solid #00ff41;">

## 📖 Descrição Estratégica
O **LinuxBot Forense** é uma solução de engenharia de segurança desenvolvida para realizar a análise profunda de logs de servidores Web (Nginx/HAProxy). O motor utiliza lógica de score para rastreio de reputação de IPs, identificando padrões de ataque antes que eles comprometam a aplicação.

## 🧠 Lógica de Inteligência
Diferente de firewalls estáticos, este motor opera com **análise comportamental**:

* **Scoring de Reputação:** Cada IP é avaliado com base em frequência, tipos de erros gerados e acesso a diretórios sensíveis.
* **Persistência JSON:** Armazenamento de histórico em banco de dados leve (`JSON`) para rastreio de reincidência.
* **Ação em Nível de Kernel:** Integração com o framework `nftables` para bloqueios de altíssima performance, minimizando o impacto na CPU.

## 📂 Arquitetura do Sistema
O ecossistema é organizado de forma modular para garantir baixa latência no processamento:

* **Motor de Análise:** Responsável pelo parsing de logs e cálculo de risco.
* **Base de Inteligência:** Histórico de reputação e lista negra dinâmica.
* **Log de Auditoria:** Registro detalhado de cada tomada de decisão para análise forense posterior.

## ⚙️ Operação e Automação
O sistema foi projetado para operar em modo **Zero-Touch**, com agendamentos automatizados (Cron) que garantem a inspeção contínua dos perímetros de rede. 

> **Nota de Segurança:** Por questões de integridade e proteção de propriedade intelectual, os scripts de execução (`.py`) e comandos específicos de infraestrutura são mantidos em ambiente privado de produção. Este repositório foca na documentação da arquitetura e das capacidades da ferramenta.

<hr style="border: 0.5px solid #00ff41;">

<div align="right">
  <sub>Bare Metal Security Solutions | DicCarlo SOC</sub>
</div>
