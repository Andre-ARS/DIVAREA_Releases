<p align="center">
  <img src="assets/divarea_icon.png" alt="DIVAREA" width="128">
</p>

<h1 align="center">DIVAREA</h1>
<p align="center"><strong>Divida terrenos em lotes no AutoCAD.</strong></p>
<p align="center">Prepare lotes, confira a prévia e acrescente números e áreas ao desenho.</p>
<p align="center">Versão 1.8.0</p>

A DIVAREA é uma ferramenta para AutoCAD 2022 completo no Windows que divide um contorno fechado em lotes. Direção mantém áreas iguais na região; Formato mantém igualdade dentro de cada zona natural, permitindo tamanhos diferentes entre zonas. O trabalho acontece no próprio desenho, com prévia antes da criação e preservação do contorno original.

## Do contorno aos lotes

1. Execute **DIVAREA** e selecione uma polilinha fechada com segmentos retos ou arcos.
2. Escolha se deseja criar estrada interna. Sem estrada, escolha o modo Direção ou Formato.
3. Depois do modo, informe a **área mínima desejada dos lotes em m²**, ou pressione **Enter para seguir sem mínimo**. Com estrada interna, essa pergunta vem somente depois de configurar e confirmar a estrada.
4. Com área informada, a pergunta da quantidade mostra essa área mínima e o número sugerido como resposta padrão. **Enter confirma a sugestão**, digitar outro número permite escolher menos lotes e **Esc cancela**. A identificação de lado aparece somente na estrada interna. O programa só calcula as divisões depois dessa escolha. Sem referência de área, informe a quantidade diretamente.
5. Configure frente mínima opcional, direção e linhas ou colunas. A quantidade escolhida será validada geometricamente, respeitando a área informada quando houver.
6. Confira a prévia colorida. Ajuste a proposta, confirme a criação ou saia sem criar os lotes.
7. Depois de criar, escolha se deseja inserir numeração, tamanho das áreas ou ambos.

## Divisão e conferência

- Cada lote é uma polilinha fechada e conectada e respeita a área mínima quando informada. Em Direção, a igualdade vale na região dividida. No Formato, vale dentro de cada zona natural; as áreas podem diferir entre zonas e entre lados da estrada.
- Os trechos curvos do contorno são preservados como arcos nos lotes finais.
- O contorno original e os objetos que já estavam no desenho são preservados.
- A distribuição por formato permite ajustar a direção de um setor ou reorganizar a separação entre setores.
- A divisão pode ser desfeita com **UNDO**. Cancelar a prévia remove os objetos temporários sem criar lotes definitivos.

A distribuição por formato usa uma busca geométrica e pode não encontrar uma solução para certos contornos. Confira a disposição e os acessos antes de confirmar; a ferramenta não substitui a análise de um projeto de parcelamento.

## Estrada interna

Marque dois lados do terreno, **A e B**, para entrada e saída da estrada. O centro da estrada fica no ponto médio de cada lado por padrão, medido pelo comprimento real, inclusive em lados curvos. É possível indicar outro ponto em um lado ou nos dois.

Informe a largura total em metros. O programa propõe um percurso que acompanha o terreno, com curvas suaves e largura constante, evitando desvios curtos desnecessários junto à entrada e à saída. As bordas curvas são arcos reais. Os pontos escolhidos são mantidos; a estrada não é estreitada automaticamente.

Antes de calcular, é possível indicar obstáculos por polilinhas fechadas ou por pontos, como casas e lagos. Para um rio, selecione uma linha ou polilinha aberta de uma margem e clique do lado da água. As pontas da margem são prolongadas pelas tangentes e o lado indicado fica impedido para a estrada.

Escolha um afastamento positivo em metros para todos os obstáculos; **Enter usa 5 m**. A medida parte da borda da estrada. As referências aparecem em vermelho e são preservadas. Ao ajustar, mantenha, substitua ou remova os obstáculos e reveja a distância, com o valor anterior oferecido por padrão. O afastamento é uma configuração do projeto; o programa não faz enquadramento normativo. Obstáculos restringem o percurso, sem retirar área dos lotes.

Confira a estrada na prévia e ajuste os lados, centros ou largura quando necessário. O traçado precisa deixar exatamente duas regiões fechadas e conectadas. Gargalos, cruzamentos ou curvas que impeçam a largura ou o afastamento exigidos são recusados. A busca é geométrica e pode não encontrar uma proposta para certos terrenos.

Depois de configurar e confirmar a estrada, informe a área mínima desejada opcional uma única vez para os dois lados. A área da estrada é descontada antes de sugerir quantidades. Para cada lado, confirme a sugestão por área ou escolha menos lotes **antes do cálculo da divisão**. Sem área informada, digite as quantidades diretamente. Um lote mantém a região inteira no modo Direção; no Formato, a quantidade precisa atender às zonas e faixas escolhidas. A referência de tamanho não exige lotes exatamente daquele tamanho: a sobra é distribuída conforme a regra de igualdade do modo, e escolher menos lotes os deixa maiores.

Se as medidas não permitirem a divisão de um lado, o programa oferece alternativas para rever direção, distribuição ou quantidade. Com frente mínima, permite editar ou retirar a exigência e apresenta uma frente viável quando encontra uma proposta completa com a mesma quantidade de lotes e área mínima. O valor sugerido é conferido em cada lote, inclusive em bordas curvas. Mudanças dependem da escolha do usuário.

