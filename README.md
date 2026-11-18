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

O ModelCraft oferece estratégias diferentes, que não devem ser confundidas:

| Modo | Abordagem |
|---|---|
| CPU local 2.5D | Preserva a vista frontal e cria relevo/extrusão. Não recupera o volume real nem as faces ocultas. |
| Modelado ONNX | Reconstrução volumétrica baseada em TripoSR via ONNX Runtime FP32 em CPU. |
| Multivista | Usa silhuetas de fotografias de ângulos diferentes para construir uma geometria aproximada. |

Uma única fotografia não contém dados suficientes para revelar o verso, cavidades ocultas ou dimensões físicas exatas. Nessas regiões, o motor precisa estimar ou sintetizar informação. Sempre inspecione a geometria, as texturas e as partes ocultas antes de usar o asset em produção.

## Instalação — versão 0.1.0

A distribuição Windows é fornecida em dois instaladores separados na página de Releases:

1. **ModelCraft Software** — instala o aplicativo desktop e seu runtime.
2. **ModelCraft Models** — instala os motores e pesos de IA a partir do pacote de modelos distribuído junto à versão.

### Passos

1. Baixe os arquivos da versão **ModelCraft 0.1.0** na página de [Releases](https://github.com/IGOR-SciDATA/modelcraft/releases).
2. Extraia o pacote de modelos completo para uma pasta local. Não execute os instaladores de dentro do ZIP.
3. Execute `ModelCraft-Software-Setup-0.1.0-x64.msi`.
4. Mantenha a pasta `payload_models` ao lado de `ModelCraft-Models-Setup-0.1.0-x64.msi` e execute esse segundo instalador.
5. Aguarde a cópia dos motores e pesos terminar e abra o ModelCraft pelo atalho criado.

**Requisitos importantes**
- Windows 64-bit.
- A pasta de modelos ocupa aproximadamente **11,44 GB**; reserve espaço adicional para a cópia durante a instalação.
- O Blender não está incluído. Instale-o separadamente caso pretenda utilizar os recursos que dependem dele.
- O pacote 0.1.0 inclui os hashes SHA-256 para conferência dos instaladores.

Consulte o arquivo `LEIA-ME-INSTALACAO.txt` incluído na distribuição para os detalhes de instalação.

## Licenças e modelos

O software integra componentes e modelos de terceiros, cada um com suas próprias condições de licença. Consulte os avisos e arquivos de licença incluídos na distribuição e nos projetos de origem antes de redistribuir ou utilizar componentes individualmente.

## Aviso sobre resultados

A qualidade de um modelo depende da fotografia, do objeto, do motor selecionado e dos dados observados. Uma malha fechada (*watertight*) não significa necessariamente que a geometria seja fiel. Textura de alta resolução também não aumenta, por si só, a resolução da malha.

---

<div align="center">
  <strong>ModelCraft 0.1.0</strong><br />
  <sub>Imagem → Geometria → Asset 3D</sub>
</div>
