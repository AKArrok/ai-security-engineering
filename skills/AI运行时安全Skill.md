# Skill：AI运行时安全

目标：对任何 Model/Agent/RAG/Memory/Tool/MCP 工作流执行统一运行时安全检查。

```text
Trust = Identity × Context × Permission × Tool Control × Data Boundary × Auditability
```

执行：
1. 标记输入信任域与 provenance。
2. 解析调用者、Agent、服务身份与委托关系。
3. 将任务目标转成最小 task scope。
4. RAG/Memory 读取按来源、租户、时效和授权过滤。
5. Tool 调用前验证 tool/args/object/data scope。
6. 高风险动作走 Policy/HITL；优先 preview/dry-run/可回滚方案。
7. 输出前做数据流边界检查。
8. 执行后验证结果并记录不可抵赖审计。

> **模型负责理解意图，系统负责守住边界。**
