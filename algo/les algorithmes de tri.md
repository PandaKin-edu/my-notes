les algorithmes de tri

# les algorithmes de tri
28/10/2020 19:44

## Tri par sélection

Complexité = $O(n^2)$

- on cherche le plus petit élément de tableau
- on place cette element au debut
- on recherche d'un nouveau minimum
- on place en second position
- ...  
    <img src="../_resources/3d42c22015ca4b72bcbb74d757ca6bc6.png" alt="8ffd12855a1c600d757ef2f6add3ef4b.png" width="885" height="1020" class="jop-noMdConv">  
    ![e83d529ae22cc2e2963cafbc204c2b5b.png](../_resources/291c60ffd66648668f33e45db9640c97.png)  
    ![3de4def280d86dd642064d815ec90b48.png](../_resources/687d4469ce184b3786bd558e68ca81ee.png)  
    ![12925135e979822f20eb9f9485f1dcbf.png](../_resources/1d683fffef4240718d2ddfd1d2216291.png)

### Tri par sélection en C

```c
// Selection sort in C

#include <stdio.h>

// function to swap the the position of two elements
void swap(int *a, int *b) {
  int temp = *a;
  *a = *b;
  *b = temp;
}

void selectionSort(int array[], int size) {
  for (int step = 0; step < size - 1; step++) {
    int min_idx = step;
    for (int i = step + 1; i < size; i++) {

      // To sort in descending order, change > to < in this line.
      // Select the minimum element in each loop.
      if (array[i] < array[min_idx])
        min_idx = i;
    }

    // put min at the correct position
    swap(&array[min_idx], &array[step]);
  }
}

// function to print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// driver code
int main() {
  int data[] = {20, 12, 10, 15, 2};
  int size = sizeof(data) / sizeof(data[0]);
  selectionSort(data, size);
  printf("Sorted array in Acsending Order:\n");
  printArray(data, size);
}
```

## Tri à bulles

complexité = $O(n^2)$

- on parcours le tableau
- on compare les éléments de tableau deux a deux
- si le premier élement est plus grand de deuxiéme,ils sont echangées
- aprés chaque parcours on recommence l'opération avec les élements restants

![7a471c288d15add9d94b5f97b37d3cdf.png](../_resources/fdb4846ce9cd4646bb43dcbb816cb95c.png)  
![3bad5090c70a46760712628e4de4c59e.png](../_resources/e5bb8c84203240009b397900b2091551.png)  
![3a67cdffe114a7b80c8902921265629c.png](../_resources/726751bb01d24dc4b3bbc6efc74f81e1.png)  
![f36ec8337bc414a78189cde0034b76b5.png](../_resources/81e199047d7a4a1eb4211e03156caec9.png)

### Tri a bulles en C
```C
// Bubble sort in C

#include <stdio.h>

void bubbleSort(int array[], int size) {

  // run loops two times: one for walking throught the array
  // and the other for comparison
  for (int step = 0; step < size - 1; ++step) {
    for (int i = 0; i < size - step - 1; ++i) {
      
      // To sort in descending order, change">" to "<".
      if (array[i] > array[i + 1]) {
        
        // swap if greater is at the rear position
        int temp = array[i];
        array[i] = array[i + 1];
        array[i + 1] = temp;
      }
    }
  }
}

// function to print the array
void printArray(int array[], int size) {
  for (int i = 0; i < size; ++i) {
    printf("%d  ", array[i]);
  }
  printf("\n");
}

// driver code
int main() {
  int data[] = {-2, 45, 0, 11, -9};
  int size = sizeof(data) / sizeof(data[0]);
  bubbleSort(data, size);
  printf("Sorted Array in Ascending Order:\n");
  printArray(data, size);
}
```

## Tri par insertion
$Complexité = O(n^2)$
* on prend le premier élement
* on prend le deuxième élément et on le trie par rapport au premier
* on trie les éléments suivants par rapport aux éléments déjà triés
* ...
![48c895703eacb62849e12ac9327544d8.png](../_resources/1d61dd42f6a548f991714ddba95d0c80.png)
![d4eb70c8681855b32697050c1b0b6bcc.png](../_resources/3f3f29658a584cd6b1cf098de6c6bc18.png)
![eaa18a1a64556bcec54ecb5e6ce45a28.png](../_resources/aa0647743ae44256b7153b90faf66688.png)
![2c1a7657432f82c4d783208fe7bc6844.png](../_resources/1e875189b8ed48f79907b1459329bc04.png)
### Tri par insertion en C
```C
// Insertion sort in C

#include <stdio.h>

// Function to print an array
void printArray(int array[], int size) {
  for (int i = 0; i < size; i++) {
    printf("%d ", array[i]);
  }
  printf("\n");
}

void insertionSort(int array[], int size) {
  for (int step = 1; step < size; step++) {
    int key = array[step];
    int j = step - 1;

    // Compare key with each element on the left of it until an element smaller than
    // it is found.
    // For descending order, change key<array[j] to key>array[j].
    while (key < array[j] && j >= 0) {
      array[j + 1] = array[j];
      --j;
    }
    array[j + 1] = key;
  }
}

// Driver code
int main() {
  int data[] = {9, 5, 1, 4, 3};
  int size = sizeof(data) / sizeof(data[0]);
  insertionSort(data, size);
  printf("Sorted array in ascending order:\n");
  printArray(data, size);
}
```
