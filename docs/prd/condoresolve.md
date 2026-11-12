# PRD — CondoResolve

> Tipo: PRD inicial · Data: 2026-11-11
> **Status:** Aguardando implementação
>
> <!-- Valores possíveis: "Aguardando implementação" | "Implementada". Atualize para "Implementada" quando todas as specs estiverem concluídas. -->

## 1. Visão geral

O CondoResolve é um sistema web de um único condomínio para registrar e acompanhar ocorrências.

Há duas portas de entrada:

- **Portal do morador.** O morador informa o e-mail cadastrado e entra, sem senha. Ele vê todas as ocorrências do condomínio, abre uma nova e comenta nas que ainda estão em andamento.
- **Dashboard da equipe.** Só funcionários entram, com e-mail e senha. A equipe cadastra moradores e outros funcionários, acompanha as ocorrências, comenta e muda o status até encerrar.

Uma ocorrência nasce **Aberta**, com título, descrição, categoria, local e, se a pessoa quiser, uma foto. Depois de criada, o texto, o local e a foto permanecem como foram enviados. O que muda é o status, e só a equipe muda. Quando o status chega em **Resolvido** ou **Cancelado**, a ocorrência encerra: ninguém comenta mais e ninguém reabre.

A aparência segue a identidade visual já definida para o CondoResolve, inclusive a identificação visual dos cinco status.

## 2. Problema que resolve

Hoje o pedido do morador se perde em mensagem, papel ou conversa na portaria. A equipe não tem uma lista única do que está aberto, em análise ou já resolvido, e o morador não vê o que aconteceu com o próprio relato nem com os problemas das áreas comuns.

O sistema substitui esse controle solto por um registro único: o morador abre a ocorrência, a equipe atualiza o andamento, e qualquer morador acompanha a lista e a conversa daquela ocorrência.

## 3. Público-alvo

- **Morador** já cadastrado pela equipe. Usa o portal para abrir ocorrência, acompanhar a lista do condomínio e comentar.
- **Funcionário** da administração ou da operação do condomínio. Usa o dashboard para cuidar de pessoas e do andamento das ocorrências.

Quem não foi cadastrado não entra. O morador não usa o dashboard. O funcionário não abre ocorrência e não entra no portal pelo e-mail de funcionário.

## 4. Objetivo do recorte atual

Entregar o primeiro uso real do CondoResolve, para um único condomínio:

1. A equipe entra com senha e cadastra moradores e funcionários.
2. O morador entra com o e-mail e abre ocorrências com categoria, local e foto opcional.
3. Morador e equipe listam e filtram por status e categoria.
4. Os dois acessam o detalhe e comentam enquanto a ocorrência não estiver encerrada.
5. A equipe muda o status e pode encerrar em Resolvido ou Cancelado, sem reabertura.

## 5. Funcionalidades

**Essenciais:**

- Página inicial com as duas portas: morador e equipe.
- Login da equipe com e-mail e senha, sessão e sair.
- Um funcionário inicial já existente, para o primeiro acesso.
- Troca da própria senha pelo funcionário que está logado.
- Cadastro, edição, desativação e reativação de moradores.
- Cadastro, desativação e reativação de outros funcionários.
- Entrada do morador só com o e-mail, sessão e sair.
- Abertura de ocorrência pelo morador: título, descrição, categoria, local e uma foto opcional.
- Lista de todas as ocorrências, no portal e no dashboard, com filtro por status e por categoria.
- Detalhe da ocorrência, com a foto quando existir.
- Comentário de qualquer morador identificado e de qualquer funcionário logado, enquanto a ocorrência não estiver encerrada.
- Mudança de status pela equipe, com encerramento irreversível em Resolvido ou Cancelado.
- Histórico visível das mudanças de status.

**Desejáveis:**

- Nenhum item desejável neste recorte. O que ficou de fora está na seção 6.

## 6. Fora do escopo

- Mais de um condomínio, ou troca de condomínio.
- Senha, link por e-mail ou confirmação de identidade do morador.
- Aviso por e-mail, push ou qualquer notificação quando o status muda ou quando alguém comenta. A pessoa só fica sabendo ao entrar de novo.
- Recuperação de senha por e-mail. Quem esquece a senha e não tem outro funcionário ativo com acesso fica sem entrar, até a implantação resolver fora deste recorte.
- Alterar nome ou e-mail de um funcionário já criado. A senha de outro funcionário também não é alterada por terceiros.
- Excluir morador, funcionário, ocorrência ou comentário.
- Editar ou apagar ocorrência depois de criada.
- Editar ou apagar comentário.
- Reabrir ocorrência Resolvida ou Cancelada.
- Funcionário abrir ocorrência, em nome próprio ou de um morador.
- Morador mudar status.
- Tela para criar, editar ou apagar categorias.
- Mais de uma foto, foto no comentário, ou outros anexos.
- Busca por texto, relatórios, indicadores e exportação.
- Reservas de área comum, visitantes, encomendas, assembleias e boletos.
- Aplicativo móvel nativo. O site precisa ser utilizável no celular, sem virar um app de loja.
- A mesma pessoa ser, ao mesmo tempo, morador e funcionário.

## 7. Regras de negócio

- Regra 1: Existe um único condomínio. Toda ocorrência e toda pessoa pertencem a ele.
- Regra 2: O morador é cadastrado pela equipe, com nome completo, e-mail, torre/apartamento e telefone. Morador não tem senha.
- Regra 3: O morador entra digitando o e-mail cadastrado. Quem souber esse e-mail entra como essa pessoa. Esta é uma decisão aceita do recorte.
- Regra 4: Morador desativado não entra. As ocorrências e os comentários que ele já fez continuam visíveis, com o nome dele.
- Regra 5: O funcionário entra com e-mail e senha. Funcionário desativado não entra.
- Regra 6: Sempre existe pelo menos um funcionário ativo. O sistema recusa desativar o último.
- Regra 7: O sistema já nasce com um funcionário ativo, com nome, e-mail e senha conhecidos por quem faz a implantação.
- Regra 8: Um e-mail identifica uma pessoa só. Não pode repetir entre moradores, nem entre funcionários, nem cruzar os dois grupos. Maiúsculas e minúsculas não fazem diferença.
- Regra 9: O morador vê todas as ocorrências do condomínio, de qualquer autor e qualquer status.
- Regra 10: No portal, o autor aparece com nome e torre/apartamento. Telefone e e-mail do morador aparecem só para a equipe, na gestão de moradores e no detalhe visto pela equipe.
- Regra 11: Categorias fixas, nesta ordem de exibição: Manutenção, Limpeza, Barulho, Segurança, Áreas comuns, Outros.
- Regra 12: Status possíveis: Aberto, Em Análise, Em Execução, Resolvido, Cancelado. Toda ocorrência nasce Aberta.
- Regra 13: Só o funcionário muda o status. Entre Aberto, Em Análise e Em Execução a mudança é livre, e ele pode ir direto para Resolvido ou Cancelado. A troca não exige comentário.
- Regra 14: Resolvido e Cancelado encerram. Não há caminho de volta. Comentário novo é recusado. O controle de status deixa de ser oferecido.
- Regra 15: Qualquer morador identificado e qualquer funcionário logado podem comentar, desde que a ocorrência não esteja encerrada.
- Regra 16: Ocorrência e comentário publicados não são editados nem apagados.
- Regra 17: A foto é opcional e única. Quem vê o detalhe vê a foto. Se o envio da foto falha, a ocorrência não é criada.
- Regra 18: A lista usa a data de abertura, da mais recente para a mais antiga. Filtro de status e filtro de categoria valem juntos: a ocorrência precisa atender os dois.
- Regra 19: Morador não acessa o dashboard. Funcionário não entra no portal com o e-mail de funcionário e não abre ocorrência.
- Regra 20: Desativar não apaga a pessoa. A equipe pode reativar. Reativar devolve o acesso na hora.
- Regra 21: O funcionário logado pode trocar a própria senha. Precisa informar a senha atual. Não existe "esqueci minha senha" neste recorte.

