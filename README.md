OBSERVAÇÃO!!!!!!!!!!!!!!!!

NA AZURE O PROJETO ESTÁ COM O NOME Sprint_03_MOTTHRU MAS SE TRATA DE TODA A ENTREGA, INCLUINDO A SPRINT 4. 

Mottu IoT — Plano de Testes (Azure Boards) + Automação (Postman)

Resumo: este repositório contém o plano de testes manuais (Azure Boards) e a automação de testes (Postman/Newman) do projeto Mottu IoT, desenvolvido como parte da Sprint 03 – Challenge FIAP 2025.

🔗 Links para correção

Azure Boards (Plano de Testes / Test Cases):
https://dev.azure.com/RM557706/Sprint_03_MOTTHRU

🌳 Estrutura do repositório

/manual
  └── mottu_azure_manual_tests.csv
/automation
  └── /postman
      └── mottu_iot_postman_collection.json
README.md

🧭 Como executar (Postman / Newman)

Variável obrigatória:
baseUrl = http://localhost:8080

Executar no Postman (Runner)
1. Importar automation/postman/mottu_iot_postman_collection.json
2. Definir a variável baseUrl em Collection Variables
3. Rodar a coleção completa

Executar via Newman (CLI)
newman run automation/postman/mottu_iot_postman_collection.json --env-var baseUrl=http://localhost:8080

🧪 Testes manuais (Azure Boards)

Arquivo para importação:
manual/mottu_azure_manual_tests.csv

Como importar no Azure DevOps:
Boards → Test Plans → Import Work Items → Upload CSV
Mapeamentos:
- Work Item Type → Test Case
- Title → Title
- Priority → Priority
- Iteration Path → Iteration Path
- Area Path → Area Path
- Tags → Tags
- Step Action → Steps
- Step Expected → Expected Result

Iterações sugeridas:
Mottu/Release-1/Sprint-1
Mottu/Release-1/Sprint-2

Dados controlados (usados nos testes):
idMoto=2001, placa="MTT1A23", modelo="CG 160"
idSensor="S-ESP32-001" (ESP32, LoRaWAN, ativo=true)
Eventos: 90001 (ENTRADA), 90002 (SAÍDA)
Timestamps ISO8601 (exemplo: 2025-11-05T10:00:00Z)

✅ Casos automatizados incluídos (Postman)
1. Cadastrar Sensor (201)
2. Registrar Moto (201)
3. Evento ENTRADA pátio (201)
4. Consultar Moto (status NO_PATIO) (200)
5. Evento SAÍDA pátio (201) + Consultar Moto (status FORA_PATIO) (200)
6. Erro Sensor duplicado (409/400)

📹 Vídeo de evidência (obrigatório)
O vídeo deve mostrar:
1) A coleção Postman importada e a variável baseUrl configurada;
2) A execução completa (Runner ou Newman);
3) O resultado dos testes (pass/fail);
4) (Opcional) Visualização de chamadas cURL no terminal.


🌿 Branch e envio no GitHub
git init
git checkout -b develop
git add .
git commit -m "Entrega: Testes manuais (Azure Boards) + automação (Postman) - Mottu IoT"
git push -u origin develop



