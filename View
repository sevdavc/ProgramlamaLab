from matplotlib import pyplot as plt
import numpy as np


def my_rot(im_1):
    m = im_1.shape[0]
    n = im_1.shape[1]

    my_new_image = np.zeros((n, m, 3), dtype=int)
    for row in range(m):
        for col in range(n):
            my_new_image[col, row, :] = im_1[row, col, :]
    return my_new_image


def my_convert_rgb_to_gray(im_1):
    m = im_1.shape[0]
    n = im_1.shape[1]
    my_new_image = np.zeros((m,n),dtype=int)

    for row in range(m):
        for col in range(n):
            my_new_image[row,col] = my_norm(im_1[row,col,:])
    return my_new_image


def my_norm(my_v):
    return int(((my_v[0]**2) + (my_v[0]**2) + (my_v[0]**2))**0.5)


def my_norm_1(my_v):
    s = int(((my_v[0]**2) + (my_v[0]**2) + (my_v[0]**2))**0.5)
    if s > 280:
        return 1
    else:
        return 0


def my_convert_gray_to_bw(im_1):
    m = im_1.shape[0]
    n = im_1.shape[1]
    my_new_image = np.zeros((m, n), dtype=int)

    for row in range(m):
        for col in range(n):
            my_new_image[row,col] = my_norm_1(im_1[row,col,:])
    return my_new_image


file_name = "bird.jpg"
im_1 = plt.imread(file_name)
im_2 = my_rot(im_1)
im_3 = my_convert_rgb_to_gray(im_2)
im_4 = my_convert_gray_to_bw(im_2)

plt.subplot(1, 4, 1)
plt.imshow(im_1)
plt.subplot(1, 4, 2)
plt.imshow(im_2)
plt.subplot(1, 4, 3)
plt.imshow(im_3, cmap='gray')
plt.subplot(1, 4, 4)
plt.imshow(im_4, cmap='gray')
