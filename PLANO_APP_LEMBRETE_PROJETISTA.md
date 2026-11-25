# Plano completo — App de Lembretes do Projetista

## 1. Objetivo

Criar um aplicativo Android para o projetista registrar, organizar e acompanhar pendências do dia a dia de forma rápida, mesmo fora do computador.

O app deve permitir:

- Tirar uma foto de uma peça, montagem, máquina ou situação de campo.
- Marcar cotas, medidas ou pontos de atenção sobre a foto.
- Escrever uma anotação técnica sobre o que precisa ser feito.
- Gravar um lembrete em áudio.
- Receber fotos, textos e, quando possível, áudios compartilhados pelo WhatsApp.
- Encaminhar uma tarefa ou mensagem de volta para o WhatsApp.
- Programar lembretes e despertadores.
- Organizar as tarefas do dia, pendências atrasadas e itens aguardando resposta.

A proposta não é substituir o SolidWorks, o `CONTROLE_PROJETO`, a Lista Suprema ou o sistema de projetos da empresa. O app é uma ferramenta de captura e acompanhamento de pendências no celular, criada para reduzir esquecimentos e facilitar a retomada do trabalho.

## 2. Problema que o app resolve

No dia a dia do projetista, surgem pendências em momentos em que não é prático abrir o computador:

- Um colega pede para conferir uma medida.
- Aparece uma interferência durante a montagem.
- Uma peça precisa ser alterada antes de liberar para corte.
- Surge uma dúvida sobre um detalhe de fabricação.
- É preciso lembrar de revisar um DXF, atualizar uma peça ou responder alguém.
- Uma foto tirada no celular fica perdida na galeria, sem contexto e sem explicação.

O problema central é que a informação fica dispersa entre fotos, conversas de WhatsApp, anotações, planilhas e a memória do projetista.

O app resolve isso criando uma **pendência visual**: foto, cota, texto, áudio, prazo e próxima ação ficam juntos.

## 3. Conceito do produto

O nome provisório do aplicativo é:

**Pendência Projetista**

Outras opções de nome:

- Foto Cota
- Lembrete Técnico
- Projeto em Dia
- Cota & Tarefa
- Nota de Obra
- Pendência Técnica

A ideia de uso é simples:

1. O projetista fotografa a situação.
2. Marca uma cota ou ponto de atenção.
3. Escreve ou grava o que precisa ser feito.
4. Define quando precisa lembrar.
5. O app organiza a pendência por projeto, prioridade e prazo.
6. No horário definido, o app avisa e abre a pendência completa.
7. O projetista pode encaminhar a informação para o WhatsApp ou marcar como concluída.

## 4. Público e uso principal

O usuário principal é o próprio projetista, que trabalha com:

- Projetos mecânicos.
- Detalhamento de peças.
- Montagens e ajustes.
- Fabricação e corte.
- Automatização.
- Acompanhamento de revisões.
- Comunicação com produção, montagem, fornecedores e colegas.

O uso principal será:

- Registrar uma pendência em menos de 30 segundos.
- Encontrar rapidamente o que precisa ser feito hoje.
- Saber qual peça, projeto ou situação originou a pendência.
- Evitar esquecer medidas, ajustes e revisões.
- Retomar uma tarefa com o contexto visual completo.

## 5. Funcionalidades da primeira versão

A primeira versão deve ser pequena, útil e testável. O objetivo é validar o fluxo principal antes de criar recursos avançados.

### 5.1. Tela inicial: Hoje

A tela inicial deve mostrar, de forma clara:

- Tarefas atrasadas.
- Tarefas para hoje.
- Tarefas para amanhã.
- Tarefas futuras.
- Tarefas concluídas recentemente.
- Quantidade total de pendências abertas.

Cada item deve mostrar:

- Miniatura da foto.
- Título da pendência.
- Projeto ou peça associada.
- Data e hora do lembrete.
- Prioridade.
- Status: aberta, concluída, aguardando resposta ou cancelada.

