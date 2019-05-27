import random


def randomCreation(n):
    dizi = []
    for i in range(n):
        dizi.append(random.randint(0, 100))
    return dizi


def get_mean_for_n_integer(numbers):
    toplam = 0
    tane = 0
    for sayi in numbers:
        toplam += sayi
        tane += 1
    return toplam / tane


def get_std_for_n_integer(numbers):
    mean = get_mean_for_n_integer(numbers)
    toplam = 0
    tane = 0
    for sayi in numbers:
        toplam += (sayi - mean) ** 2
        tane += 1
    var_1 = toplam / (tane - 1)
    std_1 = var_1 ** (1 / 2)
    return std_1


def normalizasyon(numbers):
    new_numbers = []
    ortalama = get_mean_for_n_integer(numbers)
    standart_sapma = get_std_for_n_integer(numbers)
    for x in numbers:
        new_x = (x - ortalama) / standart_sapma
        new_numbers.append(new_x)
    return new_numbers


def get_mean_one_std_neighbor_ratio(numbers):
    ortalama = get_mean_for_n_integer(numbers)
    standart_sapma = get_std_for_n_integer(numbers)
    tane = 0
    toplamtane = 0
    low = ortalama - standart_sapma
    high = ortalama + standart_sapma
    for sayi in numbers:
        if (low < sayi and high > sayi):
            tane += 1
        toplamtane += 1
    return tane / toplamtane


# insertion sort
# her bir sayıyı kendinden önceki ile karşılaştır gerekli ise swap yap
def insertionSort(numbers):
    karsilastirmaSayisi = 0
    YerDegistirme = 0

    for i in range(1, len(numbers)):
        for j in range(i, 0, -1):
            karsilastirmaSayisi += 1
            if (numbers[j] < numbers[j - 1]):
                # swap
                YerDegistirme += 1
                temp = numbers[j - 1]
                numbers[j - 1] = numbers[j]
                numbers[j] = temp
    return karsilastirmaSayisi, YerDegistirme


def get_mean_of_swap_in_insertion(numTrails, numInt):
    swap_sayilari = []
    for i in range(numTrails):
        sayilar_1 = randomCreation(numInt)
        sayilar_2 = insertionSort(sayilar_1)
        s_1 = sayilar_2[1]
        swap_sayilari.append(s_1)

    mean_1 = get_mean_for_n_integer(swap_sayilari)
    std_1 = get_std_for_n_integer(swap_sayilari)

    return numInt, mean_1, std_1


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

    return YerDegistirme


def get_mean_of_swap_in_bubble(numTrails, numInt):
    swap_sayilari = []
    for i in range(numTrails):
        sayilar_1 = randomCreation(numInt)
        s_1 = bubbleSort(sayilar_1)
        swap_sayilari.append(s_1)

    mean_1 = get_mean_for_n_integer(swap_sayilari)
    std_1 = get_std_for_n_integer(swap_sayilari)

    return numInt, mean_1, std_1


sayilar = [19, 25, 75, 14, 28, 91, 34]

numbers = randomCreation(10)
print(numbers)

ortalama = get_mean_for_n_integer(numbers)
print("ortalama =", ortalama)

std = get_std_for_n_integer(numbers) ** (1 / 2)
print("standart sapma =", std)

normalize_dizi = normalizasyon(numbers)
print("normalize dizi =", normalize_dizi)

print(get_mean_one_std_neighbor_ratio(numbers))
print(insertionSort(sayilar))
print(sayilar)

result_insertion = get_mean_of_swap_in_insertion(10, 1000)
result_bubble = get_mean_of_swap_in_bubble(10, 1000)

print("İnsertion: ", result_insertion)
print("Bubble: ", result_bubble)