## 8. Fluxos principais

### Fluxo 1 — Equipe entra e cadastra um morador

1. A pessoa abre o site e escolhe a porta da equipe.
2. Informa e-mail e senha do funcionário ativo.
3. Cai no dashboard, identificada, com saída visível.
4. Abre Moradores e cadastra nome completo, e-mail, torre/apartamento e telefone.
5. O morador passa a poder entrar pelo portal com esse e-mail.

### Fluxo 2 — Morador entra e abre uma ocorrência

1. O morador abre o site e escolhe a porta do morador.
2. Informa o e-mail cadastrado.
3. Vê a lista de todas as ocorrências, da mais recente para a mais antiga.
4. Escolhe abrir uma nova.
5. Preenche título, descrição, categoria e local. A foto fica em branco ou anexa uma imagem.
6. Confirma. A ocorrência nasce Aberta e o sistema abre o detalhe dela.

### Fluxo 3 — Acompanhar, comentar e encerrar

1. Morador ou funcionário abre uma ocorrência da lista.
2. Lê título, descrição, categoria, local, status, autor, data e a foto, se houver.
3. Se a ocorrência não estiver encerrada, escreve um comentário. O comentário aparece no fim da conversa.
4. No dashboard, o funcionário troca o status entre Aberto, Em Análise e Em Execução quando quiser.
5. Para Resolvido ou Cancelado, o funcionário confirma. A ocorrência encerra, o histórico registra a troca e o campo de comentário some.

## 9. Critérios de aceite

- O funcionário inicial consegue entrar no dashboard com e-mail e senha, e sair.
- O funcionário consegue cadastrar, editar, desativar e reativar um morador.
- O morador ativo entra só com o e-mail e vê o próprio nome e a torre/apartamento.
- Morador desativado, e-mail desconhecido e e-mail de funcionário não entram no portal.
- O morador consegue abrir uma ocorrência sem foto e outra com uma foto.
- Morador e funcionário conseguem ver todas as ocorrências e reduzir a lista por status, por categoria e pelos dois juntos.
- No detalhe, o morador vê nome e unidade do autor, e não vê telefone nem e-mail.
- No detalhe, o funcionário vê também telefone e e-mail do autor.
- Qualquer morador identificado comenta numa ocorrência Aberta, Em Análise ou Em Execução, mesmo que não seja o autor.
- O funcionário muda o status sem seguir uma ordem obrigatória e consegue encerrar direto.
- Com status Resolvido ou Cancelado, o sistema não oferece comentário nem troca de status.
- O sistema recusa desativar o único funcionário ativo.
- O sistema não oferece apagar ou editar ocorrência e comentário.

## 10. Stack

- Next.js, TypeScript e Tailwind, já presentes no projeto.
- Supabase para os dados, para o login com senha da equipe e para guardar a foto.
- Interface no padrão visual já definido para o CondoResolve.
- Formulários com validação no envio, no padrão de formulário já adotado pelo projeto.

Nada além disso entra neste recorte. Não há serviço de e-mail, fila, aplicativo nativo nem painel de indicadores.

## 11. Justificativa da stack

O projeto já é uma aplicação web em Next.js, TypeScript e Tailwind. O produto precisa de três coisas que o Supabase entrega juntas: guardar moradores, funcionários, ocorrências e comentários; autenticar o funcionário com senha; e armazenar a foto opcional. O morador não usa senha, então a entrada dele é apenas a conferência do e-mail cadastrado.

É uma stack proporcional a um condomínio só, com duas portas de acesso e um fluxo de ocorrência. Serviço de e-mail e aplicação separada ficariam grandes demais para este recorte, e o aviso por e-mail está fora de propósito de agora.

## 12. Fases de construção

### Fase 1 — Acesso da equipe

Objetivo: a equipe consegue entrar numa área que só funcionário alcança, e o primeiro acesso já tem dono.

Specs:

- Spec 01 — Página inicial e entrada da equipe

### Fase 2 — Pessoas

Objetivo: a equipe monta o cadastro de quem pode usar o sistema.

Specs:

- Spec 03 — Gestão de moradores
- Spec 04 — Gestão de funcionários

### Fase 3 — Portal do morador

Objetivo: o morador cadastrado entra com o e-mail e chega na área dele.

Specs:

- Spec 02 — Entrada do morador

### Fase 4 — Ocorrências

Objetivo: o morador registra o problema e os dois públicos acompanham, comentam e, no caso da equipe, encerram.

Specs:

- Spec 05 — Abertura de ocorrência
- Spec 07 — Detalhe da ocorrência
- Spec 06 — Lista e filtros de ocorrências
- Spec 08 — Comentários
- Spec 09 — Mudança de status

## 13. Specs funcionais detalhadas

> Cada spec deve ser autossuficiente: um agente de codificação vai ler SÓ esta spec (mais as dependências) para montar o plano técnico e implementar. Preencha todos os campos; se um não se aplica, escreva "Não se aplica" e o porquê.

### Spec 01 — Página inicial e entrada da equipe

- **Fase:** Fase 1 — Acesso da equipe
- **Objetivo (o quê):** O site abre com duas portas, e um funcionário ativo entra no dashboard com e-mail e senha, permanece identificado e consegue sair.
- **Intenção (por quê):** Sem essa porta, não existe quem cadastre moradores nem quem opere as ocorrências. O funcionário inicial existe para o primeiro acesso não depender de uma tela de cadastro público.
- **Contexto:** Não há produto anterior. Esta spec cria a página inicial e a área autenticada da equipe. A identidade visual do CondoResolve já está definida e deve ser respeitada. As áreas Moradores, Equipe e Ocorrências ganham conteúdo nas specs 03, 04 e 06.
- **Atores:** Funcionário ativo. Visitante ainda não identificado, que só escolhe a porta.
- **Descrição do comportamento:** Ao abrir o site, a pessoa vê duas escolhas claras: entrar como morador ou entrar como equipe. A porta do morador, até a Spec 02, leva a uma espera explícita de que a entrada do morador ainda será habilitada, sem pedir senha e sem fingir que um e-mail qualquer entra. A porta da equipe pede e-mail e senha. Se os dados forem de um funcionário ativo, o sistema abre o dashboard e mantém a pessoa identificada até ela sair. O dashboard mostra o nome de quem entrou, a ação Sair, e três destinos: Ocorrências, Moradores e Equipe. Cada destino, nesta spec, mostra só o nome da área, sem cadastro e sem lista. Se a pessoa já está logada e escolhe de novo a porta da equipe, vai direto ao dashboard. Sair encerra a identificação e devolve à página inicial. A área da equipe recusa quem não está identificado e mostra o formulário de e-mail e senha.
- **Entradas e saídas:** Entram o e-mail e a senha digitados. Sai a sessão do funcionário ativo, o nome dele visível no dashboard, ou uma mensagem de erro. Sair produz o fim da sessão.
- **Dados/entidades envolvidos (conceitual):** Funcionário: nome completo, e-mail, senha, situação (ativo ou desativado). Neste momento existe só o funcionário inicial, ativo, com nome, e-mail e senha definidos na implantação. A senha não é exibida em lugar nenhum depois de definida.
- **Estados e transições:** Visitante sem sessão → funcionário identificado, quando e-mail e senha batem com um funcionário ativo. Funcionário identificado → visitante, quando escolhe Sair. Conta desativada não chega a identificada.
- **Regras de negócio:** Só funcionário ativo entra. A comparação do e-mail ignora maiúsculas e minúsculas. A mensagem de senha errada não conta se o e-mail existe. A mensagem de conta desativada é específica, porque a pessoa da equipe precisa saber que deve falar com outro funcionário. O dashboard não se abre para morador nem para visitante. O funcionário inicial já nasce ativo.
- **Validações:** E-mail e senha são obrigatórios. E-mail em formato de e-mail. Sem isso, o envio não acontece e o campo faltante é indicado.
- **Fluxo do usuário (passo a passo):**
  1. A pessoa abre o site.
  2. Escolhe a porta da equipe.
  3. Informa e-mail e senha.
  4. Se estiver correta e a conta ativa, vê o dashboard com o próprio nome, Sair, e os destinos Ocorrências, Moradores e Equipe.
  5. Ao escolher Sair, volta à página inicial e a porta da equipe pede senha de novo.
