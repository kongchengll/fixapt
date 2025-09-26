# fixapt - 飞牛更新修复工具

## 简介

fixapt 是一个用于修复飞牛系统更新失败问题的脚本工具。当系统出现更新错误时，可以通过执行此脚本来解决相关问题。

## 问题描述

在某些情况下，飞牛系统更新可能会失败，出现如下错误：

![更新错误示例1](https://github.com/user-attachments/assets/d3a87fd5-6513-4d23-8b9e-6f76ee8e8d56)

![更新错误示例2](https://github.com/user-attachments/assets/b449c850-dc37-4210-869a-2f02411b7285)

## 使用方法

1. 通过 SSH 连接到您的飞牛系统
2. 下载或创建修复脚本
3. 执行以下命令：

```bash


# 执行修复脚本
curl -fsSL https://raw.githubusercontent.com/kongchengll/fixapt/main/fixapt.sh | sudo bash
```

## 功能特点

- 自动检测和修复 apt 源配置问题
- 清理损坏的软件包缓存
- 修复依赖关系问题
- 重置更新配置

## 注意事项

- 请在执行脚本前备份重要数据
- 建议在系统维护时段进行操作
- 执行完成后建议重启系统以确保修复生效

## 支持

如问题仍未解决，请提供详细的错误日志以便进一步分析。

---

*最后更新: 2024年1月*