Exemplo de card:

```text
[ Foto do suporte ]
Suporte do sensor — conferir folga
Projeto: Capela Química
Cota: 35 mm
Prazo: hoje, 14h
Status: aberta
```

### 5.2. Criar pendência com foto

O usuário deve poder:

- Tirar foto pela câmera.
- Escolher uma foto da galeria.
- Receber uma foto compartilhada de outro aplicativo.
- Visualizar a foto em tela cheia.
- Adicionar título e descrição.
- Definir projeto, peça ou contexto.
- Definir prioridade.
- Definir data e hora do lembrete.
- Salvar a pendência.

A foto deve ser salva dentro do app, com uma cópia reduzida para listagem e a imagem original preservada para visualização.

### 5.3. Marcar cota na foto

Esta é uma das funcionalidades mais importantes do app.

O usuário poderá tocar em dois pontos da imagem para criar uma cota. O app deve desenhar uma linha entre os pontos e permitir digitar o valor da medida.

Exemplo:

```text
Ponto A: borda do furo
Ponto B: borda do suporte
Cota digitada: 35 mm
```

A cota deve aparecer sobre a foto, com:

- Linha de cota.
- Setas ou pontos nas extremidades.
- Valor digitado pelo usuário.
- Cor de destaque.
- Possibilidade de mover, editar ou apagar a cota.

Na primeira versão, o app **não deve tentar medir automaticamente** pela foto. A medição automática por imagem é complexa e pode gerar erro por perspectiva, distância da câmera e escala.

O app deve permitir ao usuário informar o valor real medido, por exemplo com trena, paquímetro ou régua.

### 5.4. Anotações de texto

Cada pendência deve ter um campo de texto para registrar:

- O que precisa ser feito.
- Qual peça ou projeto está envolvido.
- Qual medida precisa ser conferida.
- Qual alteração é necessária.
- Quem solicitou a tarefa.
- Qual é a próxima ação.

Exemplo:

```text
Conferir folga do suporte do sensor.
A cota de 35 mm pode ficar apertada depois da pintura.
Verificar antes de liberar o DXF para corte.
```

### 5.5. Lembrete em áudio

O usuário poderá gravar uma nota de voz diretamente no app.

O áudio deve ficar vinculado à pendência e poder ser ouvido depois.

Casos de uso:

- Registrar uma explicação rápida enquanto caminha pela fábrica.
- Explicar uma interferência sem precisar digitar.
- Guardar uma instrução recebida verbalmente.
- Anotar uma dúvida técnica antes de esquecer.

A primeira versão deve permitir:

- Gravar áudio.
- Parar gravação.
- Ouvir a gravação.
- Apagar a gravação.
- Associar o áudio a uma pendência.

Não é necessário transcrever o áudio automaticamente na primeira versão. A transcrição pode ser avaliada depois, pois depende de serviço de reconhecimento de fala, permissões e custo.

### 5.6. Receber conteúdo do WhatsApp

O app deve permitir receber conteúdo compartilhado pelo WhatsApp por meio do compartilhamento padrão do Android.

O usuário poderá:

- Selecionar uma mensagem, foto ou arquivo no WhatsApp.
- Tocar em “Compartilhar”.
- Escolher o app de pendências.
- O app cria um rascunho de pendência com o conteúdo recebido.

A primeira versão deve priorizar:

- Texto compartilhado.
- Imagem compartilhada.
- Foto recebida pelo WhatsApp.
- Texto junto com imagem, quando o Android entregar os dois formatos.

O comportamento do WhatsApp pode variar conforme a versão do aplicativo, o tipo de arquivo e o sistema Android. Por isso, o app deve tratar cada tipo de conteúdo separadamente e nunca prometer que conseguirá ler automaticamente todas as conversas.

### 5.7. Encaminhar para o WhatsApp

