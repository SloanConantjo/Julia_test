# Julia Set Demo

这是一个非常小的 Julia 集可视化实验仓库，包含 Python 纯实现和 Cython 加速实现两条路径。

## 仓库结构

- `julia_init.py`：纯 Python 版本，包含迭代核心、图像映射和主入口。
- `calc_z_cython.pyx`：Cython 版本的迭代核心函数 `calc_z`。
- `julia.py`：调用 Cython 核心的主脚本，负责生成复平面采样点和渲染输出。
- `setup_z.py`：用于构建 `calc_z_cython.pyx` 扩展模块的 setup 脚本。
- `readme.md`：项目说明文件。

## 运行思路

1. 在复平面上生成一个网格点集合 `zs`。
2. 对每个点重复执行 `z = z^2 + c`，直到发散或达到最大迭代次数。
3. 将每个点的迭代次数映射到 RGB 颜色，输出为图片。

## 典型用途

- 对比 Python 与 Cython 在数值密集循环中的性能差异。
- 作为分形可视化和 Cython 入门示例。
