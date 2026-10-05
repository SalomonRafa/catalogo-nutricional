# Revisão da página de serviços

Versão para revisão em 05/10/2026. Não publicar nem mesclar antes de resolver o total de consultas do formato de 180 dias.

## O que mudou

- Headline preservada, com tamanho e espaçamento menores; texto de abertura substituído conforme solicitado.
- CTA padronizado como “Conversar sobre meu acompanhamento”, com explicação do primeiro contato e modalidades próximas ao botão.
- Apresentação profissional única após a abertura e antes de “Para quem”, usando exatamente a imagem incorporada que já existia no HTML. Foto de 180 × 220 px no desktop e 120 × 160 px no celular.
- Credenciais e abrangência do atendimento reunidas no bloco de apresentação. Detalhes relevantes da atuação preservados em “Conheça minha forma de trabalhar”, no mesmo bloco expansível.
- Seções repetitivas consolidadas em consulta inicial → aplicação na rotina → retorno → ajustes. Exemplos de fome, viagens, refeições fora e mudanças no treino mantidos.
- Cards padronizados com duração, consultas, modalidade, agendamento, recursos e suporte.
- 30 dias: 2 consultas incluídas, sendo 1 inicial + 1 retorno ao final dos 30 dias, com explicação da reavaliação.
- 90 dias: 4 consultas incluídas, sendo 1 inicial + 3 retornos. Videochamadas quinzenais removidas como benefício separado, conforme confirmação do responsável.
- 180 dias: redação provisória “1 consulta inicial + retornos distribuídos ao longo dos 180 dias”. Recursos descritos individualmente, sem remeter genericamente ao formato de 90 dias.
- FAQ consistente com os cards, incluindo agendamento, reserva confirmada de 30 dias, modalidades das consultas e direito aos retornos independentemente de aplicação perfeita do plano.
- Honorários, parcelas e valor da reserva removidos de index.html. Condições apresentadas pelo WhatsApp. Arquivos históricos e sistemas comerciais não foram alterados.
- 4 UTMs identificadas individualmente na mensagem preparada do WhatsApp. Navegação por âncoras conserva a query da URL; sem UTMs válidas, a mensagem mantém “Origem: direto”. Somente essas 4 chaves são lidas, sem instalar rastreamento nem transmitir dados a plataformas de anúncios.
- Menu móvel acessível, FAQ com estados e controles associados; botão flutuante ocultado quando poderia cobrir texto, imagem ou controles.

## Verificações

Teste real em Chromium headless, em 360, 390, 430 e 1440 px, com 900 px de altura. Não equivale a teste em aparelhos físicos ou Safari no iOS.

- Sem rolagem horizontal; verificação também dos limites dos elementos, mesmo com overflow-x oculto.
- Foto original carregada e presente apenas 1 vez.
- Botões principais com pelo menos 44 px de altura.
- Menu abre, navega e fecha; tecla Escape fecha e devolve foco.
- Todas as perguntas frequentes abrem e fecham, atualizando aria-expanded.
- Bloco de detalhes profissionais abre e fecha.
- Botão flutuante conferido em amostras de rolagem a cada 250 px, sem sobreposição de conteúdo ou controles.
- 9 links do WhatsApp conferidos: número 5561995662828, mensagens corretas, formato escolhido nos 3 cards, 4 UTMs e fallback direto. Valores com espaços, “&” e “+” preservados. Parâmetro estranho à atribuição ignorado.
- Nenhuma mensagem enviada e nenhum pagamento realizado.
- Sem erros de JavaScript. Nenhuma requisição de rastreamento: somente página e fontes já existentes.
- Sintaxe JavaScript e git diff --check aprovados.

| Largura | Headline | Posição vertical do CTA principal | Resultado |
| --- | --- | --- | --- |
| 360 px | 32px | 588 px | Aprovado |
| 390 px | 32px | 527 px | Aprovado |
| 430 px | 35.26px | 516 px | Aprovado |
| 1440 px | 57.6px | 528 px | Aprovado |

## Confirmações necessárias antes da publicação final

1. **180 dias: são 6 consultas no total (1 inicial + 5 retornos) ou 7 (1 inicial + 6 retornos)?** A página não exibe essa dúvida e não presume o total. Essa informação precisa ser resolvida antes de mesclar/publicar.
2. Qual é o bairro e o local atual do atendimento presencial? Não há informação atual confirmada no projeto.
3. Quais são as regras atuais de cancelamento e reagendamento?
4. Quais são os horários, limites e prazo de resposta do suporte? A página conserva a referência aos limites do contrato, sem inventar horários nem prazo.
5. Como funcionam pagamento e reserva nos formatos de 90 e 180 dias? A regra de reserva Pix abatida foi preservada apenas para 30 dias, onde estava explícita.
6. O formato de 30 dias prevê atualizações do plano além da revisão no retorno? Não foi adicionada uma frequência não confirmada.

## Preview

Abra ../index.html em um navegador para revisar a versão interativa. A foto está incorporada no arquivo; as fontes usam os endereços externos originais.

- [Abertura no celular](abertura-390.jpg)
- [Apresentação no celular](apresentacao-390.jpg)
- [Apresentação no desktop](apresentacao-1440.jpg)
- [Resultados dos testes](verificacoes.json)

![Apresentação no celular](apresentacao-390.jpg)