- **Casos de borda e erros:**
  - E-mail ou senha não batem com um funcionário: "E-mail ou senha incorretos." Os campos permanecem editáveis, a senha é limpa.
  - Funcionário desativado: "Esta conta de funcionário está desativada." Não abre o dashboard.
  - Campos vazios: o envio é barrado e o campo obrigatório é indicado.
  - Pessoa sem sessão abre direto um destino da equipe: vê o pedido de e-mail e senha, não o conteúdo.
  - Sessão já ativa abre a porta da equipe: entra no dashboard sem digitar de novo.
  - A porta do morador, nesta spec, não autentica ninguém.
- **Impacto no existente:** Nenhum produto anterior. Cria a página inicial e a casca autenticada do dashboard.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado o funcionário inicial ativo, quando informa e-mail e senha corretos, então entra no dashboard e vê o próprio nome e a ação Sair.
  - Dado um visitante sem sessão, quando tenta abrir um destino da equipe, então vê o pedido de e-mail e senha.
  - Dado e-mail ou senha incorretos, quando envia o formulário, então vê "E-mail ou senha incorretos." e não entra.
  - Dado um funcionário desativado, quando informa a senha correta, então vê "Esta conta de funcionário está desativada." e não entra.
  - Dado um funcionário identificado, quando escolhe Sair, então a próxima tentativa de abrir o dashboard pede e-mail e senha.
  - Dado a página inicial, quando a pessoa olha as portas, então encontra uma porta de morador e uma porta de equipe.
- **Definição de pronto:** Um funcionário ativo entra, permanece identificado ao navegar entre os três destinos vazios, e sai. Credencial errada e conta desativada não entram. Visitante não vê conteúdo da equipe.
- **Dependências:** Nenhuma. O funcionário inicial precisa existir para o primeiro acesso ser testável.
- **Fora do escopo desta spec:** Cadastrar morador ou funcionário, trocar senha, entrada do morador por e-mail, ocorrências, comentários e status.

### Spec 02 — Entrada do morador

- **Fase:** Fase 3 — Portal do morador
- **Objetivo (o quê):** Um morador ativo informa o e-mail cadastrado e entra no portal, sem senha, vendo quem ele é até sair.
- **Intenção (por quê):** O morador precisa chegar na lista e na abertura de ocorrência sem receber senha e sem passar pelo dashboard. O e-mail é a chave combinada com a equipe na Spec 03.
- **Contexto:** A página inicial e a porta do morador existem desde a Spec 01. O cadastro do morador existe desde a Spec 03. Esta spec substitui a espera da porta do morador pelo formulário de e-mail e pela área identificada. A lista e a nova ocorrência entram nas specs 05 e 06.
- **Atores:** Morador ativo. Morador desativado e visitante com e-mail desconhecido, que não entram.
- **Descrição do comportamento:** Na porta do morador, o sistema pede só o e-mail. Se esse e-mail for de um morador ativo, abre o portal e mostra o nome completo e a torre/apartamento de quem entrou, com a ação Sair sempre visível. A sessão aponta para o cadastro daquela pessoa, não para o texto digitado: se a equipe mudar o e-mail depois, a sessão aberta continua sendo a mesma pessoa, e a próxima entrada usa o e-mail novo. Sair encerra a identificação e volta à página inicial. Quem já está identificado e escolhe de novo a porta do morador cai direto no portal. A área do morador recusa quem não está identificado e mostra o pedido de e-mail. Esta sessão é independente da sessão da equipe: entrar como morador não abre o dashboard, e estar logado como funcionário não identifica ninguém no portal.
- **Entradas e saídas:** Entra o e-mail digitado. Sai a identificação do morador ativo, com nome e torre/apartamento visíveis, ou uma mensagem de erro. Sair remove a identificação.
- **Dados/entidades envolvidos (conceitual):** Morador: nome completo, e-mail, torre/apartamento, telefone, situação (ativo ou desativado). O telefone não aparece nesta tela.
- **Estados e transições:** Visitante → morador identificado, quando o e-mail é de um morador ativo. Morador identificado → visitante, ao sair. Se o morador for desativado no meio da sessão, a próxima ação no portal encerra a identificação e mostra a mensagem de conta desativada.
- **Regras de negócio:** Não há senha. Quem souber o e-mail de um morador ativo entra como ele. E-mail de funcionário não entra no portal, mesmo que a senha seja conhecida. E-mail desconhecido e morador desativado não entram, com mensagens diferentes. A comparação ignora maiúsculas, minúsculas e espaços nas pontas.
- **Validações:** E-mail obrigatório e em formato de e-mail. Sem isso, o envio não acontece e o campo é indicado.
- **Fluxo do usuário (passo a passo):**
  1. A pessoa escolhe a porta do morador na página inicial.
  2. Informa o e-mail.
  3. Se for um morador ativo, vê o portal com o próprio nome, a torre/apartamento e Sair.
  4. Ao sair, volta à página inicial. Entrar de novo exige o e-mail outra vez.
- **Casos de borda e erros:**
  - E-mail sem morador correspondente, inclusive e-mail só de funcionário: "Não encontramos um morador ativo com este e-mail."
  - Morador desativado: "Este morador está desativado. Fale com a administração."
  - E-mail vazio ou inválido: envio barrado, campo indicado.
  - Sessão de morador aberta enquanto a equipe desativa esse morador: a próxima abertura do portal encerra a sessão e mostra a mensagem de desativado.
  - Funcionário logado no dashboard escolhe a porta do morador: ainda precisa informar um e-mail de morador. A sessão da equipe continua só no dashboard.
- **Impacto no existente:** A porta do morador criada na Spec 01 passa a identificar o morador. O dashboard da equipe permanece como está.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado um morador ativo, quando informa o e-mail cadastrado, então entra no portal e vê nome completo e torre/apartamento.
  - Dado o mesmo morador, quando o e-mail é digitado com maiúsculas diferentes, então entra do mesmo jeito.
  - Dado um e-mail desconhecido, quando envia, então vê "Não encontramos um morador ativo com este e-mail." e não entra.
  - Dado um morador desativado, quando informa o e-mail, então vê "Este morador está desativado. Fale com a administração." e não entra.
  - Dado um morador identificado, quando escolhe Sair e tenta abrir o portal de novo, então o sistema pede o e-mail outra vez.
  - Dado um morador identificado, quando tenta abrir o dashboard, então vê o pedido de e-mail e senha da equipe, sem entrar.
- **Definição de pronto:** Morador ativo entra só com e-mail, vê quem é, sai, e não alcança o dashboard. Desativado, desconhecido e e-mail de funcionário recebem as mensagens desta spec e ficam de fora.
- **Dependências:** Spec 01, para a página inicial e a separação das portas. Spec 03, para existir morador ativo e desativado testável.
- **Fora do escopo desta spec:** Listar ocorrências, abrir ocorrência, comentar, cadastrar morador e qualquer login com senha.

### Spec 03 — Gestão de moradores

