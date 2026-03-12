# 🛡️ LINUXBOT FORENSE v5.0

**Descrição:** Automação em Python desenvolvida para análise inteligente de logs do Nginx, rastreio de reputação de IPs e geração de comandos de bloqueio para o firewall `nftables`.

---

## 📂 1. Estrutura de Pastas e Arquivos
O projeto deve ser instalado no diretório base para garantir o funcionamento dos caminhos definidos no script:

* **Diretório Base:** `/root/linuxbot/`
* **`linuxbot.py`**: Motor de análise e lógica de score.
* **`linuxbot_intelligence.json`**: Base de dados JSON que armazena o histórico de reputação.
* **`cron_log.log`**: Registro de logs das execuções automáticas do Cron.

---

## 🛠️ 2. Comandos de Instalação (Servidor Linux)

Execute os comandos abaixo para preparar o ambiente:

```bash
# 1. Criar pasta e acessar
mkdir -p /root/linuxbot && cd /root/linuxbot

# 2. Criar o script principal
nano linuxbot.py
# [Cole o código do script dentro deste arquivo]

# 3. Preparar a estrutura do Firewall (nftables)
# Necessário apenas se você ainda não tiver essas tabelas configuradas
nft add table inet filter
nft add chain inet filter input { type filter hook input priority 0 \; }

🤖 3. Automação (Agendamento no Cron)
O script foi desenhado para rodar silenciosamente em segundo plano. Para processar os logs a cada 5 minutos, adicione a seguinte linha ao seu crontab -e:

*/5 * * * * /usr/bin/python3 /root/linuxbot/linuxbot.py >> /root/linuxbot/cron_log.log 2>&1

📊 4. Como ler o Relatório
Para visualizar o dossiê de inteligência e ver quais IPs foram marcados como perigosos, execute manualmente:

python3 /root/linuxbot/linuxbot.py
