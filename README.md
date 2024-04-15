# Algoritmo de Kadane

O Algoritmo de Kadane é uma solução eficiente para encontrar a soma máxima de um subarray contíguo dentro de um array unidimensional de números. Este algoritmo é particularmente útil em problemas de programação dinâmica, onde a abordagem de força bruta pode ser muito lenta.

## Como Funciona

O algoritmo itera sobre o array, calculando a soma atual dos elementos. Se a soma atual se tornar negativa, o algoritmo a reinicia para zero. A cada passo, se a soma atual for maior que a soma máxima encontrada até então, a soma máxima é atualizada.

## Implementação em C++

Aqui está uma implementação simples do Algoritmo de Kadane em C++:

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    int max_sum = INT_MIN;
    int current_sum = 0;
    int array[] = { -2, -3, 4, -1, -2, 1, 5, -3 };
    
    int n = sizeof(array) / sizeof(array[0]);
    
    for(int i = 0; i < n; i++) {
        current_sum = current_sum + array[i];
        if(max_sum < current_sum) {
            max_sum = current_sum;
        }
        if(current_sum < 0) {
            current_sum = 0;
        }
    }
    cout << "A soma máxima do subarray é: " << max_sum << endl;
    return 0;
}
```

## Exemplo de Uso

Dado o array `{-2, -3, 4, -1, -2, 1, 5, -3}`, a implementação acima retornará `7`, que é a soma do subarray `{4, -1, -2, 1, 5}`.

## Complexidade

A complexidade de tempo do Algoritmo de Kadane é O(n), o que o torna muito mais eficiente do que a abordagem de força bruta, que tem uma complexidade de tempo O(n^2).

## Conclusão

O Algoritmo de Kadane é uma ferramenta poderosa para resolver problemas de soma de subarray e é um bom exemplo de como a programação dinâmica pode ser usada para criar soluções eficientes para problemas computacionais complexos.
