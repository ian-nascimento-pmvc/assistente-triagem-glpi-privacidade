# Política de Privacidade — Assistente de Triagem GLPI

Última atualização: 17 de novembro de 2026.

## 1. Responsável e finalidade

O Assistente de Triagem GLPI é uma extensão de uso institucional da Prefeitura Municipal de Vitória da Conquista (PMVC). Sua finalidade única é auxiliar operadores autorizados a transformar conversas de atendimento do CETIZAP em chamados do GLPI, sugerindo título, descrição, tipo, categoria e campos complementares para revisão humana.

A extensão não abre o chamado sem a ação do operador. O resultado da classificação deve ser revisado antes do salvamento no GLPI.

## 2. Dados tratados

Para prestar essa funcionalidade, a extensão pode tratar:

- conteúdo das conversas recentes do CETIZAP, incluindo mensagens, autores, datas, identificadores técnicos e referências de mídia;
- texto extraído localmente de PDF selecionado pelo operador, nome do arquivo e metadados necessários para associá-lo à conversa;
- identificadores da conversa e do chamado;
- título, descrição, tipo, categoria e módulo sugeridos e os valores finais revisados pelo operador;
- datas e duração do atendimento até a abertura do chamado;
- versão da extensão e do classificador, resultado da revisão e quantidade de campos alterados;
- endereço das páginas institucionais necessárias ao funcionamento;
- autorização temporária do CETIZAP, mantida somente em memória para consultar a conversa na API oficial.

O PDF original não é enviado pelo Assistente de Triagem. Notas internas do CETIZAP não são incluídas no conteúdo enviado para classificação. O token de autorização do CETIZAP não é persistido no armazenamento local, não é gravado no GLPI e não é enviado aos webhooks de classificação ou feedback.

## 3. Armazenamento local

No navegador, a extensão mantém no máximo cinco conversas recentes, limitadas a 200 mensagens por conversa. Esses registros são substituídos conforme novas conversas são atendidas e também podem ser apagados pelo operador no próprio assistente.

São mantidos ainda:

- cursores de conversa por até 14 dias, para separar demandas já concluídas;
- recibos técnicos de feedback por até 30 dias, para evitar envios duplicados;
- configuração de categorias e informação de versão em cache por períodos curtos;
- diagnóstico da tentativa atual no armazenamento da sessão do navegador.

## 4. Transmissão e destinatários

Os dados são transmitidos somente por HTTPS e apenas quando necessários à finalidade descrita:

- **CETIZAP e API do CETIZAP, mantidos pela PMVC:** obtenção da conversa atendida e de anexos selecionados;
- **n8n institucional da PMVC:** orquestração da classificação, configuração de categorias, controle de versão e registro do feedback operacional;
- **OpenAI, configurada como provedora do modelo no fluxo institucional:** processamento do recorte de conversa enviado para produzir a sugestão de classificação;
- **GLPI institucional da PMVC:** criação do chamado e armazenamento dos campos revisados, métricas e registros administrativos associados.

Os dados não são vendidos, não são utilizados para publicidade e não são compartilhados para avaliação de crédito ou finalidade incompatível com a triagem de chamados.

## 5. Retenção nos sistemas institucionais

Chamados, métricas e feedbacks enviados aos sistemas institucionais podem ser mantidos pelo período aplicável aos registros administrativos e às rotinas de auditoria da PMVC. Logs operacionais do n8n e registros do GLPI seguem as configurações e políticas de retenção definidas pelos administradores desses serviços.

Solicitações de acesso, correção ou eliminação serão avaliadas considerando as obrigações de preservação de registros administrativos e de segurança da informação.

## 6. Segurança

A extensão limita sua execução aos endereços institucionais `cetizap.pmvc.ba.gov.br`, `cetizap-api.pmvc.ba.gov.br`, `glpi.pmvc.ba.gov.br` e `new8n.pmvc.ba.gov.br`. As comunicações utilizam HTTPS. O código executável necessário é distribuído no próprio pacote da extensão; configurações obtidas do servidor não contêm código executável.

## 7. Uso limitado

O uso das informações é limitado à prestação, manutenção, segurança e avaliação da funcionalidade de triagem descrita nesta política. O uso de informações recebidas de APIs do Google observará a Política de Dados do Usuário da Chrome Web Store, inclusive os requisitos de Uso Limitado.

## 8. Contato

Dúvidas ou solicitações relacionadas a esta política podem ser encaminhadas ao responsável institucional pela publicação da extensão:

`publisherchromewebstore@pmvc.ba.gov.br`

