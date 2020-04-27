# -Epitech-Workshop-Compression Basics
## *How does data compression works?*

## 1. Introduction

Compression is the process of reducing the size of a data.
There is two types of compression. Lossless, which keeps the data intact after reversing the processus (which is called decompression) and lossy, which lessen the quality of the file, but permits better compression rates.

Their use depends on the file you want to process. For example a text file should not contain any error, but a slightly change of color on an image may not be a problem.

Today, we will implement one compression algorithm together.

## 2. Where to begin from ?

As we want to be able to use it anywhere, we need a lossless one. You may now be comfortable with the usage of binary trees, so we will implement the Huffman Coding.

This one can be used to compress most file types, from MP3 music file to DNA sequences.

I provided you a sample textfile in this repository in order to test our code and keep a simple example.

## 3. The algorithm

Firstly, we will keep things simple, I will elaborate later.
The core of modern compression resides in recognising patterns that occurs frequnetly and stock them in a dictionnary, and use them as it was single characters.

The one we will use is only based on characters rather than sequences, but its inventor has proven mathematicaly, it is the optimal way to store single characters using less bits.

## 4. Work in progress

Writing in progress...

You can found on this repository a working python implementation of this algorithm, both for compression and decompression. Enjoy !