O app deve permitir compartilhar uma pendência para o WhatsApp.

O usuário poderá encaminhar:

- Texto da pendência.
- Foto com as cotas marcadas.
- Foto original.
- Resumo da tarefa.
- Data e hora do lembrete.
- Informações de projeto ou peça.

Exemplo de mensagem gerada:

```text
Pendência: Suporte do sensor — conferir folga
Projeto: Capela Química
Cota: 35 mm
Observação: verificar se o rasgo permite ajuste antes de liberar o DXF.
```

O compartilhamento deve usar o sistema padrão do Android. Assim, o usuário escolhe o contato, grupo ou conversa no WhatsApp.

### 5.8. Lembretes e notificações

Cada pendência pode ter um horário de lembrete.

Ao chegar o horário, o app deve:

- Mostrar uma notificação.
- Permitir abrir a pendência pelo toque na notificação.
- Mostrar a foto, a cota, o texto e o áudio.
- Permitir concluir, adiar ou reprogramar.

Tipos de lembrete:

- Lembrete único.
- Lembrete repetido diariamente.
- Lembrete em uma data futura.
- Lembrete com prioridade alta.

### 5.9. Despertador de tarefa

Além do lembrete comum, o app deve ter um modo despertador para tarefas importantes.

O despertador deve:

- Tocar mesmo com a tela bloqueada, quando autorizado pelo sistema.
- Exibir a pendência associada.
- Permitir adiar.
- Permitir marcar como concluída.
- Permitir abrir a foto e a anotação.

Na primeira versão, o despertador pode ser uma evolução do lembrete. O importante é distinguir os dois modos:

| Recurso | Lembrete | Despertador |
|---|---|---|
| Objetivo | Avisar sobre uma pendência | Garantir atenção imediata |
| Som | Notificação normal | Som mais forte e persistente |
| Tela bloqueada | Pode aparecer como notificação | Deve abrir tela de alarme |
| Adiar | Sim | Sim |
| Prioridade | Baixa, média ou alta | Alta |

O Android possui restrições para alarmes em horário exato. O app deve pedir a autorização adequada e informar ao usuário quando o modo despertador não estiver disponível.

### 5.10. Orientador de tarefas do dia

A tela “Hoje” deve funcionar como um orientador simples.

Ela deve organizar as pendências em blocos:

```text
Atrasadas
- Conferir folga do suporte do sensor
- Atualizar chapa do painel elétrico

Para hoje
- Revisar DXF da correia transportadora
- Responder fornecedor sobre perfil

Aguardando resposta
- Definição do tipo de fixação
- Aprovação do cliente

Concluídas hoje
- Liberar corte da base
```

Para cada pendência, o app pode sugerir uma próxima ação baseada no texto, na cota e no status.

Exemplos:

- “Conferir medida”.
- “Atualizar peça no CAD”.
- “Revisar DXF”.
- “Enviar para aprovação”.
- “Aguardar resposta”.
- “Liberar para fabricação”.

Na primeira versão, a sugestão pode ser feita por palavras-chave simples. Inteligência artificial pode ser avaliada depois, mas não é necessária para validar o produto.

## 6. Estrutura de dados

Cada pendência deve ter os seguintes campos:

```text
ID da pendência
Título
Descrição
Data de criação
Data e hora do lembrete
Status
Prioridade
Projeto
Peça ou equipamento
Local
Responsável
Foto original
Miniatura da foto
Lista de cotas
Áudio
Texto compartilhado
Origem da pendência
Próxima ação sugerida
Data de conclusão
```

### 6.1. Cota

Cada cota deve conter:

```text
ID da cota
ID da pendência
Posição X do primeiro ponto
Posição Y do primeiro ponto
Posição X do segundo ponto
Posição Y do segundo ponto
Valor da medida
Unidade
Texto ou observação
Cor
```

### 6.2. Status possíveis

