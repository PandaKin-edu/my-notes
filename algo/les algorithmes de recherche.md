les algorithmes de recherche

# les algorithmes de recherche
28/10/2020 20:16
## Recherche séquentielle / linéaire
<img src="https://render.githubusercontent.com/render/math?math=complexite= O(n)">

* on parcours les élement d'un tableau **non trié** à partir du début
![736f3e993f310fdc433a9940597b3c92.png](../_resources/6a8a05f02ab84c2bbf8690fe6795badb.png)
![ec67dbd7df8186cad6919ddf226b21c4.png](../_resources/70b376409bea42008cbc3da84efb8f54.png)
![78de98d3739176ae1a4e12cce2d037af.png](../_resources/577f3ac31b3b4129aa11db88044056a6.png)
### Recherche séquentielle en C
```c
// Linear Search in C

#include <stdio.h>

int search(int array[], int n, int x) {
  
  // Going through array sequencially
  for (int i = 0; i < n; i++)
    if (array[i] == x)
      return i;
  return -1;
}

int main() {
  int array[] = {2, 4, 0, 1, 9};
  int x = 1;
  int n = sizeof(array) / sizeof(array[0]);

  int result = search(array, n, x);

  (result == -1) ? printf("Element not found") : printf("Element found at index: %d", result);
}
```
## Recherche dichotomique
<img src="https://render.githubusercontent.com/render/math?math=complexite= O(log n)">
*  on commence par décoper le tableau en deux tablea.
*  on compare la valeur recherchée avec la valeur du milieu du tableau.
*  * si la valeur est rechercher est inférieur a la valeur du millieu, alors on cherche dans la 1ére moitié du tableau.
*  * si la valeur rechercher est supérieure à la valeur du milieu, Alors on cherche dans la 2éme moitié du tableau.
*  * on continue le découpage jusqu'à un sous tableau de dimention 1

![7a49afc2f9656427fe8a3c796143b3f5.png](../_resources/b7c40a7208d84f3181c605d695fb9ad6.png)

### Recherche dichotomique en C

```C
// Binary Search in C

#include <stdio.h>

int binarySearch(int array[], int x, int low, int high) {
  // Repeat until the pointers low and high meet each other
  while (low <= high) {
    int mid = low + (high - low) / 2;

    if (array[mid] == x)
      return mid;

    if (array[mid] < x)
      low = mid + 1;

    else
      high = mid - 1;
  }

  return -1;
}

int main(void) {
  int array[] = {3, 4, 5, 6, 7, 8, 9};
  int n = sizeof(array) / sizeof(array[0]);
  int x = 4;
  int result = binarySearch(array, x, 0, n - 1);
  if (result == -1)
    printf("Not found");
  else
    printf("Element is found at index %d", result);
  return 0;
}
```
