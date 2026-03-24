# 小鹏汽车 AI Infra 一面

- 来源平台：牛客
- 原始 URL：https://www.nowcoder.com/feed/main/detail/e4e725793a3f4c9197c36645bc63cf32
- 日期：2026-03-02
- 公司/岗位：小鹏汽车 / AI Infra 一面
- 梳理状态：已完成首轮提炼
- 可信度：高，基于搜索摘要整理

## 原始问题梳理

1. 项目深挖
2. 给出代码找 4 个编译错误，重点考察 `const` 的作用范围
3. 动态链接库依赖顺序
4. `static_cast`、`dynamic_cast`、`const_cast`、`reinterpret_cast` 的区别与底层含义
5. 给出 CUDA Kernel 代码，识别其功能
6. 手撕：计算平面上两个任意角度矩形的重叠面积

## 分类整理

### C++ 基础与编译链接

- `const` 的作用范围和常见编译错误
- 动态链接库依赖顺序
- 四种 `cast` 的语义和使用边界

### CUDA 与底层实现

- CUDA Kernel 功能识别

### 算法题

- 任意角度矩形重叠面积计算

## 备注

- 这篇明显偏 `AI Infra / C++ / CUDA / 底层工程`，不是纯大模型八股。