- Aberta.
- Em andamento.
- Aguardando resposta.
- Concluída.
- Cancelada.
- Atrasada.

O status “atrasada” pode ser calculado automaticamente quando a data e hora do lembrete passam e a pendência continua aberta.

### 6.3. Prioridade

- Baixa.
- Média.
- Alta.
- Urgente.

A prioridade alta pode alterar a cor do card, a ordem na tela e o comportamento da notificação.

## 7. Telas do aplicativo

### 7.1. Tela Hoje

Objetivo: mostrar rapidamente o que precisa de atenção.

Elementos:

- Saudação e data.
- Contador de pendências atrasadas.
- Contador de pendências para hoje.
- Lista de tarefas atrasadas.
- Lista de tarefas para hoje.
- Lista de tarefas futuras.
- Botão para criar nova pendência.
- Filtro por projeto, status e prioridade.

### 7.2. Tela Nova pendência

Objetivo: registrar uma pendência em poucos passos.

Elementos:

- Botão para tirar foto.
- Botão para escolher foto.
- Botão para receber conteúdo compartilhado.
- Campo de título.
- Campo de descrição.
- Botão para gravar áudio.
- Botão para marcar cota.
- Campo de projeto.
- Campo de peça ou equipamento.
- Seleção de prioridade.
- Seleção de data e hora.
- Botão salvar.

### 7.3. Tela de edição da foto

Objetivo: marcar cotas e pontos de atenção.

Elementos:

- Foto em tela cheia.
- Botão para adicionar cota.
- Botão para adicionar texto sobre a foto.
- Botão para desfazer.
- Botão para apagar cota.
- Campo para digitar o valor da medida.
- Botão para salvar.

### 7.4. Tela de detalhe da pendência

Objetivo: mostrar todas as informações da pendência.

Elementos:

- Foto.
- Cotar marcadas.
- Texto.
- Áudio.
- Projeto.
- Peça.
- Prioridade.
- Status.
- Data e hora.
- Botão concluir.
- Botão adiar.
- Botão editar.
- Botão compartilhar no WhatsApp.
- Botão excluir.

### 7.5. Tela de lista de pendências

Objetivo: consultar, filtrar e buscar pendências.

Filtros:

- Hoje.
- Atrasadas.
- Esta semana.
- Por projeto.
- Por status.
- Por prioridade.
- Com foto.
- Com áudio.
- Concluídas.

### 7.6. Tela de configurações

Elementos:

- Ativar ou desativar notificações.
- Autorizar alarmes exatos.
- Escolher som do despertador.
- Configurar horário padrão de lembrete.
- Backup e exportação.
- Informações sobre armazenamento.
- Sobre o aplicativo.

## 8. Fluxo principal de uso

### 8.1. Registrar uma pendência com foto

1. O projetista vê uma peça, montagem ou situação que precisa de atenção.
2. Abre o app.
3. Toca em “Nova pendência”.
4. Tira uma foto ou escolhe uma imagem.
5. Toca em “Marcar cota”.
6. Seleciona dois pontos na foto.
7. Digita o valor da medida.
8. Escreve a tarefa.
9. Define o horário do lembrete.
10. Salva.
11. O app cria a pendência e agenda a notificação.

### 8.2. Receber uma pendência do WhatsApp

1. O colega envia uma foto ou mensagem pelo WhatsApp.
2. O projetista toca e segura o conteúdo.
3. Escolhe “Compartilhar”.
4. Seleciona o app de pendências.
5. O app abre uma nova pendência com o conteúdo recebido.
6. O projetista adiciona título, cota, prioridade e horário.
7. Salva a pendência.

### 8.3. Encaminhar uma pendência

1. O projetista abre uma pendência.
2. Toca em “Compartilhar”.
3. Escolhe “WhatsApp”.
4. Seleciona o contato ou grupo.
5. O WhatsApp abre com o texto e a imagem preparados.
6. O projetista envia a mensagem.

