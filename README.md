# 🎯 ATS Resume Matchmaker & Optimizer

Aplicação web moderna desenvolvida 100% na plataforma **Lovable** (utilizando React, TypeScript, Tailwind CSS e Shadcn UI) com o objetivo de automatizar o processo de adequação de currículos para sistemas ATS (*Applicant Tracking Systems*), utilizando inteligência artificial para matchmaking e otimização baseada em vagas externas.

A aplicação está publicada e acessível em: https://pixel-perfect-playbook-970.lovable.app

---

## 🚀 1. O Problema que a Aplicação Resolve

No mercado de trabalho atual, a grande maioria das empresas utiliza softwares de triagem automática (**ATS**) antes que um recrutador humano veja um currículo. Candidatos frequentemente perdem oportunidades não por falta de qualificação, mas porque seus currículos não contêm as palavras-chave exatas, os termos técnicos ou o formato legível que os algoritmos esperam.

Esta aplicação resolve esse problema permitindo que o usuário:
1. Traga os detalhes de **qualquer vaga externa** (via URL ou inserção manual da descrição).
2. Realize uma **análise de compatibilidade imediata (Match %)** contra o seu perfil base.
3. Identifique **gaps** (palavras-chave e competências faltantes) para elevar o seu score.
4. Gere **automaticamente um currículo ATS-friendly** customizado para a vaga, maximizando as chances de aprovação na triagem inicial.

---

## 📝 2. O Mega Prompt Inicial e Evolução Iterativa

### O Mega Prompt Inicial (Versão 1)
O projeto nasceu a partir do seguinte prompt estruturado enviado à IA no Lovable:

> *"Você é um desenvolvedor frontend sênior especialista em React, Tailwind CSS, TypeScript e Shadcn UI. Sua tarefa é criar uma aplicação web completa, moderna e responsiva de matchmaking de vagas de emprego e otimizador de currículos ATS-friendly. O aplicativo deve permitir que o usuário cadastre o seu perfil profissional e currículo base, explore vagas de emprego com uma indicação visual de compatibilidade (match %), visualize análises detalhadas de gaps e gere versões personalizadas do currículo otimizadas para sistemas ATS. Utilize Shadcn UI e paleta de cores em Verde, Preto e Cinza (zinc-950, zinc-900, emerald-600)."*

### O que mudou do prompt inicial até a versão final?
Ao longo do desenvolvimento, o escopo do produto passou por simplificações estratégicas e melhorias de fluxo:
* **Remoção de Módulos Desnecessários:** Inicialmente, o app previa uma página pública de listagem de vagas e um painel de administração protegido por senha (`/admin`). O escopo foi refinado para remover completamente o gerenciamento interno de vagas e a tela de admin, focando exclusivamente no usuário final.
* **Centralização no Fluxo de Vagas Externas:** Em vez de depender de um banco de vagas interno pré-cadastrado, o sistema evoluiu para receber a vaga diretamente da necessidade do usuário (via URL ou colagem da descrição).
* **Fluxo Interativo de Match & Confirmação:** Adicionou-se uma etapa intermediária onde o sistema avalia o *match* atual, aponta melhorias no perfil e solicita a confirmação do usuário antes de disparar a geração final do currículo otimizado.

---

## ⚙️ 3. Como a Análise Funciona (Da Vaga ao Currículo Ajustado)

O fluxo de funcionamento do sistema na interface opera em etapas sequenciais:

1. **Entrada de Dados da Vaga:**
   * O usuário acessa a tela de **Currículo ATS**.
   * Escolhe entre colar o link da vaga externa (para extração automática de dados) ou preencher manualmente o Título, Empresa e Descrição completa.
2. **Processamento e Análise de Match:**
   * Ao clicar em **"Otimizar Currículo"**, o sistema roda um algoritmo de comparação entre as competências da vaga e o perfil base do candidato.
   * O resultado exibe um **Indicador Percentual de Match** (ex: 78%).
3. **Identificação de Gaps (Sugestões de Melhoria):**
   * O sistema lista explicitamente quais palavras-chave, hard skills ou tecnologias estão faltando no perfil e que, se incluídas, aumentariam a pontuação junto ao ATS.
4. **Confirmação e Geração do Currículo:**
   * O usuário visualiza a mensagem de confirmação para gerar o currículo otimizado com base em seu perfil atual e nas melhorias identificadas.
   * O sistema reescreve o resumo profissional e reestrutura as experiências sem elementos gráficos complexos (garantindo 100% de compatibilidade com leitores ATS).
5. **Exportação:**
   * O usuário pode **Copiar o Texto** formatado ou **Baixar o Currículo** pronto para envio.

---

## 🔄 4. Ajustes Solicitados Pós-Primeira Geração e Justificativas

Após a entrega do primeiro protótipo funcional, foram solicitados ajustes finos para adequação de usabilidade e segurança:

1. **Adição de Modo Admin e Senha:** 
   * *O que foi pedido:* Criar uma área administrativa protegida por senha inicial (`123456`) com opção de alteração exigindo a senha atual.
   * *Por quê:* Permitir simular o gerenciamento e cadastro de vagas centralizadas no sistema antes da mudança de escopo. *(Nota: Essa camada foi posteriormente removida em favor do foco total em vagas externas, conforme a evolução do produto).*
2. **Remoção das Telas de Admin e Listagem de Vagas:**
   * *O que foi pedido:* Excluir as telas de gestão de vagas e painel restrito.
   * *Por quê:* Evitar complexidade desnecessária e fricção no produto, transformando o app em uma ferramenta utilitária e direta de otimização de currículo sob demanda.
3. **Inclusão de Sugestões de Melhoria de Perfil:**
   * *O que foi pedido:* Exibir o que pode ser incluído no perfil para elevar o percentual de match antes da confirmação de geração.
   * *Por quê:* Dar transparência ao usuário sobre *por que* o match está em determinado patamar e dar orientações práticas de como melhorar a sua empregabilidade para aquela vaga específica.
