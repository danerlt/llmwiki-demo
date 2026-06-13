# Python 机器学习技术栈概览

> 来源类型:学习笔记 · 收录日期:2026-06-13

## §1 为什么是 Python

Python 成为 AI 第一语言的原因不在语言本身的性能,而在生态:几乎所有
核心计算库的底层都是 C/C++/CUDA 实现,Python 只是"胶水层"。科研代码
到生产代码的迁移成本低,社区教程与预训练模型资源最丰富。

## §2 数值计算基座:NumPy

NumPy 提供 ndarray(多维数组)与向量化运算,是整个技术栈的地基。
关键心智模型:**避免 Python 层的 for 循环,用广播(broadcasting)和
向量化操作把计算下沉到 C 层**。pandas、scikit-learn、PyTorch 的张量
接口都沿袭了 NumPy 的 API 习惯。

## §3 经典机器学习:scikit-learn

scikit-learn 覆盖分类、回归、聚类、降维与模型评估,API 统一为
`fit / predict / transform` 三件套。适合中小规模表格数据;深度学习
不在其范围内。

## §4 深度学习:PyTorch

PyTorch 是当前研究界与工业界的主流深度学习框架,核心抽象:

- `Tensor`:支持 GPU 加速与自动微分的多维数组,接口与 NumPy 高度相似
- `autograd`:动态计算图,反向传播自动求导
- `nn.Module`:模型组件化封装
- `DataLoader`:批量数据加载与预处理流水线

动态图(define-by-run)让调试体验接近普通 Python 代码,这是它赢得
研究社区的关键原因。

## §5 学习顺序建议

先 NumPy(理解向量化)→ pandas(数据处理)→ scikit-learn(建模流程
与评估方法论)→ PyTorch(深度学习)。跳过前三步直接学深度学习的人,
通常会在数据处理和实验评估上反复踩坑。
