<div align="center">
  <img src="imagens/logo.png" alt="ModelCraft" width="180" />
  <h1>ModelCraft</h1>
  <p><strong>Transforme imagens em assets 3D — localmente, com controle sobre o seu fluxo.</strong></p>
  <p>
    <a href="https://github.com/IGOR-SciDATA/modelcraft/releases">Downloads</a> ·
    <a href="https://github.com/IGOR-SciDATA/modelcraft/issues">Reportar problema</a>
  </p>
  <p>
    <img src="https://img.shields.io/badge/vers%C3%A3o-0.1.0-8B5CF6?style=for-the-badge" alt="Versão 0.1.0" />
    <img src="https://img.shields.io/badge/plataforma-Windows%2064--bit-2563EB?style=for-the-badge" alt="Windows 64-bit" />
    <img src="https://img.shields.io/badge/processamento-CPU%20local-0EA5E9?style=for-the-badge" alt="CPU local" />
  </p>
</div>

---

## Visão geral

**ModelCraft** é um aplicativo desktop para transformar fotografias em modelos e assets 3D. O projeto reúne motores de reconstrução, processamento de imagem, ferramentas de geometria e visualização em um único fluxo de trabalho para Windows.

A proposta é permitir que o usuário trabalhe com processamento local, sem depender de créditos por geração ou de uma GPU dedicada para os fluxos compatíveis com CPU.

<div align="center">
  <img src="imagens/ModelCraft-Preview.png" alt="ModelCraft aberto no Windows" width="900" />
  <sub>Interface do ModelCraft 0.1.0</sub>
</div>

## O que oferece

- **Geração a partir de imagem:** fluxo de entrada de uma fotografia e geração de asset 3D.
- **Processamento local em CPU:** motores ONNX para execução local, sem exigir CUDA.
- **Pré-processamento:** remoção de fundo e preparação da imagem.
- **Mais de uma estratégia:** geração procedural 2.5D e reconstrução volumétrica por IA, cada uma com suas características.
- **Fluxo multivista:** possibilidade de fornecer fotografias adicionais (frente, laterais, topo e traseira) para apoiar a reconstrução.
- **Visualizador 3D:** inspeção dos resultados e exportação em formatos como GLB, GLTF e OBJ.
- **Refinamento:** ferramentas para limpeza, remeshing e ajustes de malha, com preservação do arquivo original.

## Como funciona

O ModelCraft hoje ainda está em versão de testes:

| Modo | Abordagem |
|---|---|
| TESTE | Apenas alguns usuários selecionados, a fim de melhorarmos antes do release oficial |
| SOLICITAR | Caso tenha interesse em participar do beta fechado, só entrar em contato através do perfil. |

## Instalação — versão 0.1.0

Os instaladores Windows x64 estão publicados na página de [Releases](https://github.com/IGOR-SciDATA/modelcraft/releases/tag/v0.1.0):

- **ModelCraft Software** — instala o aplicativo desktop e o runtime.
- **ModelCraft Models** — instalador auxiliar dos motores e pesos de IA.

> **Atenção — pacote de modelos ainda não disponível nesta Release.** O instalador ModelCraft Models precisa da pasta `payload_models` (aproximadamente 11,44 GB) ao lado do MSI. Essa pasta não foi anexada à Release porque o envio dos volumes grandes não foi confirmado pelo GitHub. Portanto, por enquanto, instale apenas o MSI do software. Não execute o MSI ModelCraft Models sem o pacote completo.

Quando o pacote completo de modelos estiver disponível, a instalação seguirá estes passos:

1. Baixe todos os volumes do pacote de modelos para a mesma pasta.
2. Extraia o volume inicial com 7-Zip para reconstruir a pasta `payload_models`.
3. Execute `ModelCraft-Software-Setup-0.1.0-x64.msi`.
4. Mantenha `payload_models` ao lado de `ModelCraft-Models-Setup-0.1.0-x64.msi` e execute esse segundo instalador.
5. Aguarde a cópia dos motores e pesos terminar e abra o ModelCraft pelo atalho criado.

**Requisitos importantes**
- Windows 64-bit.
- A pasta de modelos ocupa aproximadamente **11,44 GB**; reserve espaço adicional para a cópia durante a instalação.
- O Blender não está incluído. Instale-o separadamente caso pretenda utilizar os recursos que dependem dele.
- Os hashes SHA-256 dos dois instaladores estão disponíveis na Release.

Consulte o arquivo `LEIA-ME-INSTALACAO.txt` incluído nos assets da Release.

## Licenças e modelos

O software integra componentes e modelos de terceiros, cada um com suas próprias condições de licença. Consulte os avisos e arquivos de licença incluídos na distribuição e nos projetos de origem antes de redistribuir ou utilizar componentes individualmente.

## Aviso sobre resultados

A qualidade de um modelo depende da fotografia, do objeto, do motor selecionado e dos dados observados. Uma malha fechada (*watertight*) não significa necessariamente que a geometria seja fiel. Textura de alta resolução também não aumenta, por si só, a resolução da malha.

---

<div align="center">
  <strong>ModelCraft 0.1.0</strong><br />
  <sub>Imagem → Geometria → Asset 3D</sub>
</div>
