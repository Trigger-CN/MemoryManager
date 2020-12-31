# MemoryManager
MemoryManager内存管理器

自制的轻量化内存管理器，方便将操作的内存限制在自定义的范围内,这样进行内存操作就心里有底了。。

替代malloc()，free()等操作

现有功能：内存申请、内存释放、内存初始化、查看内存池占用情况。

### 示例
```c
//申请内存
Node_TypeDef *newNode = (Node_TypeDef*)MM_Alloc(sizeof(Node_TypeDef));
//内存初始化
MM_Set(newNode, 0, sizeof(Node_TypeDef));
//输出内存占用情况
printf("%d\n",MM_Occupation());
//内存释放
MM_Free(newNode);
```
2020.12.31现已加入Debug功能，方便排查错误

```c
#define USE_DEBUG 1 //当USE_DEBUG为1时，打开Debug功能，反之关闭。

#if ( USE_DEBUG != 0 )
#include <stdio.h>
#define DEBUG_LOG(format, ...)\
do{\
    printf("File:%s Line:%d Function:%s >>", __FILE__, __LINE__, __FUNCTION__);\
    printf(format, ##__VA_ARGS__);\
    printf("\r\n");\
    while(1);\
}while(0)
#else
#define DEBUG_LOG(...)
#endif
```
