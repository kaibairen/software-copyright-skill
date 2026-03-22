---
name: software-copyright-design
description: 指导完成中国计算机软件著作权申请的全流程文档生成。当用户请求生成"软著"、"软件著作权"、"软件说明文档"、"软件代码文档"或提及软件著作权申请时使用此技能。包含意图确认、PRD生成、使用说明书生成、代码文档生成和最终材料整理五个步骤。
user-invocable: true
allowed-tools: Read, Write, Edit, Bash
---

## 概述

本技能提供完整的计算机软件著作权申请文档生成流程，分为五个步骤。根据用户当前所处的阶段，自动选择对应的reference指导执行。

### 步骤判断逻辑

| 用户状态 | 使用的参考文件 |
|---------|--------------|
| 首次启动软著设计 | `step1-confirm-intent` |
| 已完成意图确认，需要生成PRD | `step2-generate-prd` |
| 已完成PRD，需要生成软件说明文档 | `step3-generate-manual` |
| 已完成软件说明文档，需要生成代码文档 | `step4-generate-code` |
| 已完成所有部分，整理软著材料 | `step5-documents-archive` |

### 使用流程

1. 首次调用时，自动使用 `step1-confirm-intent` 收集信息
2. 每个步骤完成后，会提示用户进入下一步
3. 用户可直接指定某个步骤（如"直接生成PRD"、"跳到文档生成"）

---

## Reference: step1-confirm-intent

软著设计意图确认和信息收集阶段。

详细指令请参考 `references/step1-confirm-intent.md`

---

## Reference: step2-generate-prd

基于前期收集的prepare信息生成软件项目PRD文件。

详细指令请参考 `references/step2-generate-prd.md`

---

## Reference: step3-generate-manual

基于PRD信息生成符合《计算机软件著作权登记办法》要求的《软件使用说明书》。

详细指令请参考 `references/step3-generate-manual.md`

---

## Reference: step4-generate-code

基于PRD信息和前端静态代码生成符合《计算机软件著作权登记办法》要求的《软件代码文档》。

详细指令请参考 `references/step4-generate-code.md`

---

## Reference: step5-documents-archive

整理所有文件信息，生成符合《计算机软件著作权登记办法》要求的申请表、使用说明书和代码手册。

详细指令请参考 `references/step5-documents-archive.md`

本步骤使用以下Python脚本生成最终文档：
- `scripts/generate_application_form.py` - 填写申请表


---

## 附加资源

- 申请表模板：`asserts/申请表模板.docx`
- 使用手册模板：`asserts/申请表模板.docx`
- 代码手册模板：`asserts/申请表模板.docx`