# MemoryManager
MemoryManager内存管理器

自制的轻量化内存管理器，方便将操作的内存限制在自定义的范围内,这样进行内存操作就心里有底了。。

替代malloc()，free()等操作

现有功能：内存申请、内存释放、内存初始化、查看内存池占用情况。

### 示例
```c
Node_TypeDef *newNode = (Node_TypeDef*)MM_Alloc(sizeof(Node_TypeDef));

MM_Free(newNode);
```
