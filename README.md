# 🚀 Pipeline de Automação de Dados de Vendas e Envio de E-mails

<img width="1128" height="785" alt="print" src="https://github.com/user-attachments/assets/0bcab8ec-e875-4deb-a0c4-ddb5c4456d6c" />


## 📌 O Desafio
O processamento manual de dados de vendas diárias e anuais para múltiplas filiais é altamente ineficiente. Além de consumir horas de trabalho repetitivo, introduz um risco crítico de fuga de informação — como o envio acidental de dados financeiros confidenciais de uma filial para o gerente de outra unidade.

## 💡 A Solução
Desenvolvimento de um pipeline robusto em Python que automatiza todo o fluxo de trabalho de relatórios de ponta a ponta. O script ingere uma base de dados bruta de vendas, cruza as informações para calcular Indicadores-Chave de Desempenho (Faturamento, Diversidade de Produtos e Ticket Médio) e gera relatórios personalizados em formato `.xlsx` para 25 lojas distintas.

O sistema faz o provisionamento automático de uma estrutura de diretórios para backup local e realiza o disparo de e-mails personalizados em HTML para cada gerente. Isto garante a privacidade estrita dos dados, assegurando que cada destinatário receba apenas as métricas relevantes para a sua respetiva unidade.

## 🛠️ Tecnologias & Bibliotecas
* **Python**
* **Pandas:** Para manipulação avançada, filtragem e agregação de dados.
* **Pathlib:** Para gestão de diretórios locais e roteamento dinâmico de ficheiros multiplataforma.
* **SMTPLib & email.mime:** Para conexão segura com o servidor de e-mail e disparo automatizado com anexos.

## 📈 Destaques Técnicos
* **Arquitetura SMTP Otimizada:** Para garantir alta performance e evitar o bloqueio por protocolos anti-spam (comum quando ocorrem múltiplas requisições rápidas de login), a conexão com o servidor SMTP é estabelecida exatamente uma vez *fora* do loop de repetição, permitindo o envio rápido de todos os e-mails numa única sessão.
* **Segregação Estrita de Dados:** O algoritmo isola os dados ao nível de processamento, eliminando qualquer risco de exposição cruzada de informações antes mesmo da geração física dos ficheiros.
* **Relatórios HTML Dinâmicos:** Os e-mails são estruturados com tabelas limpas em HTML e indicadores visuais de desempenho (✅/❌), baseados na lógica de atingimento de metas calculada em tempo de execução.
