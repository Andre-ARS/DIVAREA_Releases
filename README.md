<h1 align="center">DIVAREA</h1>
<p align="center"><strong>Divida terrenos em áreas iguais no AutoCAD.</strong></p>
<p align="center">Prepare lotes, confira a prévia e acrescente números e áreas ao desenho.</p>

A DIVAREA é uma ferramenta para AutoCAD 2022 completo no Windows que divide um contorno fechado em lotes de áreas iguais. O trabalho acontece no próprio desenho, com prévia antes da criação e preservação do contorno original.

## Do contorno aos lotes

1. Execute **DIVAREA** e selecione uma polilinha fechada com segmentos retos ou arcos.
2. Informe o número total de lotes e escolha se deseja exigir frente mínima para estrada.
3. Escolha uma direção de divisão ou a distribuição por formato, que propõe setores com direções locais.
4. Se necessário, ative múltiplas linhas ou colunas.
5. Confira a prévia colorida. Ajuste a proposta, confirme a criação ou saia sem criar os lotes.
6. Depois de criar, escolha se deseja inserir numeração, tamanho das áreas ou ambos.

## Divisão e conferência

- Cada lote é uma polilinha fechada e conectada, com área igual à dos demais lotes.
- Os trechos curvos do contorno são preservados como arcos nos lotes finais.
- O contorno original e os objetos que já estavam no desenho são preservados.
- A distribuição por formato permite ajustar a direção de um setor ou reorganizar a separação entre setores.
- A divisão pode ser desfeita com **UNDO**. Cancelar a prévia de áreas não cria lotes.

A distribuição por formato usa uma busca geométrica e pode não encontrar uma solução para certos contornos. Confira a disposição e os acessos antes de confirmar; a ferramenta não substitui a análise de um projeto de parcelamento.

## Frente mínima e múltiplas faixas

A frente mínima é medida ao longo de um segmento reto ou curvo do contorno escolhido como estrada. Quando a exigência é ativada, cada lote precisa atendê-la.

Com duas faixas, selecione dois lados distintos para representar as estradas. Mais de duas faixas estão disponíveis sem a exigência de frente mínima; o acesso viário dessas distribuições não é planejado automaticamente.

O número informado é sempre o total de lotes. Por exemplo, dez lotes em duas faixas são distribuídos em cinco e cinco; onze lotes são distribuídos em seis e cinco, mantendo áreas iguais por lote.

## Numeração e textos de área

Depois da criação, é possível inserir somente números, somente áreas ou ambos. A numeração permite escolher o primeiro número e o percurso direto ou em serpentina entre colunas.

Os textos ficam centralizados nos lotes, com altura padrão de **1** e alinhamento padrão para o norte do desenho. Também é possível indicar outra direção por dois pontos e escolher números vermelhos ou com a cor da camada.

A prévia dos textos permite ajustar, confirmar ou cancelar sem remover os lotes já criados. Somente os lotes daquela execução recebem textos. Os textos são estáticos: alterações posteriores na geometria não atualizam os valores automaticamente.

## Instalação e atualizações

Os instaladores e os arquivos de verificação são disponibilizados na seção **Releases** deste repositório.

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
