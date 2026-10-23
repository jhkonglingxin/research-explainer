# Research Explainer · 科研讲明白

Explain research clearly without weakening the evidence.

An instruction-only Agent Skill for general readers, students, and researchers working outside their own field. It helps explain papers, results, methods, equations, figures, and tables in the reader's language, while retaining the numbers, assumptions, uncertainty, and scope that matter.

## What it helps with

- Plain-language explanations of research questions, findings, and methods.
- Quantitative, qualitative, theoretical, engineering, computational, and mixed evidence.
- Journal-club notes, teaching explanations, public summaries, and cross-disciplinary briefings.
- Figure and table interpretation, including units, scales, reference groups, and uncertainty.
- Chinese, English, and other requested languages. The skill follows the user's language rather than forcing English.

The workflow distinguishes evidence from interpretation, association from causation, simulation from measurement, and missing information from a negative result. It adapts the depth and format instead of forcing every answer into a long report.

## Install

From this repository:

```sh
npx skills add jhkonglingxin/research-explainer --skill research-explainer
```

For a personal Codex installation:

```sh
npx skills add jhkonglingxin/research-explainer --skill research-explainer --agent codex --global
```

The skill is in [`skills/research-explainer`](skills/research-explainer). It contains instructions and two optional reference files, with no executable scripts, required account, or bundled network client. Host capabilities and permissions still determine which files or tools an agent can use.

## Use

In Codex:

```text
$research-explainer Explain this paper for a researcher from another field.
Keep the main numbers and uncertainty, and explain why the method was used.
```

```text
$research-explainer 用普通读者能理解的中文解释这张图。
说明坐标、比较对象、主要结果，以及哪些结论不能据此得出。
```

```text
$research-explainer Explain this theorem to a first-year student.
Define the symbols, preserve the assumptions, and distinguish intuition from proof.
```

Supply the paper, excerpt, table, or image you want explained. A concept question can also be answered without a paper; the skill should not invent a study to support it. Naming the audience and desired length is helpful but not required.

## Example: simplification that preserves uncertainty

**Invented source:** An observational study reports an odds ratio of 0.70, 95% confidence interval 0.46–1.08. Absolute baseline risk is not supplied.

**Avoid:** “The intervention lowers your risk by 30%.”

**Explain:** “The study found an association with lower odds, but the estimate is uncertain and includes no difference. It did not test an intervention, and these numbers alone do not tell us the absolute change in a person's risk.”

This example is synthetic. It is not medical advice or evidence from a real paper.

## 中文说明

`research-explainer` 用于把科研内容讲清楚，面向普通读者、学生和跨专业合作者。它沿用用户的语言和格式，解释必要术语，同时保留关键数字、单位、比较对象、适用条件与不确定性。

它覆盖定量研究、访谈与解释性研究、数学理论、工程实验、机器学习和仿真等常见材料。不会把统计显著写成重要或有效，不会把摘要缺少信息写成全文未报告，也不会把模型预测写成实物验证。图表可通过图注、正文、演讲备注或文字替代来解释，无需每张图都套固定的前后段落。

适合：论文解读、方法讲解、图表解读、组会准备、课堂讲解、公众摘要、跨学科沟通。

不承担：自动完成新分析、验证整篇论文、替代正式证据评价、替用户作临床决定，或默认上传与发布研究文件。需要新检索、计算或正式文档时，应使用所在环境中适用的工具，并保留任务范围。

## Validation and limitations

Synthetic evaluation requests are provided in [`evals`](evals). They exercise evidence fidelity and readable explanations across different research types. These are behavioral scenarios, not proof that every answer will be correct. Review explanations against their sources, especially when the information is incomplete or consequential.

The skill adds no telemetry of its own. The host application, install tool, and any services explicitly used have their own behavior and policies.

## Contributing

Report a concrete failure with a public or synthetic minimal example, the requested audience, and what the explanation changed or missed. Do not submit confidential manuscripts, participant data, credentials, or identifying interview excerpts in issues or pull requests.

## License

[MIT License](LICENSE). Copyright (c) 2026 jhkonglingxin.
