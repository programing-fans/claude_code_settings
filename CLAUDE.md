# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 🏗️ Repository Architecture

This is a **Claude Code multi-agent workflow system** that transforms manual development commands into automated expert team workflows. It implements a **Requirements-Driven Development** approach with 90% quality gates.

### Core System Components

#### 1. **Commands Directory** (`/commands/`)
11 specialized slash commands for targeted development tasks:
- `/requirements-pilot` - Complete automated workflow (requirements → code → review → test)
- `/ask` - Architecture consultation without code changes
- `/code` - Feature implementation with constraints
- `/debug` - UltraThink systematic problem analysis
- `/test` - Comprehensive testing strategy
- `/review` - Multi-dimensional code validation
- `/optimize` - Performance optimization coordination
- `/refactor` - Quality-gated code refactoring
- `/bugfix` - Systematic bug resolution workflow
- `/docs` - Documentation generation
- `/think` - Advanced analysis and strategic thinking

#### 2. **Agents Directory** (`/agents/`)
Two-tier agent architecture:

**Tier 1: Contains-Studio Agents** (`/agents/`) - 40+ specialized agents organized by:
- **Engineering**: ai-engineer, backend-architect, devops-automator, frontend-developer, mobile-app-builder, rapid-prototyper, test-writer-fixer
- **Design**: brand-guardian, ui-designer, ux-researcher, visual-storyteller, whimsy-injector
- **Marketing**: app-store-optimizer, content-creator, growth-hacker, tiktok-strategist
- **Product**: feedback-synthesizer, sprint-prioritizer, trend-researcher
- **Project Management**: experiment-tracker, project-shipper, studio-producer
- **Studio Operations**: analytics-reporter, finance-tracker, infrastructure-maintainer

**Tier 2: Requirements-Driven Agents** (`/agents/zhisheng/`) - 9 specialized agents:
- `requirements-generate` - Create implementation-ready technical specs
- `requirements-code` - Direct implementation with minimal architecture overhead
- `requirements-review` - Practical code review focused on functionality
- `requirements-testing` - Functional validation and integration testing
- `bugfix` - Defect analysis and resolution
- `bugfix-verify` - Objective fix validation
- `code` - Development coordination
- `debug` - Systematic debugging with UltraThink
- `optimize` - Performance optimization coordination

### 🎯 Key Workflows

#### **Requirements-Driven Full Automation**
```bash
/requirements-pilot "企业用户管理系统，JWT认证，RBAC权限，500并发用户"
```
Automatically executes:
1. **Phase 1**: Interactive requirements confirmation (90+ quality gate)
2. **Approval Gate**: Explicit user approval required
3. **Phase 2**: Automated sub-agent chain execution
   - `requirements-generate` → `requirements-code` → `requirements-review` → testing decision

#### **Manual Expert Orchestration**
```bash
/ask "微服务架构设计考虑"
/code "实现JWT认证中间件"
test "创建并发测试套件"
review "验证安全最佳实践"
```

### 📊 Quality Gate System

**Requirements Quality (100-point system)**:
- Functional Clarity (30 pts) - Clear specs, user interactions, success criteria
- Technical Specificity (25 pts) - Integration points, constraints, performance needs
- Implementation Completeness (25 pts) - Edge cases, error handling, validation
- Business Context (20 pts) - User value, priority definition

**Code Quality (90% threshold)**:
- Functional correctness
- Integration quality
- Code maintainability
- Performance adequacy

### 🔧 Usage Patterns

#### **Complex Feature Development**
```bash
# Full automation with quality gates
/requirements-pilot "OAuth2认证系统，支持刷新令牌，集成企业LDAP，刷新令牌轮换"

# Manual step-by-step for learning/debugging
/ask "OAuth2架构最佳实践"
/code "实现核心认证逻辑"
/test "创建安全测试套件"
review "验证实现质量"
```

#### **Bug Resolution**
```bash
# Systematic bug fixing
/bugfix "用户登录在高并发时偶尔失败"

# Manual debugging
/debug "分析登录并发问题"
code "实现修复方案"
bugfix-verify "验证修复效果"
```

#### **Performance Optimization**
```bash
optimize "数据库查询性能问题"
```

### 🌍 Language Support
- **Chinese**: All commands support Chinese input/output
- **Mixed Language**: Seamless Chinese/English switching
- **Context-Aware**: Automatically detects and responds in appropriate language

### 📁 Key File Structures

```
claude_code_settings/
├── commands/          # 11 specialized slash commands
├── agents/           # Multi-tier agent architecture
├── README-zh.md      # Comprehensive Chinese documentation
├── README.md         # English overview
└── CLAUDE.md         # This guidance file
```

### 🚀 Quick Start Commands

#### **For New Projects**
```bash
/requirements-pilot "描述你的第一个功能需求"
# 自动执行完整工作流
```

#### **For Existing Codebases**
```bash
/ask "分析现有架构并提出改进建议"
/bugfix "修复已知的生产问题"
optimize "提升关键路径性能"
```

#### **For Learning/Exploration**
```bash
/think "分析这个技术决策的利弊"
/ask "解释微服务架构的核心概念"
```

### ⚡ Advanced Features

#### **Testing Control Options**
- `--test` / `要测试` - Force testing execution
- `--no-test` / `不要测试` - Skip testing phase
- Interactive mode - Smart recommendations based on task complexity

#### **Quality Customization**
- Default: 90% quality threshold
- Override: Set custom thresholds per command
- Iterative: Automatic optimization loops until threshold met

#### **Context Isolation**
- Each sub-agent operates in independent context
- No cross-contamination between specialized domains
- Maintains focus and expertise depth

### 🎭 Pro Agent Triggers

Some agents activate automatically:
- **studio-coach** - Complex multi-agent coordination
- **test-writer-fixer** - After code changes/bug fixes
- **whimsy-injector** - After UI/UX improvements
- **experiment-tracker** - When feature flags added

### 📈 Development Philosophy

**Requirements-Driven**: Specifications → Implementation → Validation
**Quality-Gated**: Objective scoring prevents quality degradation
**Expert Specialization**: Domain experts vs. generalists
**Rapid Iteration**: 6-day sprint compatibility
**Production Ready**: Emphasis on working solutions over perfect architecture

### 🛠️ Common Commands Summary

| Command | Purpose | Automation Level | Quality Gate |
|---------|---------|------------------|--------------|
| `/requirements-pilot` | Full development workflow | 95% automated | 90% threshold |
| `/ask` | Architecture consultation | Manual | N/A |
| `/code` | Feature implementation | Semi-automated | Review required |
| `/debug` | Systematic problem analysis | Guided | Validation |
| `/test` | Testing strategy | Automated | Coverage metrics |
| `/optimize` | Performance tuning | Semi-automated | Benchmark validation |

### 🔍 Diagnostic Commands

```bash
# Check system health
/deploy-check

# Security analysis
/security

# Workflow optimization
/commands/think "分析当前开发流程瓶颈"
```