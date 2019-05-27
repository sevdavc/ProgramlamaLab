from random import randint
import copy

def ShellSort(arr):
    n = len(arr)
    gap = n // 2
    swapCounter = 0
    comparisonCounter = 0

    while gap > 0:
        for i in range(gap, n):
            comparisonCounter += 1
            temp = arr[i]
            j = i
            while j >= gap and arr[j - gap] > temp:
                swapCounter += 1
                arr[j] = arr[j - gap]
                j -= gap

            arr[j] = temp
        gap = gap // 2

    return "swap =", swapCounter, "comparison =", comparisonCounter


def InsertionSort(numbers):
    karsilastirmaSayisi = 0
    YerDegistirme = 0

    for i in range(1, len(numbers)):
        karsilastirmaSayisi += 1
        key = numbers[i]
        j = i - 1
        while j >= 0 and key < numbers[j]:
            YerDegistirme += 1
            numbers[j + 1] = numbers[j]
            j -= 1
        numbers[j + 1] = key

    return "swap = ", YerDegistirme, "comparison = ", karsilastirmaSayisi


def bubbleSort(arr):
    n = len(arr)
    karsilastirmaSayisi = 0
    YerDegistirme = 0

    # Traverse through all array elements
    for i in range(n):

        # Last i elements are already in place
        for j in range(0, n - i - 1):
            karsilastirmaSayisi += 1
            # traverse the array from 0 to n-i-1
            # Swap if the element found is greater
            # than the next element
            if arr[j] > arr[j + 1]:
                YerDegistirme += 1
                arr[j], arr[j + 1] = arr[j + 1], arr[j]

    return "swap = ", YerDegistirme, "comparison = ", karsilastirmaSayisi


def createList(n):
    liste = []
    for i in range(n):
        liste.append(randint(0, 100))

    return liste


liste = createList(1000)
liste2 = copy.deepcopy(liste)
liste3 = copy.deepcopy(liste)
print("Shell sort =", ShellSort(liste))
print("Insertion sort =", InsertionSort(liste2))
print("Bubble sort =", bubbleSort(liste3))