As tentativas no lado 2 mantêm a estrada e a configuração válida do lado 1. Uma tentativa inviável retorna ao menu; cancelar encerra sem criar entidades. A busca de alternativas é geométrica e pode não encontrar todas as soluções possíveis.

A prévia acompanha zoom e deslocamento da vista. Os objetos temporários são removidos ao ajustar, cancelar ou criar; estrada e lotes definitivos só são montados após confirmar. Confira estrada e lotes juntos antes de criar. A operação cria uma polilinha da estrada e os lotes dos dois lados, preservando o contorno original. **UNDO** desfaz a geometria em conjunto.

## Frente mínima e múltiplas faixas

Sem estrada interna, a frente mínima é medida ao longo de um segmento reto ou curvo do contorno escolhido como estrada. Com estrada interna, é medida ao longo da borda gerada que atende cada lado. Quando a exigência é ativada, cada lote precisa atendê-la.

No fluxo sem estrada interna, com duas faixas, selecione dois lados distintos para representar as estradas. Mais de duas faixas estão disponíveis sem a exigência de frente mínima; o acesso viário dessas distribuições não é planejado automaticamente.

O número informado é sempre o total de lotes. No Formato, a sugestão soma as capacidades das zonas naturais; os limites das zonas acompanham a geometria, sem faixas de compensação. As colunas mantêm a orientação de cada zona. Dentro de uma zona, dez lotes em duas faixas são distribuídos em cinco e cinco; onze lotes são distribuídos em seis e cinco, mantendo áreas iguais por lote naquela zona.

## Numeração e textos de área

Depois da criação, é possível inserir somente números, somente áreas ou ambos. A numeração permite escolher o primeiro número e o percurso **Serpentina**, **Alternar colunas** ou **Direto**. Serpentina percorre cada trecho inteiro e continua pelo extremo mais próximo do próximo grupo, acompanhando mudanças de orientação e os dois lados da estrada. Em grades paralelas, mantém o zig-zag. Alternar colunas numera um lote de cada coluna por vez e continua pelas colunas restantes quando suas quantidades diferem.

Os textos ficam centralizados nos lotes, com altura padrão de **1** e alinhamento padrão para o norte do desenho. Também é possível indicar outra direção por dois pontos e escolher números vermelhos ou com a cor da camada.

Com estrada interna, a configuração e a prévia dos textos são únicas para os dois lados, com sequência contínua e área real de cada lote. A estrada fica fora da numeração. A prévia dos textos permite ajustar, confirmar ou cancelar sem remover a estrada e os lotes já criados. Somente os lotes daquela execução recebem textos. Os textos são estáticos: alterações posteriores na geometria não atualizam os valores automaticamente.

## Instalação e atualizações

Os instaladores e os arquivos de verificação são disponibilizados na seção **Releases** deste repositório. O executável usa o mesmo ícone da DIVAREA apresentado no topo desta página.

1. Feche todas as janelas do AutoCAD.
2. Na versão desejada em **Releases**, baixe **Instalar_DIVAREA.exe**. O arquivo **Instalar_DIVAREA.exe.sha256** permite conferir a integridade do download.
3. Execute o instalador. Não é necessário instalar Python, baixar arquivos separados ou executar como administrador.
4. Reabra o AutoCAD 2022 e confira a mensagem de versão e a disponibilidade de **DIVAREA**, sem carregar a rotina manualmente.
5. Abra outro desenho e confira novamente o comando.

A instalação usa o pacote **DIVAREA.bundle** na pasta de plugins do usuário. Para atualizar, feche o AutoCAD, execute o instalador mais recente e reabra o programa. Arquivos diferentes são preservados em backups antes da substituição.

Se o AutoCAD bloquear o carregamento, confira a origem do instalador e as configurações de carregamento de aplicativos e locais confiáveis. Quando necessário, cadastre somente a subpasta **Contents** do pacote nos locais confiáveis, preservando as demais entradas e as proteções do programa. Em ambientes administrados, consulte o responsável pela configuração.

## Requisitos e unidades

- AutoCAD 2022 completo no Windows de 64 bits. AutoCAD LT 2022 não executa esta ferramenta.
- Contorno formado por uma polilinha fechada simples, sem furos, cruzamentos ou lados sobrepostos, paralela ao plano XY do WCS, com normal +Z.
- Geometria desenhada em metros: uma unidade de coordenada equivale a **um metro**, independentemente de INSUNITS. Converta desenhos em outras escalas antes de usar a ferramenta.
- Camada atual visível e desbloqueada para criar os lotes.

As áreas são apresentadas em **m²**, com ponto para milhares, vírgula decimal e duas casas. A escolha de outra unidade na entrada da frente mínima converte somente a medida digitada, sem alterar a escala do desenho.

## Suporte

Para relatar um problema ou sugerir uma melhoria, use a seção **Issues** deste repositório.

Informe a versão da DIVAREA, a edição do AutoCAD e do Windows e os passos para reproduzir o problema. Ao compartilhar imagens ou desenhos, use exemplos sem dados pessoais ou confidenciais.
