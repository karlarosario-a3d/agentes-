---
inclusion: manual
---
<!------------------------------------------------------------------------------------
   Add rules to this file or a short description and have Kiro refine them for you.
   
   Learn about inclusion modes: https://kiro.dev/docs/steering/#inclusion-modes
-------------------------------------------------------------------------------------> 
## inclusion: manual

# A3Data Design System Steering

Use este steering quando a tarefa envolver criação, revisão ou atualização de interface, design system, documentação visual, componentes, dashboards, DataViz ou implementação de UI alinhada à identidade da A3Data.

## Fonte de verdade

A fonte principal de design deste workspace é:

```text
a3-design/DESIGN.md
```

Antes de sugerir ou implementar qualquer UI, leia primeiro:

```text
a3-design/DESIGN.md
```

Depois, quando necessário, consulte:

```text
a3-design/tokens/colors.json
a3-design/tokens/typography.json
a3-design/tokens/spacing.json
a3-design/tokens/components.json
a3-design/docs/ai-implementation-rules.md
a3-design/docs/component-guidelines.md
a3-design/docs/data-visualization-guidelines.md
a3-design/docs/brand-guidelines.md
```

Use `a3-design/raw/` apenas para auditoria, validação ou rastreabilidade. Não use os arquivos brutos como fonte principal de implementação.

## Regras principais

* Sempre respeitar os tokens definidos em `a3-design/`.
* Não inventar cores, fontes, espaçamentos, componentes ou padrões visuais.
* Não criar cores avulsas no código sem justificar.
* Não alterar identidade visual sem registrar motivo.
* Quando encontrar `needs-review`, não assumir como final.
* Se houver divergência entre Figma, `a3-design/` e código existente, reporte a divergência antes de alterar implementação.
* Reutilizar componentes existentes do projeto antes de criar novos.
* Priorizar clareza, consistência, acessibilidade e baixa poluição visual.
* Para dashboards e telas analíticas, seguir `a3-design/docs/data-visualization-guidelines.md`.

## Escopo permitido

Quando este steering for usado para implementação de UI, pode ler:

```text
a3-design/
src/
frontend/
components/
app/
pages/
```

Mas só deve alterar arquivos de código se a tarefa pedir explicitamente implementação.

Quando a tarefa for apenas documentação de design, alterar somente:

```text
a3-design/
```

## Arquivos que não devem ser alterados sem confirmação

Não alterar sem confirmação explícita:

```text
package.json
package-lock.json
pnpm-lock.yaml
bun.lock
tailwind.config.*
vite.config.*
tsconfig.*
.env
.env.*
```

Nunca criar ou modificar arquivos contendo segredos.

## Uso do Figma

A documentação `a3-design/` já foi gerada a partir do manual de identidade da A3Data no Figma.

Fonte original:

```text
File key: LmV1BuT3zPufCKMOoCsbiM
Node ID: 2:21
Fonte: Manual de Identidade A3Data
Método usado: Figma REST API
```

Não consultar novamente a API do Figma por padrão.

Só usar a Figma REST API quando a tarefa pedir atualização, auditoria ou sincronização do manual.

Se a API do Figma for usada:

* Ler o token apenas da variável de ambiente `FIGMA_TOKEN`.
* Nunca exibir o token.
* Nunca salvar o token em arquivo.
* Nunca commitar o token.
* Registrar endpoints e limitações em `a3-design/docs/figma-audit.md`.

## Regras para implementação de UI

Ao criar ou revisar telas:

1. Leia `a3-design/DESIGN.md`.
2. Consulte os tokens JSON necessários.
3. Verifique se já existem componentes equivalentes no projeto.
4. Aplique cores, tipografia e spacing do design system.
5. Garanta estados de interface:

   * loading;
   * error;
   * empty;
   * success;
   * disabled;
   * focus;
   * hover.
6. Garanta acessibilidade:

   * contraste;
   * foco visível;
   * textos legíveis;
   * navegação por teclado quando aplicável;
   * uso de cor acompanhado de texto/ícone em estados importantes.
7. Para dashboards, priorize:

   * clareza;
   * hierarquia visual;
   * tooltips em vez de excesso de labels;
   * cores semânticas consistentes;
   * redução de poluição visual;
   * boa leitura de KPIs, tabelas e gráficos.

## Regras para documentação

Quando atualizar `a3-design/`:

* Manter `DESIGN.md` como arquivo principal e autossuficiente.
* Manter tokens estruturados em `tokens/*.json`.
* Manter evidências brutas em `raw/`.
* Não excluir arquivos brutos sem confirmação humana.
* Atualizar `docs/figma-audit.md` quando houver nova extração.
* Marcar como `needs-review` qualquer dado incompleto, ambíguo ou contraditório.

## Resposta esperada ao final de tarefas com este steering

Ao concluir, responder com:

1. O que foi lido em `a3-design/`.
2. O que foi criado, alterado ou preservado.
3. Quais tokens ou diretrizes foram aplicados.
4. Quais itens ficaram como `needs-review`.
5. Se houve divergência entre design e código.
6. Confirmação de que nenhum segredo foi exposto.
7. Confirmação de que nenhum arquivo fora do escopo solicitado foi alterado.