### 8.4. Receber o lembrete

1. Chega o horário programado.
2. O app mostra a notificação.
3. O projetista toca na notificação.
4. O app abre a pendência.
5. O projetista vê a foto, a cota, a anotação e o áudio.
6. Ele executa a ação ou reprograma o lembrete.

## 9. Regras de funcionamento

### 9.1. Foto

- A foto original deve ser preservada.
- O app deve criar uma versão menor para carregar mais rápido na lista.
- A cota deve ser salva como informação separada da imagem.
- A imagem original não deve ser alterada permanentemente.
- A visualização com cotas deve ser gerada na tela ou em uma cópia de exportação.

### 9.2. Cota

- A cota é uma anotação visual, não uma medição automática.
- O usuário informa o valor real.
- A cota deve poder ser editada.
- A cota deve poder ser apagada.
- A cota deve permanecer associada à pendência.
- A cota deve aparecer na foto quando a pendência for aberta.

### 9.3. Áudio

- O áudio deve ser gravado dentro do app.
- O áudio deve ficar vinculado à pendência.
- O áudio deve poder ser ouvido depois.
- O áudio deve poder ser apagado.
- A gravação deve funcionar mesmo sem internet.

### 9.4. WhatsApp

- O app deve receber conteúdo compartilhado pelo WhatsApp.
- O app não deve prometer leitura automática de conversas.
- O app deve criar um rascunho quando receber texto ou imagem.
- O app deve permitir encaminhar pendências pelo compartilhamento do Android.
- O envio deve sempre passar pela escolha do usuário no WhatsApp.

### 9.5. Notificações

- O app deve solicitar permissão de notificações.
- O app deve informar quando a permissão estiver desativada.
- O app deve permitir reprogramar o lembrete.
- O app deve permitir concluir a pendência pela notificação, se possível.
- O app deve abrir a pendência correta ao tocar na notificação.

### 9.6. Despertador

- O despertador deve ser um recurso opcional.
- O app deve verificar se o Android permite alarmes exatos.
- O app deve orientar o usuário a autorizar o recurso quando necessário.
- O app não deve fingir que o despertador funcionará se a permissão não estiver liberada.

## 10. Armazenamento local

Na primeira versão, os dados devem ficar no próprio celular.

Estrutura sugerida:

```text
PendenciaProjetista/
  database/
    pendencias.db
  fotos/
    originais/
    miniaturas/
  audios/
  exportacoes/
  backup/
```

Vantagens:

- Funciona sem internet.
- É mais simples de desenvolver.
- Mantém fotos e áudios no aparelho.
- Permite uso dentro da fábrica, mesmo em áreas com sinal ruim.

Limitações:

- Se o celular for perdido, os dados podem ser perdidos.
- Não permite acesso por outro aparelho.
- Não permite sincronização automática entre celular e computador.

A solução futura pode incluir exportação manual ou sincronização opcional.

## 11. Backup e exportação

Mesmo na primeira versão, o app deve permitir exportar dados.

Opções:

- Exportar uma pendência em PDF.
- Exportar foto com cotas.
- Exportar lista de pendências em CSV.
- Exportar backup completo.
- Compartilhar pendência em PDF pelo WhatsApp.
- Salvar pendência na galeria, quando fizer sentido.

Isso é importante porque a pendência pode precisar ser enviada para outra pessoa, arquivada ou usada como registro técnico.

## 12. Tecnologias sugeridas

Para um aplicativo Android moderno, a recomendação é usar:

- Kotlin.
- Jetpack Compose.
- Room para banco de dados local.
- CameraX para câmera.
- WorkManager ou AlarmManager para lembretes.
- NotificationManager para notificações.
- MediaRecorder para gravação de áudio.
- Android Sharesheet para compartilhar e receber conteúdo.

A escolha do Kotlin com Jetpack Compose é recomendada porque permite criar uma interface moderna, reativa e mais fácil de manter.