- **Fase:** Fase 2 — Pessoas
- **Objetivo (o quê):** O funcionário cadastra, edita, desativa e reativa moradores, e consulta a lista deles.
- **Intenção (por quê):** O portal não tem autocadastro. Sem este cadastro, ninguém entra como morador e ninguém abre ocorrência. Desativar tira o acesso de quem saiu do condomínio sem apagar o histórico.
- **Contexto:** O dashboard autenticado existe desde a Spec 01, com o destino Moradores ainda vazio. Esta spec preenche esse destino. O portal da Spec 02 usa o morador criado aqui.
- **Atores:** Funcionário ativo e logado.
- **Descrição do comportamento:** No destino Moradores, a equipe vê a lista em ordem alfabética do nome completo, com e-mail, torre/apartamento, telefone e situação (ativo ou desativado). Pode cadastrar um morador novo com esses quatro dados, sem senha. Pode abrir um morador e alterar qualquer um dos quatro dados. Pode desativar um ativo e reativar um desativado. Desativar e reativar pedem confirmação antes de valer. Desativar não apaga o registro. Não existe ação de excluir. Um morador desativado permanece na lista, marcado como desativado, e deixa de conseguir entrar no portal. Se o e-mail for alterado, a próxima entrada usa o e-mail novo; o antigo deixa de funcionar.
- **Entradas e saídas:** Entram nome completo, e-mail, torre/apartamento e telefone, além da confirmação de desativar ou reativar. Sai a lista atualizada e o morador disponível, ou não, para a entrada por e-mail. Em erro, o formulário permanece preenchido e indica o problema.
- **Dados/entidades envolvidos (conceitual):** Morador: nome completo, e-mail, torre/apartamento (um único texto, por exemplo "Torre B, apto 104"), telefone, situação ativo ou desativado. Não há senha. Não há foto de perfil.
- **Estados e transições:** Novo cadastro nasce ativo. Ativo → desativado, com confirmação. Desativado → ativo, com confirmação. Não há estado excluído.
- **Regras de negócio:** Só funcionário identificado acessa esta área. E-mail do morador é único entre moradores e não pode coincidir com e-mail de funcionário. A unicidade ignora maiúsculas e minúsculas. Desativar não apaga ocorrências futuras nem, quando elas existirem, as já feitas por essa pessoa. Telefone e e-mail são dados da gestão; no portal do morador eles não aparecem para os outros moradores (Spec 07).
- **Validações:**
  - Nome completo obrigatório, com pelo menos um nome e um sobrenome, até 120 caracteres, sem contar espaços nas pontas.
  - E-mail obrigatório, em formato de e-mail, até 160 caracteres.
  - Torre/apartamento obrigatória, até 80 caracteres.
  - Telefone obrigatório, com pelo menos 10 dígitos, aceitando pontuação comum de telefone brasileiro. O que se guarda é o que foi digitado, limitado a 20 caracteres.
  - E-mail repetido de outro morador: "Já existe um morador com este e-mail."
  - E-mail igual ao de um funcionário: "Este e-mail já pertence a um funcionário."
- **Fluxo do usuário (passo a passo):**
  1. O funcionário entra no dashboard e abre Moradores.
  2. Vê a lista, ou a mensagem de lista vazia se ainda não houver ninguém além da necessidade de cadastrar o primeiro.
  3. Escolhe cadastrar, preenche os quatro campos e confirma.
  4. O morador aparece na lista como ativo.
  5. Para corrigir, abre o morador, altera os campos e salva.
  6. Para tirar o acesso, escolhe desativar e confirma. Para devolver, escolhe reativar e confirma.
- **Casos de borda e erros:**
  - Lista vazia: "Nenhum morador cadastrado." e a ação de cadastrar continua visível.
  - Campo obrigatório vazio ou telefone com menos de 10 dígitos: o registro não salva e o campo é indicado.
  - E-mail duplicado: não salva e mostra a mensagem correspondente.
  - Confirmação de desativar ou reativar recusada: a situação permanece como estava.
  - Visitante ou morador abre esta área: vê o login da equipe, sem dados de moradores.
  - Dois cadastros simultâneos com o mesmo e-mail: só um é aceito; o outro recebe a mensagem de e-mail já existente.
- **Impacto no existente:** Preenche o destino Moradores do dashboard. Passa a ser a origem dos moradores que a Spec 02 identifica.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado um funcionário logado, quando cadastra nome, e-mail, torre/apartamento e telefone válidos, então o morador aparece na lista como ativo e não há senha para informar.
  - Dado um morador ativo, quando a equipe altera a torre/apartamento e salva, então a lista mostra o valor novo.
  - Dado um morador ativo, quando a equipe desativa e confirma, então a situação fica desativada e esse e-mail não entra no portal.
  - Dado um morador desativado, quando a equipe reativa e confirma, então o e-mail volta a entrar no portal.
  - Dado um e-mail já usado por outro morador ou por um funcionário, quando tenta salvar, então o sistema recusa e explica qual dos dois conflitos ocorreu.
  - Dado a confirmação de desativar ainda não aceita, quando a equipe cancela, então o morador continua ativo.
- **Definição de pronto:** A equipe cadastra, corrige, desativa e reativa moradores, a lista mostra a situação, e-mails duplicados não passam, e quem não é funcionário não vê esses dados.
- **Dependências:** Spec 01, para o dashboard e o destino Moradores. A Spec 02 depende desta para ter quem entrar.
- **Fora do escopo desta spec:** Autocadastro do morador, exclusão definitiva, ocorrências, importar planilha e busca na lista.

### Spec 04 — Gestão de funcionários

- **Fase:** Fase 2 — Pessoas
- **Objetivo (o quê):** O funcionário logado cadastra outros funcionários, desativa e reativa contas, e troca a própria senha.
- **Intenção (por quê):** Mais de uma pessoa da administração precisa operar o dashboard. Desativar tira o acesso de quem saiu da equipe sem apagar o nome do histórico de status. Trocar a própria senha evita que a senha da implantação fique valendo para sempre, já que não há recuperação por e-mail.
- **Contexto:** O dashboard da Spec 01 tem o destino Equipe ainda vazio, e o funcionário inicial já existe. O e-mail dos funcionários também entra na regra de unicidade da Spec 03.
- **Atores:** Funcionário ativo e logado.
- **Descrição do comportamento:** No destino Equipe, a lista mostra nome, e-mail e situação, em ordem alfabética do nome. A senha nunca aparece. O funcionário logado cadastra outro com nome completo, e-mail e senha. A conta nova nasce ativa e já pode entrar. Não há edição de nome nem de e-mail. Desativar e reativar pedem confirmação. O sistema recusa desativar quando aquele for o único funcionário ativo, inclusive se a pessoa tentar desativar a si mesma sendo a última. O funcionário logado pode substituir a própria senha: informa a senha atual e a nova, duas vezes. Não consegue definir a senha de outra pessoa. O funcionário inicial aparece na lista como os demais e segue as mesmas regras.
- **Entradas e saídas:** Entram nome, e-mail e senha no cadastro; confirmação na desativação e na reativação; senha atual e senha nova na troca. Sai a lista atualizada, ou uma mensagem de erro sem alterar a conta. A senha nova passa a valer no próximo login. A sessão atual da troca de senha permanece válida.
- **Dados/entidades envolvidos (conceitual):** Funcionário: nome completo, e-mail, senha, situação ativo ou desativado. A senha é secreta. Não há telefone nem torre/apartamento de funcionário neste recorte.
- **Estados e transições:** Novo funcionário nasce ativo. Ativo → desativado, se ainda restar outro ativo, com confirmação. Desativado → ativo, com confirmação. Não há estado excluído.
- **Regras de negócio:** Só funcionário identificado acessa esta área. E-mail único entre funcionários e diferente de qualquer e-mail de morador, ignorando maiúsculas e minúsculas. Sempre resta pelo menos um ativo. Desativar não apaga o nome que já tenha sido, ou venha a ser, mostrado no histórico de status. Não existe recuperação de senha por e-mail. Não existe alteração de nome ou e-mail.
- **Validações:**
  - Nome completo obrigatório, com pelo menos um nome e um sobrenome, até 120 caracteres.
  - E-mail obrigatório, em formato de e-mail, até 160 caracteres.
  - Senha obrigatória, com no mínimo 8 caracteres.
  - Na troca, a senha atual precisa conferir com a senha vigente. A nova senha tem no mínimo 8 caracteres e as duas digitações da senha nova precisam ser iguais.
  - E-mail de outro funcionário: "Já existe um funcionário com este e-mail."
  - E-mail de um morador: "Este e-mail já pertence a um morador."
  - Senha atual errada: "A senha atual não confere."
  - Último ativo: "É preciso manter pelo menos um funcionário ativo."
