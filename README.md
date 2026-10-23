# MyAPI

MyAPI 是 OneHistory 的后端模块运行时探索项目。当前从 `b-Code-MyAPI/` 中的 Lite 原型开始，目标是形成模块注册器、命令管线以及本地/HTTP/MCP 调用适配；页面由独立前端模块提供，AppShell 和 Web 只承担页面宿主层。用于验收模块接入的测试能力和注册适配已外置到根级 `b-Code-TestModule/`。

本项目处于 V4 exploration 状态，不影响已冻结的 `2026-023-AppShell` 3.0.3，也不提供稳定 API 或正式发布包。

## 入口

- [AI 工作合同](AGENTS.md)
- [项目清单](project.manifest.json)
- [文档中心](b-Office/document-center.md)
- [项目概览](b-Office/current/overview.md)
- [技术合同](b-Office/current/technical-contract.md)
- [V4 探索模型](b-Office/current/v4-exploration.md)
- [复用说明](b-Office/package/reuse.md)
- [模块开放说明](Module/模块开放说明.md)

## 当前构建

```powershell
dotnet restore .\b-Code-MyAPI\MyAPI.sln --locked-mode
dotnet build .\b-Code-MyAPI\MyAPI.sln -c Release --no-restore
dotnet run --project .\b-Code-MyAPI\tests\MyAPI.ContractTests\MyAPI.ContractTests.csproj -c Release --no-build
```

旧 Lite 工程已被拆分为合同、运行时、宿主和契约测试项目；外置测试模块用于验证真实的跨目录模块消费，不属于生产内核或发布内容。V4 API 仍处于探索态，待边界稳定后再评审正式 NuGet 命名。

OHS、AppShell 等上层模块的实验性源码和工程暂存于 `Module/`。该目录用于逐步建构和验证模块，不是正式发布快照。

## 保留内容

### logo与作者

- 作者：pinavia
- ![logo](./Logo.png)

### 学习许可与权利保留

- 本项目允许个人、学校和研究者进行非商业性的学习、研究和引用。
- 未经著作权人书面许可，不得将项目内容用于商业开发、产品制造、商业服务、商业宣传、投标交付、毕业设计成品交付或再授权。
- 不得删除作者、来源、版本历史和第三方许可证声明，不得将本项目或其衍生成果宣称为与作者无关的原创项目。
- 软件源码适用 [PolyForm Noncommercial 1.0.0](https://polyformproject.org/licenses/noncommercial/1.0.0/)；机械模型、PCB、原理图、图片、文档、Unity 工程和其他非软件资料适用 [CC BY-NC-ND 4.0](https://creativecommons.org/licenses/by-nc-nd/4.0/)。
- SE、SW、STEP/STP 及其他三维模型仅允许个人或学校进行非商业学习、评审和研究；未经著作权人书面许可，不得用于加工、打样、制造、销售、量产、投标、产品交付、商业宣传、改作或再授权。
- 第三方组件、模板、元件库、外购件模型和工具仍受其原始许可证约束；本声明不扩大作者对第三方内容的权利。

商业使用、产品化、公司内部长期使用、转让或排他性授权需另行取得著作权人的书面许可。
