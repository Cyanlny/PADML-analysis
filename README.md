# PAD Machine Learning — analysis source archive

完整分析源码快照，归档日期：2026-10-14。经作者授权，仓库于2026-10-16开放公开访问。此次仅变更可见性及说明，不改变归档源码，不启动或修改任何计算。

## 下载

下载 `PADML-analysis-source-20261014.zip`，按 `SHA256SUMS.txt` 核对后解压。包内逐文件来源、SHA256与大小见 `SOURCE_MANIFEST.json`。

## 包含的分析

- `machine_learning/`：原始数据绑定、嵌套 LOCO、训练/应用双视图 M20 MICE、筛选、RSF/GBM/XGBoost/CoxTime/Elastic Net/FPM/Cox PH、refit、SHAP、O_fit、selection B1000、A04、评价修订、曲线与 RMSE、统计补充研究、紧凑存储和恢复、OSS传输，以及独立 AAR 阈值分析。
- `association/`：主关联分析的冻结 R 引擎、A01–A07 相关入口、协变量/模型/种子/科学规则注册表、Rubin 合并、PH/时变效应、RCS、亚组与敏感性分析，以及发布源码清单内的辅助脚本。
- `association_a01_source_delta/`：阈值输入所用原 A01 冻结源码与后续关联源码的少量差异。只需复现原 A01 时，按清单 `association_a01_original_members` 将指定成员放回其原 `source_path`，不得将后续来源混称为原 A01。
- 保留原科学协议、约束、依赖锁、原生性能补丁和工程测试。历史修复脚本位于 `machine_learning/execution/`，不是新任务的通用启动入口。

## 来源版本

- 机器学习及阈值：`c38c729a3210a37a51a99d21fcaf8f9f503f2adf`。
- 关联分析发布代码：`d7b99a742e92426b1641700b2eafe6782ee5864f`；已对照发布清单核对全部61个登记源文件。其代码胶囊另包含科学配置及执行依赖。
- 原 A01：`b916e0088faa92e72e29adb54ed5340ade9f3430`，代码胶囊SHA256为 `3b538926cbda06ee08ded8177bfec0e92d97ee609090cd1565c870c629aeadf3`。
- 这是按文件保留原字节的源码归档，不包含 `.git` 历史；压缩包具有独立SHA256，不冒充原冻结部署包。

## 使用入口

先阅读各目录的科学协议与 README/AGENTS。机器学习环境由 `machine_learning/dependency-lock.json` 及 `config/environment.example.json` 说明；关联分析依赖见 `association/renv.lock`。

机器学习命令说明：在 `machine_learning/` 中运行 `python -m padml.run --help`。阈值命令说明：`python -m padml.threshold_analysis --help`。这些帮助命令不启动科学计算。

阈值分析需要独立、受限的原 A01 `analysis_state.rds` 与原ROC输入，不能用机器学习插补数据代替。主流程和原生回归检查也需要相应已授权数据及锁定运行环境。

## 数据与环境边界

本包不包含原始患者工作簿、插补数据、患者级结果、拟合模型、SSH/OSS/GitHub密钥、登录凭证、安装环境二进制、运行日志或旧计算回执。变量字典、科学注册表、代码内测试夹具与历史编译说明属于源码材料。原始结果和环境制品继续按既有受限OSS归档管理。

冻结依赖中含定制R内核；只安装同名最新版CRAN包不能替代锁定环境。原生补丁和制品身份保留，运行环境须另外恢复及验收。本次只验证源码归档一致性和Python语法，不重复拟合、插补、SHAP或重抽样。

部分历史辅助脚本保留原运行路径作为来源说明；不可直接用于新实例。使用时需按实际环境配置，并继续遵守患者数据保护和计算owner规则。第三方组件沿用原许可；本次归档不授予新的开源许可证。
