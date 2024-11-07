#include <iostream>
#include <ctime>
#include <cstdlib>

int main() {
    const int size = 20;
    int A[size], B[size];
    int *pA = A, *pB = B, countB = 0;

    std::srand(static_cast<unsigned int>(std::time(0)));

    for (int i = 0; i < size; ++i) {
        *(pA + i) = std::rand() % 201 - 100;
    }

    for (int i = size - 1; i >= 0; --i) {
        if (*(pA + i) < 0) {
            *(pB + countB++) = *(pA + i);
        }
    }

    std::cout << "Масив B: ";
    for (int i = 0; i < countB; ++i) {
        std::cout << *(pB + i) << " ";
    }
    std::cout << std::endl;

    return 0;
}