- **Fluxo do usuário (passo a passo):**
  1. O funcionário abre Equipe no dashboard.
  2. Vê a lista, incluindo o funcionário inicial.
  3. Cadastra outro funcionário com nome, e-mail e senha.
  4. Esse segundo funcionário entra pela porta da equipe com a senha definida.
  5. Quem está logado abre a troca da própria senha, informa a atual e a nova, e confirma.
  6. Para tirar o acesso de alguém, escolhe desativar e confirma, desde que sobre outro ativo.
- **Casos de borda e erros:**
  - Tentativa de desativar o último ativo: a situação não muda e aparece "É preciso manter pelo menos um funcionário ativo."
  - Confirmação cancelada: a situação não muda.
  - Senha com menos de 8 caracteres, ou confirmação diferente da senha nova: não salva e indica o campo.
  - Funcionário desativado no meio da sessão: a próxima ação no dashboard encerra a sessão e mostra "Esta conta de funcionário está desativada."
  - Visitante ou morador abre Equipe: vê o login da equipe, sem a lista.
  - Reativar um desativado: volta a entrar com a mesma senha de antes. A reativação não redefine senha.
- **Impacto no existente:** Preenche o destino Equipe. O login da Spec 01 passa a aceitar os novos funcionários ativos e a recusar os desativados. A unicidade de e-mail da Spec 03 considera também estas contas.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado um funcionário logado, quando cadastra nome, e-mail e senha válidos, então a nova conta aparece como ativa e consegue entrar no dashboard.
  - Dado a lista da equipe, quando alguém olha um funcionário, então vê nome, e-mail e situação, e não vê a senha.
  - Dado dois funcionários ativos, quando um desativa o outro e confirma, então o desativado não entra mais.
  - Dado um único funcionário ativo, quando tenta desativar a si mesmo, então vê "É preciso manter pelo menos um funcionário ativo." e continua podendo entrar.
  - Dado um funcionário logado, quando informa a senha atual correta e uma senha nova válida, então o próximo login exige a senha nova.
  - Dado a senha atual errada, quando tenta trocar, então vê "A senha atual não confere." e a senha antiga continua valendo.
  - Dado um e-mail de morador, quando tenta usá-lo num funcionário novo, então o sistema recusa com "Este e-mail já pertence a um morador."
- **Definição de pronto:** Dá para criar outro funcionário, impedi-lo de entrar ao desativar, devolver o acesso ao reativar, impedir a desativação do último ativo e trocar a própria senha. Nome e e-mail de funcionário não têm edição.
- **Dependências:** Spec 01, para o login, o funcionário inicial e o destino Equipe.
- **Fora do escopo desta spec:** Esqueci minha senha, editar nome ou e-mail, definir a senha de outra pessoa, excluir funcionário e cadastrar morador.

### Spec 05 — Abertura de ocorrência

- **Fase:** Fase 4 — Ocorrências
- **Objetivo (o quê):** O morador identificado registra uma ocorrência com título, descrição, categoria, local e, se quiser, uma foto. Ela nasce Aberta e não pode mais ser editada.
- **Intenção (por quê):** Este é o registro que substitui o pedido solto. A foto ajuda a equipe a entender o problema sem ser obrigatória, porque nem todo relato tem imagem, e nem todo morador consegue tirar a foto na hora.
- **Contexto:** O morador entra pela Spec 02. As categorias e os status estão fixos nas regras deste PRD. O detalhe que exibe o resultado é a Spec 07. A equipe não possui este formulário.
- **Atores:** Morador ativo e identificado.
- **Descrição do comportamento:** No portal, o morador pede para abrir uma ocorrência e preenche título, descrição, categoria e local. A categoria é uma das seis fixas. O local é texto livre, escrito por quem abre, por exemplo "Piscina", "Garagem G2" ou "Hall da Torre A". A foto é opcional e no máximo uma. Se não houver foto, a ocorrência é criada assim mesmo. Se houver foto, ela só é aceita quando for uma imagem e for guardada com sucesso; se a imagem não puder ser salva, a ocorrência inteira não é criada e os campos permanecem preenchidos para tentar de novo. Ao salvar, o status é Aberto, o autor é o morador da sessão, a data de abertura é o momento do envio, e o sistema abre o detalhe dessa ocorrência. Não há rascunho. Não há como editar nem apagar depois.
- **Entradas e saídas:** Entram título, descrição, categoria, local e, opcionalmente, uma imagem, sempre da sessão do morador. Sai a ocorrência Aberta, ligada a esse morador, pronta para a lista e para o detalhe. Em falha, nada é criado.
- **Dados/entidades envolvidos (conceitual):** Ocorrência: título, descrição, categoria, local, foto opcional, status inicial Aberto, autor (o morador), data de abertura. Categorias: Manutenção, Limpeza, Barulho, Segurança, Áreas comuns, Outros.
- **Estados e transições:** Não existe antes do envio. No envio bem-sucedido, passa a existir como Aberta. Mudanças posteriores de status não acontecem nesta spec.
- **Regras de negócio:** Só morador ativo identificado cria. Funcionário não cria. A ocorrência é de todo o condomínio: entra na lista de todos. O autor fica gravado mesmo que o morador seja desativado depois. Uma foto, no máximo. Sem foto é válido. Falha na foto impede a criação. Conteúdo publicado não é editado nem apagado.
- **Validações:**
  - Título obrigatório, até 120 caracteres, não pode ser só espaço.
  - Descrição obrigatória, até 2000 caracteres, não pode ser só espaço.
  - Categoria obrigatória e uma das seis.
  - Local obrigatório, até 120 caracteres, não pode ser só espaço.
  - Foto ausente é válida. Se presente, precisa ser uma imagem. Caso contrário: "A foto precisa ser uma imagem."
  - Se a imagem não puder ser guardada: "Não foi possível salvar a foto. A ocorrência não foi registrada."
- **Fluxo do usuário (passo a passo):**
  1. O morador identificado escolhe abrir uma ocorrência.
  2. Preenche título, descrição, categoria e local.
  3. Anexa uma imagem, ou deixa sem foto.
  4. Confirma.
  5. Vê o detalhe da ocorrência recém-criada, com status Aberto.
- **Casos de borda e erros:**
  - Campo obrigatório vazio: não cria e indica o campo. O que já foi preenchido permanece.
  - Arquivo que não é imagem: não cria e mostra "A foto precisa ser uma imagem."
  - Falha ao guardar a imagem: não cria e mostra "Não foi possível salvar a foto. A ocorrência não foi registrada."
  - Morador desativado no meio do preenchimento: o envio não cria a ocorrência, encerra a sessão e mostra a mensagem de morador desativado.
  - Funcionário ou visitante tenta abrir o formulário: visitante cai no pedido de e-mail; funcionário não tem esta ação no dashboard.
  - Duplo envio: cada envio aceito cria uma ocorrência. Não há fusão automática de relatos parecidos.
- **Impacto no existente:** Adiciona a ação de abrir ocorrência no portal do morador. Não muda o cadastro de pessoas.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado um morador identificado, quando envia título, descrição, categoria e local válidos sem foto, então existe uma ocorrência Aberta, de autoria dele, e o detalhe é aberto.
  - Dado o mesmo formulário com uma imagem válida, quando o envio guarda a foto, então a ocorrência existe e a foto permanece associada a ela.
  - Dado um arquivo que não é imagem, quando tenta enviar, então a ocorrência não é criada e ele vê "A foto precisa ser uma imagem."
  - Dado a foto não pôde ser guardada, quando o envio termina, então a ocorrência não existe e os campos continuam preenchidos.
  - Dado um funcionário logado no dashboard, quando procura onde abrir ocorrência, então essa ação não é oferecida.
  - Dado uma ocorrência já criada, quando o autor procura editar ou apagar, então essas ações não existem.
