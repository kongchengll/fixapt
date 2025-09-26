# fixapt - 飞牛更新修复工具

## 简介

fixapt 是一个用于修复飞牛系统更新失败问题的脚本工具。当系统出现更新错误时，可以通过执行此脚本来解决相关问题。

## 问题描述

在某些情况下，飞牛系统更新可能会失败，出现如下错误：

![更新错误示例1](https://github.com/user-attachments/assets/d3a87fd5-6513-4d23-8b9e-6f76ee8e8d56)

![更新错误示例2](https://github.com/user-attachments/assets/b449c850-dc37-4210-869a-2f02411b7285)

## 使用方法

### 第一步：SSH连接到飞牛系统
如果您不熟悉SSH连接，请参考以下教程：
- [飞牛系统SSH连接教程](https://blog.csdn.net/zhengaga/article/details/145811517])
- [Windows系统SSH连接指南](https://blog.csdn.net/zhengaga/article/details/145811517)
- [Mac/Linux系统SSH连接指南](https://zhuanlan.zhihu.com/p/1929105535367636231)

基本SSH连接命令：
```bash
ssh 用户名@飞牛系统IP地址
# 示例：ssh admin@192.168.1.100
```

### 第二步：执行修复命令
在SSH连接成功后，执行以下一键修复命令：

```bash
curl -fsSL https://raw.githubusercontent.com/kongchengll/fixapt/main/fixapt.sh | sudo bash
```

### 替代方法：分步执行
如果上述命令执行失败，可以尝试分步执行：

```bash
# 下载脚本
wget https://raw.githubusercontent.com/kongchengll/fixapt/main/fixapt.sh

# 给予执行权限
chmod +x fixapt.sh

# 执行脚本
sudo ./fixapt.sh
```

## 功能特点

- 自动检测和修复 apt 源配置问题
- 清理损坏的软件包缓存
- 修复依赖关系问题
- 重置更新配置
- 交互式操作，安全可靠

## 执行流程

1. **自动备份**：脚本会自动备份当前软件源配置
2. **清理缓存**：清理损坏的软件包缓存和临时文件
3. **重置源配置**：恢复默认的软件源设置
4. **系统更新**：执行系统更新和修复依赖关系
5. **完成验证**：显示修复结果和后续建议

## 注意事项

- ⚠️ 请在执行脚本前备份重要数据
- ⚠️ 建议在系统维护时段进行操作
- ⚠️ 执行过程中请保持网络连接稳定
- ⚠️ 执行完成后建议重启系统以确保修复生效
- 💡 脚本会自动请求sudo权限，无需提前切换root用户

## 故障排除

如果脚本执行失败，请检查：
- SSH连接是否稳定
- 网络连接是否正常
- 系统时间是否正确
- 磁盘空间是否充足

## 支持

如问题仍未解决，请提供以下信息以便进一步分析：
1. 完整的错误截图或日志
2. 飞牛系统版本信息
3. 执行 `sudo apt update` 的输出结果

---

*最后更新: 2025年9月*
