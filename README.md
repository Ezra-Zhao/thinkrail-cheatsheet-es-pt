# ThinkRail 速查表 | ThinkRail Cheatsheet | Guía rápida de ThinkRail

> 一页看懂 ThinkRail：JetBrains 孵化器出的开源 agent IDE——给极简编程 agent pi 套上一个真 IDE（Monaco 编辑器、文件树、终端、PR/CI 面板），每个项目按 git worktree 切隔离工作区让多个 agent 并行干活不打架，项目知识存成互相链接的 SPEC.md 活规格图、跨会话不丢。（本页以葡语为重点：ThinkRail 界面内置英/日/俄/简中/西五种语言，偏偏没有葡语。）

- 上游项目：[JetBrains/thinkrail](https://github.com/JetBrains/thinkrail)（2026-10-30 实测 6,430 ★ / 350 forks，124 个 release）
- 平台：桌面版（macOS / Windows / Linux）+ CLI
- 本页结构：中文主文 → English → Español → Português

---

Apoyo y más: [GitHub Sponsors](https://github.com/sponsors/Ezra-Zhao) · [Gumroad — plantillas y cuadernos que uso](https://ezraflow28.gumroad.com) · [Ko-fi](https://ko-fi.com/ezra777zhao)

## 它和普通 IDE 的区别

| 部件 | 说明 |
|---|---|
| agent 内核 | 底层 agent 是极简的 pi，ThinkRail 给它套上完整的 IDE 外壳 |
| 真 IDE 界面 | Monaco 编辑器、文件树、集成终端、PR/CI 面板——不是聊天框加个文件列表 |
| Worktree 工作区 | 每个项目按 git worktree 切出隔离工作区，多个 agent 并行改代码互不干扰 |
| SPEC.md 活规格 | 项目知识存成互相链接的 SPEC.md 规格图，跨会话保留，agent 和你看的是同一份「项目记忆」 |
| Agent Skills 兼容 | 能直接读你现成的 Agent Skills，不用为它重写一遍 |

## 两种装法

| 装法 | 适合谁 | 注意 |
|---|---|---|
| 桌面版 | 想要完整 IDE 体验 | 三平台去官网/GitHub Releases 下对应安装包；Linux 需 Ubuntu 24.04+ 并装齐 GTK 相关依赖，老发行版先别折腾 |
| CLI | 只想在终端里用它的工作区/agent 能力 | 一行脚本安装（命令见上游 README），不需要图形界面 |

**怎么选**：日常主力开发、要看 PR/CI 面板 → 桌面版；远程服务器、轻量试水、已有顺手的编辑器 → CLI 先行。

## 工作区模型一图流

项目 → 按任务开 worktree 工作区（每个 agent 一个） → 各自干活、互不污染 → **合并好的那个分支，其余删掉** → PR 合并后工作区自动归架（archived），项目保持干净。

要点：worktree 是隔离手段不是收藏品——胜利者合并完，落选工作区立刻清，别让仓库里堆一排没人认领的分支。

## 模型接入

| 方式 | 说明 |
|---|---|
| JetBrains AI 登录 | 用 JetBrains 账号登录，模型走 JetBrains AI 的额度与规则 |
| 接自己的供应商 | 通过 pi 接你自己的模型供应商与 key（OpenAI / Anthropic / 本地模型等以 pi 的支持面为准） |

ThinkRail 自己**没有账号体系**，也不卖模型额度：它只管 IDE 与工作区，模型账单永远是你和供应商之间的事。

## 诚实标注区

- **仍处早期阶段**：官方文档多处写着「即将推出」，功能面在快速变化，拿它当唯一生产环境前先小项目试水。
- **应用免费开源≠使用免费**：IDE 本身不要钱，但每次模型调用照常向你的供应商付费，跑并行 agent 前先想好预算。
- **葡语用户被官方漏掉了**：UI 内置语言有英/日/俄/简中/西，唯独没有葡语——这也是本页葡语版存在的理由。

---

## English (summary)

ThinkRail (from the JetBrains incubator, ~6,430 stars and 124 releases as of 2026-10-30) is an open-source agent IDE: it wraps the minimal coding agent pi in a real IDE — Monaco editor, file tree, terminal, PR/CI panels — isolates each project into git-worktree workspaces so multiple agents can work in parallel without collisions, and stores project knowledge as a cross-linked graph of SPEC.md living specs that survives across sessions. It reads your existing Agent Skills as-is.

Install it as a desktop app (macOS/Windows/Linux — Linux needs Ubuntu 24.04+ and its GTK dependencies) or via the one-line CLI script. Workspaces follow a simple lifecycle: branch one worktree per task, merge the winner, delete the rest, and the workspace auto-archives once the PR merges. There is no ThinkRail account system: sign in with JetBrains AI or bring your own provider keys through pi — model bills are always between you and your provider.

Honest notes: the project is young and parts of its docs still say "coming soon"; the IDE is free and open source, but model calls are not free. Its UI ships in English, Japanese, Russian, Simplified Chinese and Spanish — Portuguese is missing, which is exactly why this page leads with it.

---

## Español (guía rápida — traducción de estudio, pendiente de revisión por un hablante nativo)

ThinkRail (de la incubadora de JetBrains, ~6.430 estrellas y 124 versiones en octubre de 2026) es un IDE de agentes de código abierto: envuelve al agente minimalista pi en un IDE de verdad — editor Monaco, árbol de archivos, terminal, paneles de PR/CI —, separa cada proyecto en workspaces con git worktree para que varios agentes trabajen en paralelo sin pisarse, y guarda el conocimiento del proyecto como un grafo de especificaciones vivas en archivos SPEC.md enlazados, que sobrevive entre sesiones. Además lee tus Agent Skills existentes tal cual.

**Instalación**: app de escritorio (macOS/Windows/Linux; en Linux pide Ubuntu 24.04+ y dependencias GTK) o el script de una línea de la CLI. Escritorio si quieres la experiencia IDE completa; CLI para servidores o para probar ligero.

**Modelo de workspaces**: un worktree por tarea → cada agente trabaja aislado → se fusiona la rama ganadora y se borran las demás → al fusionarse el PR, el workspace se archiva solo.

**Modelos**: ThinkRail no tiene sistema de cuentas propio. Entras con JetBrains AI o conectas tus propios proveedores y claves a través de pi; la factura del modelo siempre es entre tú y tu proveedor.

**Notas honestas**: el proyecto es joven y parte de su documentación aún dice «próximamente»; el IDE es gratis y abierto, pero las llamadas al modelo se pagan como siempre.

---

## Português (guia rápido — tradução de estudo, aguardando revisão de um falante nativo)

O ThinkRail (da incubadora da JetBrains, ~6.430 estrelas e 124 releases em outubro de 2026) é um IDE de agentes open source: ele envolve o agente minimalista pi num IDE de verdade — editor Monaco, árvore de arquivos, terminal, painéis de PR/CI —, separa cada projeto em workspaces com git worktree para vários agentes trabalharem em paralelo sem se atropelar, e guarda o conhecimento do projeto como um grafo de especificações vivas em arquivos SPEC.md interligados, que sobrevive entre sessões. E ele lê os seus Agent Skills atuais sem você precisar reescrever nada.

**Instalação**: aplicativo desktop (macOS/Windows/Linux; no Linux pede Ubuntu 24.04+ e as dependências GTK) ou o script de uma linha da CLI. Desktop se você quer a experiência completa de IDE; CLI para servidores ou para testar leve.

**Modelo de workspaces**: um worktree por tarefa → cada agente trabalha isolado → faz merge do branch vencedor e apaga os demais → quando o PR é mergeado, o workspace é arquivado sozinho.

**Modelos**: o ThinkRail não tem sistema de contas próprio. Você entra com o JetBrains AI ou conecta os seus próprios provedores e chaves através do pi; a conta do modelo é sempre entre você e o seu provedor.

**A nota que importa para o Brasil**: a interface do ThinkRail tem inglês, japonês, russo, chinês simplificado e espanhol — **português ficou de fora**. É por isso que este guia existe: instalação, modelo de workspaces e conexão de modelos, tudo numa página só, na sua língua.

**Notas honestas**: o projeto é jovem e parte da documentação ainda diz "em breve"; o IDE é grátis e aberto, mas as chamadas ao modelo custam o de sempre.

---

## 来源与声明

- 灵感来源 / Source / Fuente / Fonte: [JetBrains/thinkrail](https://github.com/JetBrains/thinkrail)
- 本仓是个人学习整理：内容用我自己的话总结自上游公开文档，不搬运原文；安装与功能细节以 2026-10-30 的上游 README 与官方文档为准，上游迭代很快，请以官方 changelog 为最终依据。
- 西语、葡语部分为学习译稿，待母语校对。Las secciones en español y portugués son traducciones de estudio pendientes de revisión nativa.
- License: MIT © 2026 Guangyi Zhao
