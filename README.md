# xfce4-panel-modificado

Customização do **xfce4-panel 4.18.4** para Linux/XFCE, baseada no código-fonte original do projeto XFCE.

Este repositório mantém uma versão modificada do painel para uso pessoal, backup e documentação das alterações realizadas.
(planejo fazer mais modificações no futuro)

## Modificação principal

Foi implementada uma animação suave para o comportamento de ocultação/mostração automática do painel.

A modificação inclui:

* animação suave ao revelar o painel;
* animação reversa quando o cursor deixa a região do painel;
* easing cúbico para suavizar o movimento;
* funcionamento em múltiplos monitores;
* correções relacionadas à posição e geometria do painel durante a animação;
* atualização da área de captura após o painel voltar ao estado oculto.

A implementação foi feita diretamente em:

```text
panel/panel-window.c
```

## Base do projeto

Este trabalho é baseado no **xfce4-panel 4.18.4** do projeto XFCE.

Não reivindico autoria do código original do XFCE. Os créditos, direitos autorais e licença do projeto original permanecem pertencentes aos respectivos autores e contribuidores.

Este repositório contém apenas as modificações realizadas sobre essa base.

## Estrutura

```text
panel/panel-window.c
patches/smooth-autohide.patch
config/xfce4-panel-custom.desktop
README.md
```

### `panel/panel-window.c`

Versão modificada do arquivo principal responsável pelo comportamento da janela do painel.

### `patches/smooth-autohide.patch`

Patch contendo as alterações realizadas em relação à versão original utilizada como base.

### `config/xfce4-panel-custom.desktop`

Arquivo de autostart utilizado para iniciar a versão personalizada do `xfce4-panel`.

## Compilação

O projeto pode ser compilado a partir do código-fonte utilizando o processo padrão do xfce4-panel.

Exemplo:

```bash
./autogen.sh --prefix=/usr/local
make -j$(nproc)
sudo make install
```

Depois da instalação, o binário personalizado pode ser encontrado em:

```text
/usr/local/bin/xfce4-panel
```

## Autostart

O arquivo:

```text
config/xfce4-panel-custom.desktop
```

pode ser utilizado para iniciar automaticamente a versão personalizada durante o login do XFCE.

## Patch

Para visualizar as diferenças em relação à versão original:

```bash
git diff
```

O patch completo também está disponível em:

```text
patches/smooth-autohide.patch
```

## Assistência de IA

Parte significativa do processo de análise, depuração, investigação do código e desenvolvimento das modificações contou com **assistência de inteligência artificial**.

A IA foi utilizada como ferramenta de apoio para:

* analisar o código-fonte do XFCE;
* investigar o comportamento do autohide;
* analisar erros e comportamentos inesperados;
* auxiliar na depuração;
* revisar partes da implementação.

As alterações foram testadas e ajustadas no ambiente local antes de serem mantidas neste repositório.

## Objetivo

O objetivo deste repositório é principalmente:

* manter um backup das modificações;
* documentar o desenvolvimento da customização;
* facilitar a reprodução da configuração;
* registrar as alterações feitas sobre o código original.

Este não é um fork oficial do projeto XFCE nem pretende representar uma versão oficial do `xfce4-panel`.

## Licença

O código original segue a licença aplicável ao projeto **xfce4-panel/XFCE**.

As modificações deste repositório devem ser utilizadas respeitando os termos da licença do projeto original e os direitos dos autores e contribuidores.