- **Definição de pronto:** O morador cria ocorrência com e sem foto, a autoria e o status Aberto ficam gravados, falha de foto não gera registro pela metade, e não há edição nem exclusão.
- **Dependências:** Spec 02, para o morador identificado. Spec 03, para o cadastro desse morador. A exibição completa do detalhe é a Spec 07; até ela existir, o resultado mínimo desta spec é a ocorrência criada e uma confirmação visível de que foi registrada, com os dados enviados.
- **Fora do escopo desta spec:** Lista, filtros, comentários, mudança de status, mais de uma foto e abertura pela equipe.

### Spec 06 — Lista e filtros de ocorrências

- **Fase:** Fase 4 — Ocorrências
- **Objetivo (o quê):** Morador e funcionário veem todas as ocorrências do condomínio, da mais recente para a mais antiga, e reduzem a lista por status e por categoria.
- **Intenção (por quê):** A lista é o quadro único que o problema pede. O morador acompanha o condomínio inteiro, e a equipe encontra o que ainda precisa de ação sem ler relato por relato.
- **Contexto:** As ocorrências nascem na Spec 05. O detalhe aberto a partir da lista é a Spec 07. O portal existe na Spec 02 e o dashboard na Spec 01. Esta spec preenche o destino Ocorrências dos dois lados.
- **Atores:** Morador ativo identificado. Funcionário ativo logado.
- **Descrição do comportamento:** Os dois veem a mesma coleção de ocorrências, com os mesmos filtros. A ordem é a data de abertura, da mais recente para a mais antiga. Cada item mostra título, um trecho curto da descrição, categoria, status, local, nome de quem abriu, torre/apartamento, data de abertura e quantidade de comentários. Não mostra telefone, e-mail nem a foto inteira; a foto fica no detalhe. O status usa a identificação visual já definida no projeto para Aberto, Em Análise, Em Execução, Resolvido e Cancelado. Os filtros são status e categoria. Cada um começa em "Todos". Dá para escolher um status, uma categoria, ou um de cada. Os dois filtros valem juntos. Limpar filtros volta a mostrar todas. Clicar num item abre o detalhe daquela ocorrência. No portal, a ação de abrir nova ocorrência permanece visível junto da lista, tenha item ou não. No dashboard, essa ação não existe. Para o funcionário, a lista de ocorrências é a primeira tela do dashboard depois do login.
- **Entradas e saídas:** Entram a sessão (morador ou funcionário) e, se a pessoa filtrar, um status e/ou uma categoria. Sai a lista correspondente, ou o estado vazio. A navegação leva ao detalhe de uma ocorrência.
- **Dados/entidades envolvidos (conceitual):** Os mesmos dados da ocorrência usados na lista: título, trecho da descrição, categoria, status, local, autor (nome e torre/apartamento), data de abertura, quantidade de comentários. A quantidade é zero enquanto a Spec 08 não tiver comentários; o número mostrado acompanha os comentários existentes.
- **Estados e transições:** Não se aplica à lista em si. Ela reflete o status atual de cada ocorrência, inclusive Resolvido e Cancelado, que continuam aparecendo.
- **Regras de negócio:** Morador vê todas, não só as próprias. Funcionário vê todas. Filtros combinados exigem os dois critérios. A ordem não muda por causa de comentário novo: continua pela data de abertura. Morador desativado e visitante não veem a lista. Funcionário só vê a lista dentro do dashboard.
- **Validações:** Status do filtro, quando não for "Todos", é um dos cinco. Categoria, quando não for "Todos", é uma das seis. Valor fora dessas opções não é oferecido.
- **Fluxo do usuário (passo a passo):**
  1. O morador entra no portal, ou o funcionário entra no dashboard.
  2. Vê a lista completa, da mais recente para a mais antiga.
  3. Escolhe um status, uma categoria, ou os dois.
  4. A lista mostra só o que combina.
  5. Limpa os filtros e a lista volta ao todo.
  6. Abre uma ocorrência para ver o detalhe.
- **Casos de borda e erros:**
  - Nenhuma ocorrência cadastrada: "Nenhuma ocorrência ainda." No portal, a ação de abrir a primeira continua visível. No dashboard, o texto explica que as ocorrências aparecem quando um morador abre.
  - Filtros sem resultado: "Nenhuma ocorrência com esses filtros." e a ação de limpar filtros está visível.
  - Ocorrência encerrada: continua na lista, com o status Resolvido ou Cancelado.
  - Autor desativado: o item continua, com o nome e a torre/apartamento gravados.
  - Visitante abre a lista do portal: cai no pedido de e-mail. Visitante abre a lista da equipe: cai no login.
  - Sessão encerrada porque a pessoa foi desativada: a lista não é mostrada; vale a mensagem de conta desativada da spec de entrada correspondente.
- **Impacto no existente:** O destino Ocorrências deixa de ser vazio nos dois lados. Depois do login, o funcionário cai nesta lista. O portal do morador também abre nela.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado ocorrências de autores diferentes, quando um morador abre a lista, então vê todas, da mais recente para a mais antiga.
  - Dado a mesma base, quando um funcionário abre o dashboard, então a primeira tela é essa lista, com as mesmas ocorrências.
  - Dado um filtro de status Aberto e categoria Barulho, quando aplica, então só aparecem ocorrências que são Abertas e de Barulho.
  - Dado filtros que não combinam com nada, quando aplica, então vê "Nenhuma ocorrência com esses filtros."
  - Dado um item da lista, quando é exibido, então mostra título, trecho da descrição, categoria, status, local, nome, torre/apartamento, data de abertura e quantidade de comentários, e não mostra telefone nem e-mail.
  - Dado a lista no dashboard, quando o funcionário procura abrir uma ocorrência nova, então essa ação não existe.
  - Dado um item, quando a pessoa clica, então abre o detalhe daquela ocorrência.
- **Definição de pronto:** Os dois públicos veem a coleção inteira, filtram por status, por categoria e pelos dois, entendem a lista vazia e o filtro sem resultado, e chegam ao detalhe a partir de um item.
- **Dependências:** Spec 05, para existir ocorrência. Spec 07, para o clique ter destino. Spec 02 e Spec 01, para as duas áreas autenticadas. A quantidade de comentários fica correta quando a Spec 08 existir; antes disso, zero é o comportamento certo.
- **Fora do escopo desta spec:** Busca por texto, filtro por torre, ordenar por outro critério, editar pela lista e mudar status pela lista.

### Spec 07 — Detalhe da ocorrência

- **Fase:** Fase 4 — Ocorrências
- **Objetivo (o quê):** Morador e funcionário abrem uma ocorrência e leem o registro completo, incluindo a foto e a conversa já existente.
- **Intenção (por quê):** A lista só apresenta o problema. A decisão da equipe e o comentário do morador dependem de ver o relato inteiro, o local, a imagem e quem pediu.
- **Contexto:** A ocorrência é criada na Spec 05 e encontrada na Spec 06. Os comentários exibidos aqui são os já publicados; escrever um novo é a Spec 08. Mudar status é a Spec 09. O visual dos status já está definido no projeto.
- **Atores:** Morador ativo identificado. Funcionário ativo logado.
- **Descrição do comportamento:** O detalhe mostra título, descrição completa, categoria, local, status, data de abertura, nome do autor e torre/apartamento. Se houver foto, ela aparece e pode ser vista por quem chegou ao detalhe. Se não houver, não aparece um espaço vazio de imagem. A conversa mostra os comentários já feitos, do mais antigo para o mais recente, cada um com nome de quem escreveu, se é morador ou equipe, torre/apartamento quando for morador, texto e data. Sem comentários, a área da conversa diz que ainda não há comentário. O morador não vê telefone nem e-mail do autor. O funcionário vê, além do que o morador vê, o telefone e o e-mail do autor, para conseguir falar com quem abriu. Os dois veem uma forma de voltar à lista. Não há editar, apagar, comentar nem mudar status nesta spec: comentar e mudar status entram nas specs seguintes e, até lá, o detalhe é só leitura.
- **Entradas e saídas:** Entra a identificação da ocorrência, a partir da lista ou de um acesso direto de quem já está identificado. Sai o registro completo, ou a mensagem de não encontrada. Para o funcionário, saem também telefone e e-mail do autor.
- **Dados/entidades envolvidos (conceitual):** Ocorrência, como na Spec 05, mais o autor com nome, torre/apartamento e, só para a equipe, telefone e e-mail. Comentário, quando já existir: texto, autor, papel (morador ou equipe), torre/apartamento se morador, data.
- **Estados e transições:** Não se aplica. O detalhe apenas reflete o status atual, inclusive encerrado.
- **Regras de negócio:** Qualquer morador identificado vê qualquer ocorrência do condomínio. Qualquer funcionário logado vê qualquer ocorrência. Telefone e e-mail não vazam para o portal. Autor desativado continua nomeado. Ocorrência inexistente não revela dados de outras.
- **Validações:** A ocorrência precisa existir. A pessoa precisa estar identificada no lado em que está: morador no portal, funcionário no dashboard.
- **Fluxo do usuário (passo a passo):**
  1. A pessoa abre um item da lista.
  2. Lê o relato, o status, o local e o autor.
  3. Vê a foto, se a ocorrência tiver uma.
  4. Lê a conversa, ou vê que ainda não há comentário.
  5. Volta à lista.