## 13. Permissões necessárias

O app precisará solicitar permissões apenas quando forem necessárias:

| Permissão | Uso |
|---|---|
| Câmera | Tirar foto |
| Fotos e mídia | Escolher imagem da galeria |
| Microfone | Gravar áudio |
| Notificações | Mostrar lembretes |
| Alarmes e lembretes | Criar alarmes em horário exato |
| Armazenamento | Salvar fotos, áudios e exportações |

O app deve explicar ao usuário por que cada permissão é necessária.

## 14. Etapas de desenvolvimento

### Etapa 1 — Estrutura básica

Entregar:

- Projeto Android criado.
- Tela inicial.
- Tela de nova pendência.
- Banco de dados local.
- Salvamento de título, descrição, data e status.
- Lista de pendências.

Teste:

- Criar uma pendência.
- Fechar o app.
- Reabrir o app.
- Confirmar que a pendência continua salva.

### Etapa 2 — Foto e cota

Entregar:

- Tirar foto.
- Escolher foto da galeria.
- Visualizar foto.
- Marcar dois pontos.
- Digitar valor da cota.
- Salvar cota.
- Exibir cota na foto.
- Editar e apagar cota.

Teste:

- Criar pendência com foto.
- Marcar uma cota.
- Fechar e reabrir o app.
- Confirmar que a cota continua no lugar correto.

### Etapa 3 — Lembretes

Entregar:

- Selecionar data e hora.
- Criar notificação.
- Abrir pendência pela notificação.
- Concluir pendência.
- Adiar pendência.
- Reprogramar pendência.

Teste:

- Criar pendência com aviso para dois minutos depois.
- Bloquear o celular.
- Aguardar a notificação.
- Tocar na notificação.
- Confirmar que abre a pendência correta.

### Etapa 4 — Áudio

Entregar:

- Gravar áudio.
- Parar gravação.
- Ouvir áudio.
- Apagar áudio.
- Associar áudio à pendência.

Teste:

- Gravar uma explicação de 10 segundos.
- Fechar o app.
- Reabrir a pendência.
- Ouvir o áudio.

### Etapa 5 — WhatsApp

Entregar:

- Receber texto compartilhado.
- Receber imagem compartilhada.
- Criar rascunho de pendência.
- Compartilhar texto da pendência.
- Compartilhar foto com cotas.
- Compartilhar pendência em PDF, se necessário.

Teste:

- Enviar uma foto do WhatsApp para o app.
- Verificar se o app cria o rascunho.
- Enviar uma pendência de volta para o WhatsApp.
- Confirmar se a imagem e o texto chegam corretamente.

### Etapa 6 — Orientador do dia

Entregar:

- Separação por atrasadas, hoje, amanhã e futuras.
- Filtro por projeto.
- Filtro por prioridade.
- Filtro por status.
- Sugestão de próxima ação.
- Contadores de pendências.

Teste:

- Criar pendências com prazos diferentes.
- Verificar se aparecem nos blocos corretos.
- Concluir uma pendência.
- Confirmar que ela sai da lista de pendências abertas.

### Etapa 7 — Despertador

Entregar:

- Modo despertador.
- Som mais forte.
- Tela de alarme.
- Adiar.
- Concluir.
- Verificação de permissão de alarmes exatos.

Teste:

- Criar despertador para dois minutos depois.
- Bloquear o celular.
- Verificar se o alarme toca.
- Confirmar se abre a pendência associada.

## 15. O que não fazer na primeira versão

Para evitar atraso e complexidade desnecessária, a primeira versão não deve incluir:

- Medição automática por foto.
- Reconhecimento de objetos.
- Leitura automática de todas as conversas do WhatsApp.
- Integração direta com WhatsApp Business API.
- Sincronização em nuvem.
- Login de usuários.
- Trabalho em equipe.
- Integração imediata com SolidWorks.
- Integração imediata com o `CONTROLE_PROJETO`.
- Inteligência artificial para interpretar áudio.
- Relatórios avançados.
- Versão para iPhone.

