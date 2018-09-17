# C_Vector
std::vector implemented in C

### How to use

```c
/* include header */
#include "vector.h"

/* define a vector template */
vector_template(int)

int main()
{
  /* declare a vector_t of int */
  vector_t(int) *vec1 = New(vector_t(int));

  assign(vec1, 5, 42); //fill vector with [42, 42, 42, 42, 42]
 
  clear(vec1); //reset vector, vec1->size is now 0
  
  for (int i = 1; i <= 5; i++)  // [1, 2, 3, 4, 5]
    push_back(vec1, i);
  
  erase(vec1, at(vec1, 2)); // [1, 2, 4, 5]
  
  printf("[ ");
  for (iterator(vector_t(int)) it = begin(vec1); it != end(vec1); it++)
    printf(" %d", *it);
  printf(" ]\n");
  
  printf("[");
  for (size_t i = 0; i < vec1->size; i++)
    printf(" %d", get(vec1, i));
  printf("]\n");
  
  Delete(vec1); //release resources
  return 0;
}
```