- **Casos de borda e erros:**
  - Ocorrência inexistente: "Ocorrência não encontrada." e um caminho de volta à lista.
  - Sem foto: o detalhe não reserva um bloco de imagem.
  - Sem comentários: "Nenhum comentário ainda."
  - Autor desativado: nome e torre/apartamento continuam. Para a equipe, telefone e e-mail também continuam.
  - Visitante no endereço do detalhe do portal: vai ao pedido de e-mail. Depois de se identificar, consegue abrir aquela ocorrência, porque todo morador vê todas.
  - Visitante no detalhe do dashboard: vai ao login da equipe.
  - Morador abre o detalhe pelo dashboard, ou funcionário abre o detalhe pelo portal sem ser morador: cada um só vê o detalhe no lado em que está identificado.
- **Impacto no existente:** Dá destino aos itens da lista. Não altera o conteúdo da ocorrência criada na Spec 05.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado uma ocorrência com foto, quando um morador abre o detalhe, então vê título, descrição, categoria, local, status, data, nome, torre/apartamento e a foto, e não vê telefone nem e-mail.
  - Dado a mesma ocorrência, quando um funcionário abre o detalhe, então vê também o telefone e o e-mail do autor.
  - Dado uma ocorrência sem foto e sem comentários, quando alguém abre o detalhe, então não há bloco de imagem e a conversa diz "Nenhum comentário ainda."
  - Dado um identificador inexistente, quando alguém identificado tenta abrir, então vê "Ocorrência não encontrada."
  - Dado uma ocorrência de outro morador, quando um morador qualquer abre a lista e entra no item, então o detalhe é exibido.
- **Definição de pronto:** Os dois públicos leem o registro certo, a foto aparece só quando existe, o morador não vê contato do autor, a equipe vê, e o identificador inválido não quebra a tela.
- **Dependências:** Spec 05, para a ocorrência. Spec 06, como caminho normal de chegada. Spec 01 e Spec 02, para saber quem está olhando. A lista de comentários usa o que a Spec 08 vier a gravar.
- **Fora do escopo desta spec:** Escrever comentário, mudar status, editar campos e mostrar o histórico de status. O histórico entra na Spec 09.

### Spec 08 — Comentários

- **Fase:** Fase 4 — Ocorrências
- **Objetivo (o quê):** Morador identificado e funcionário logado publicam um comentário no detalhe de uma ocorrência que ainda não foi encerrada.
- **Intenção (por quê):** A ocorrência sozinha não chega para a portaria combinar o conserto nem para um vizinho acrescentar o que viu. O comentário é a conversa embaixo do relato, visível para todo mundo que abre o detalhe.
- **Contexto:** O detalhe da Spec 07 já mostra a conversa. Esta spec adiciona o campo de escrever. O encerramento que trava o campo é a Spec 09; enquanto o status não for Resolvido nem Cancelado, o campo existe.
- **Atores:** Morador ativo identificado, tenha sido ele o autor da ocorrência ou não. Funcionário ativo logado.
- **Descrição do comportamento:** No detalhe de uma ocorrência Aberta, Em Análise ou Em Execução, a pessoa escreve um texto e publica. O comentário entra no fim da conversa, com o nome de quem escreveu, o papel (morador ou equipe), a torre/apartamento se for morador, o texto e a data. O campo fica vazio de novo, pronto para outro comentário. Não há edição nem exclusão. Não há foto no comentário. Em ocorrência Resolvida ou Cancelada, o campo não é oferecido. Se o status encerrar enquanto a pessoa ainda está com o texto digitado, o envio é recusado e o comentário não entra. O autor do comentário permanece o mesmo mesmo que a pessoa seja desativada depois.
- **Entradas e saídas:** Entram o texto e a sessão de quem escreve, ligados a uma ocorrência existente. Sai o comentário no fim da conversa, visível para morador e equipe no detalhe e contabilizado na lista. Em recusa, a conversa não muda.
- **Dados/entidades envolvidos (conceitual):** Comentário: texto, autor (morador ou funcionário), papel, torre/apartamento quando o autor for morador, data, ocorrência a que pertence.
- **Estados e transições:** O comentário nasce publicado. Não muda e não é apagado. A ocorrência não muda de status por causa do comentário.
- **Regras de negócio:** Qualquer morador identificado comenta em qualquer ocorrência não encerrada, inclusive na dos outros. Qualquer funcionário logado comenta. Resolvido e Cancelado não recebem comentário. Comentário não edita e não apaga. Um comentário não altera título, descrição, local, foto nem status.
- **Validações:** Texto obrigatório, não pode ser só espaço, até 1000 caracteres. Ocorrência precisa existir e estar Aberta, Em Análise ou Em Execução. A pessoa precisa estar identificada no lado em que comenta.
- **Fluxo do usuário (passo a passo):**
  1. A pessoa abre o detalhe de uma ocorrência não encerrada.
  2. Escreve o comentário.
  3. Publica.
  4. Vê o próprio comentário no fim da conversa e o campo vazio outra vez.
- **Casos de borda e erros:**
  - Texto vazio ou só com espaço: não publica e mostra "Escreva um comentário antes de enviar."
  - Texto acima de 1000 caracteres: não publica e indica o limite.
  - Ocorrência encerrada: o campo não aparece. Se o envio chegar mesmo assim, nada é gravado e a pessoa vê "Ocorrência encerrada não recebe comentários."
  - Ocorrência inexistente: "Ocorrência não encontrada."
  - Sessão caiu ou a pessoa foi desativada antes do envio: o comentário não é gravado e vale a mensagem de entrada da spec correspondente.
  - Dois comentários publicados quase juntos: os dois aparecem, do mais antigo para o mais recente.
- **Impacto no existente:** O detalhe da Spec 07 ganha o campo de publicar quando o status permite. A quantidade de comentários na lista da Spec 06 passa a contar os novos.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado uma ocorrência Aberta de outro morador, quando um morador identificado comenta, então o texto aparece no fim, com o nome dele, o papel morador, a torre/apartamento e a data.
  - Dado uma ocorrência Em Análise, quando um funcionário comenta, então o comentário aparece com o nome dele e o papel equipe, sem torre/apartamento.
  - Dado um comentário publicado, quando o autor procura editar ou apagar, então essas ações não existem e o texto segue igual.
  - Dado uma ocorrência Resolvida ou Cancelada, quando alguém abre o detalhe, então não há campo de comentário.
  - Dado o campo preenchido e a ocorrência encerrada antes do envio, quando a pessoa publica, então o comentário não entra e ela vê "Ocorrência encerrada não recebe comentários."
  - Dado um comentário novo, quando a lista é aberta, então a quantidade de comentários daquele item inclui o comentário recém-publicado.