Esses recursos podem ser avaliados depois, conforme o uso real do app.

## 16. Riscos e pontos de atenção

### 16.1. Foto não mede com precisão

Uma foto pode parecer mostrar uma medida, mas a perspectiva, a distância da câmera e o ângulo podem distorcer a imagem.

Por isso, o app deve deixar claro que a cota é uma anotação feita pelo usuário, e não uma medição automática.

### 16.2. WhatsApp pode limitar o compartilhamento

O WhatsApp pode entregar textos, imagens e arquivos de formas diferentes conforme a versão do aplicativo e o tipo de conteúdo.

Por isso, o app deve ser testado com:

- Texto simples.
- Foto.
- Áudio.
- Documento.
- Várias imagens.
- Texto junto com imagem.
- Imagem encaminhada.

### 16.3. Alarmes podem ser bloqueados pelo Android

O Android pode restringir alarmes exatos por economia de bateria, permissões ou políticas do fabricante do celular.

O app deve detectar essa situação e orientar o usuário.

### 16.4. Áudio pode ocupar espaço

Áudios longos podem ocupar bastante espaço no celular.

O app deve:

- Mostrar o tamanho do áudio.
- Permitir apagar áudios antigos.
- Avisar quando o armazenamento estiver cheio.
- Não gravar automaticamente sem que o usuário solicite.

### 16.5. Dados locais podem ser perdidos

Se o app salvar tudo apenas no celular, perder o aparelho pode significar perder pendências, fotos e áudios.

A solução inicial pode ser exportação manual. Depois, pode ser avaliado backup automático ou sincronização.

## 17. Critérios de sucesso

O app será considerado útil se permitir:

- Criar uma pendência com foto em menos de 30 segundos.
- Encontrar uma pendência em menos de 10 segundos.
- Reabrir a pendência correta pelo lembrete.
- Ver a foto, a cota e a anotação juntas.
- Gravar e ouvir um áudio sem dificuldade.
- Receber uma foto do WhatsApp e transformá-la em pendência.
- Encaminhar uma pendência para o WhatsApp.
- Organizar o dia sem precisar abrir o computador.
- Reduzir esquecimentos de medidas, revisões e pendências técnicas.

## 18. Primeiro protótipo recomendado

O primeiro protótipo deve conter apenas:

- Tela Hoje.
- Nova pendência.
- Foto.
- Cota manual.
- Texto.
- Data e hora.
- Notificação.
- Detalhe da pendência.
- Concluir.
- Adiar.
- Lista de pendências.

O áudio, o WhatsApp e o despertador entram depois.

Essa ordem é importante porque o núcleo do app é:

```text
Foto + cota + tarefa + lembrete
```

Se esse fluxo funcionar bem, os demais recursos passam a ter valor.

## 19. Teste prático inicial

Antes de avançar para o desenvolvimento completo, faça este teste:

1. Escolha uma peça ou montagem real.
2. Tire uma foto.
3. Marque uma cota manualmente.
4. Escreva o que precisa ser feito.
5. Programe um lembrete para dois minutos depois.
6. Bloqueie o celular.
7. Aguarde a notificação.
8. Toque na notificação.
9. Confira se o app abre a pendência certa.
10. Veja se a foto, a cota e a anotação aparecem juntas.

Se esse fluxo funcionar de forma clara, o app já terá uma base útil para o dia a dia.

## 20. Próximo passo

O próximo passo é definir a primeira tela e o modelo de dados da pendência.

A entrega deve começar por:

```text
Tela Hoje
Tela Nova Pendência
Tela Detalhe da Pendência
Modelo de dados da pendência
Modelo de dados da cota
Fluxo de notificação
```

Depois disso, entra a câmera, a marcação de cotas e o agendamento do lembrete.
