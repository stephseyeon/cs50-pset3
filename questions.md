# Questions

## What's `stdint.h`?
stdint.h is a header file in C library that allows programmers to write different sets of integer types.

## What's the point of using `uint8_t`, `uint32_t`, `int32_t`, and `uint16_t` in a program?
These are different integer types with a exact number of width. For example, 'uint8_t' is an unsigned integer type (integer that can only hold positive numbers) with a width of 8-bits, and 'int32_t' is a signed integer (integer that can hold both positive and negative numbers) type with a width of 32-bits. These integer types are used to hold exact amount of data in different cases.

## How many bytes is a `BYTE`, a `DWORD`, a `LONG`, and a `WORD`, respectively?
BYTE = 1 byte (8 bits)
DWORD = 4 bytes (32 bits)
LONG = 4 bytes (32 bits)
WORD = 2 bytes (16 bits)

## What (in ASCII, decimal, or hexadecimal) must the first two bytes of any BMP file be? Leading bytes used to identify file formats (with high probability) are generally called "magic numbers."
The first two bytes of any BMP file should be bfType and bfSize......TODO

## What's the difference between `bfSize` and `biSize`?
bfSize is BITMAPFILEHEADER that contains information about type, size, layout of a file that contains DIB (Device Independent Bitmap; Windows general bitmap format), and biSize is BITMAPINFOHEADER that contains information about dimensions and color format of DIB.

## What does it mean if `biHeight` is negative?
If biHeight is negative, it's indicating a top-down DIB, meaning the memory starts reading the pixels from upper-left corner in a row.

## What field in `BITMAPINFOHEADER` specifies the BMP's color depth (i.e., bits per pixel)?
A 4-bit index specifies the Bitmap's color depth.

## Why might `fopen` return `NULL` in `copy.c`?
If the file that's trying to open doesn't exist, it'll go back to 0.

## Why is the third argument to `fread` always `1` in our code?
fread specifies how many files you want read but because we only need to read 1 struct, it's always 1.

## What value does `copy.c` assign to `padding` if `bi.biWidth` is `3`?
Because the size of RGBTRIPLE is 3 bytes, 
3 (bytes) * 3 (bytes per pixel) = 9
9 % 4 (DWORD; biSize) = 1
4 - 1 = 3
3 % 4 = 3
Thus, int padding = (4 - (3 * 3 % 4)) % 4) = 3

## What does `fseek` do?
fseek moves the pointer to a different location in the file.

## What is `SEEK_CUR`?
A constant integer that specifies the current position of the file pointer.