- **Definição de pronto:** Morador e funcionário comentam em ocorrência não encerrada, a conversa fica visível para os dois públicos, encerrada não aceita comentário, e não há edição nem exclusão.
- **Dependências:** Spec 07, para o detalhe onde o campo vive. Spec 05, para a ocorrência. Spec 01 e Spec 02, para as sessões. A trava de encerrado fica coberta também pela Spec 09, que é quem leva o status até Resolvido ou Cancelado.
- **Fora do escopo desta spec:** Comentário com foto, editar, apagar, mencionar pessoa, e comentar a partir da lista sem abrir o detalhe.

### Spec 09 — Mudança de status

- **Fase:** Fase 4 — Ocorrências
- **Objetivo (o quê):** O funcionário muda o status de uma ocorrência ainda não encerrada e, ao escolher Resolvido ou Cancelado, encerra de forma definitiva. O detalhe mostra o histórico dessas trocas.
- **Intenção (por quê):** A lista só é útil se a equipe conseguir marcar o que está em análise, o que está em execução e o que já acabou. O encerramento é irreversível para ninguém reabrir um caso encerrado por engano sem perceber, e o histórico mostra quem fez a última troca.
- **Contexto:** A ocorrência nasce Aberta na Spec 05. O detalhe é a Spec 07. O comentário da Spec 08 depende deste status para saber se ainda pode ser escrito. O morador vê o status e o histórico, e não vê o controle.
- **Atores:** Funcionário ativo e logado, que muda o status. Morador identificado, que apenas vê o status e o histórico.
- **Descrição do comportamento:** No detalhe, dentro do dashboard, enquanto o status for Aberto, Em Análise ou Em Execução, o funcionário vê as outras quatro opções de status. Pode ir de qualquer uma das três para qualquer outra, ou direto para Resolvido ou Cancelado, sem comentar. Troca entre Aberto, Em Análise e Em Execução vale na hora. Escolher Resolvido ou Cancelado pede confirmação avisando que a ocorrência será encerrada, não receberá comentários e não voltará a um status aberto. Se a confirmação for cancelada, o status permanece. Se for aceita, o status muda, o controle some e o campo de comentário também some. Cada troca entra num histórico visível para morador e equipe, com a data, o status novo e o nome do funcionário. A abertura também aparece no histórico como o início, com a data e o nome do morador, status Aberto. O histórico é só leitura, do mais antigo para o mais recente. No portal, o morador vê o status e o histórico e não vê controle. Em ocorrência já encerrada, o controle não é oferecido nos dois lados.
- **Entradas e saídas:** Entra o status escolhido e, no caso de Resolvido ou Cancelado, a confirmação, sempre de um funcionário logado. Sai o status novo, uma linha no histórico e, se encerrou, a retirada do campo de comentário e do controle. Se a pessoa recusa a confirmação, sai tudo como estava.
- **Dados/entidades envolvidos (conceitual):** Status da ocorrência. Cada linha do histórico: data, status registrado, quem registrou (morador na abertura, funcionário nas trocas). A ocorrência não ganha outro campo editável.
- **Estados e transições:** Aberto, Em Análise e Em Execução podem ir para qualquer um dos cinco, exceto repetir o status atual. Resolvido e Cancelado não saem para nenhum outro. A abertura é a primeira linha, sempre Aberto, feita pelo morador.
- **Regras de negócio:** Só funcionário muda status. A mudança não exige comentário. Não há ordem obrigatória entre os três status de andamento. Resolvido e Cancelado encerram para sempre. O morador não recebe controle mesmo sendo o autor. O nome de um funcionário desativado depois continua na linha do histórico que ele já gerou.
- **Validações:** O status destino é um dos cinco e é diferente do atual. A ocorrência existe e não está Resolvida nem Cancelada. Quem envia é funcionário ativo logado. Encerrar só vale depois da confirmação.
- **Fluxo do usuário (passo a passo):**
  1. O funcionário abre o detalhe de uma ocorrência Aberta, Em Análise ou Em Execução.
  2. Escolhe outro status de andamento e a tela passa a mostrar o status novo e a nova linha do histórico.
  3. Ou escolhe Resolvido ou Cancelado.
  4. Lê a confirmação de encerramento.
  5. Confirma. O status encerra, o histórico ganha a linha e o comentário deixa de ser oferecido.
- **Casos de borda e erros:**
  - Confirmação de encerramento recusada: status, histórico e campo de comentário permanecem.
  - Tentativa de mudar uma ocorrência já encerrada: o controle não aparece. Se o pedido chegar, nada muda e a pessoa vê "Ocorrência encerrada não muda de status."
  - Morador tenta mudar: o controle não existe no portal. Se o pedido chegar, nada muda.
  - Funcionário desativado no meio da ação: a troca não vale, a sessão encerra e aparece a mensagem de conta desativada.
  - Escolher o status que já está valendo: essa opção não é oferecida.
  - Ocorrência inexistente: "Ocorrência não encontrada."
- **Impacto no existente:** O detalhe do dashboard ganha o controle de status. O detalhe dos dois lados ganha o histórico. A Spec 08 passa a esconder e recusar comentário quando o status resultante for Resolvido ou Cancelado. A lista da Spec 06 mostra o status novo e continua incluindo a ocorrência.
- **Critérios de aceite (Dado/Quando/Então):**
  - Dado uma ocorrência Aberta, quando o funcionário escolhe Em Execução, então o status passa a Em Execução sem pedido de confirmação e o histórico ganha uma linha com o nome dele e a data.
  - Dado uma ocorrência Em Análise, quando o funcionário escolhe Resolvido e confirma, então o status fica Resolvido, o controle some e o campo de comentário some para morador e equipe.
  - Dado a confirmação de Cancelado ainda aberta, quando o funcionário desiste, então o status anterior permanece e ainda dá para comentar.
  - Dado uma ocorrência Resolvida, quando o funcionário ou o morador abre o detalhe, então não há como escolher outro status.
  - Dado o portal do morador, quando o autor abre a própria ocorrência Aberta, então vê o status e o histórico e não vê controle de mudança.
  - Dado o histórico, quando os dois públicos abrem o detalhe, então veem a abertura pelo morador e cada troca seguinte pelo funcionário, da mais antiga para a mais recente.
- **Definição de pronto:** A equipe move o status com liberdade entre os três de andamento, encerra só com confirmação, ninguém reabre, o histórico fica visível para os dois públicos e o morador não tem controle.
- **Dependências:** Spec 07, para o detalhe. Spec 05, para a ocorrência Aberta. Spec 01, para o funcionário logado. Spec 08, para o campo de comentário que deve sumir no encerramento.
- **Fora do escopo desta spec:** Reabrir, exigir comentário na troca, mudar status pela lista, avisar o morador por e-mail e apagar uma linha do histórico.

## 14. Ordem recomendada de implementação

1. Spec 01 — Página inicial e entrada da equipe
2. Spec 03 — Gestão de moradores
3. Spec 04 — Gestão de funcionários
4. Spec 02 — Entrada do morador
5. Spec 05 — Abertura de ocorrência
6. Spec 07 — Detalhe da ocorrência
7. Spec 06 — Lista e filtros de ocorrências
8. Spec 08 — Comentários
9. Spec 09 — Mudança de status

A Spec 01 vem primeiro porque as outras ações da equipe acontecem dentro do dashboard. Moradores (03) vêm antes da entrada do morador (02), senão não existe e-mail que entre. Funcionários (04) ficam logo depois do login para a unicidade de e-mail já valer quando os moradores forem cadastrados; se a Spec 03 for implementada antes da 04, a checagem contra e-mail de funcionário precisa ser incluída assim que a Spec 04 existir. A ocorrência (05) só faz sentido com morador identificado. O detalhe (07) vem antes da lista (06) para o clique do item já ter destino. Comentários (08) e status (09) fecham o detalhe; a 09 fica por último porque é ela que trava o comentário ao encerrar.
