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

## 4. The magic

Initialy, a character takes 8 bits, let's see how to hack this with a simple example.
Let's take the following ADN sequence

`TGACTAGATGCTAATGTTAGTT`


It is composed of 4 different characters, while 8 bits can store 256, then we could use only 2 bits to code all those 4 characters. But this is not the optimal way.

Huffman coding resides in binary trees, here is a representation of the one we would get with this file.
![Huffman Tree](/HuffmanTree.png)
As you can see each letter corresonds to a binary sequence, with the shortest ones been asigned to most used characters.

Let's verify it is really the optimal way by calculating size with each method
- Uncompressed (ASCII) : 22*8 bits = 176 bits
- 2 bits : 22 * 2 = 44 bits 
- Huffington : 9 * 1 + 6 * 2 + 5 * 3 + 2 * 3 = 42 bits

Now you know how it works...

## 5. Let's code !
The first function you have to write should return you the occurence of each character in your element.

Now we will build our tree. Each node represents a probabilty.
We will create a node by fusing the 2 less used characters and add their occurence, and iterate like this until the node we get corresponds to the total of characters.

Now that you tree is completed, just add to the character binary sequence a 0 for a left node, or a 1 for the right node.

Finally, you have to replace every character by its sequence. And that's all, your file is now compressed. Don't forget to add the tree in order to be able to recover it.

## 6. Take some time to decompress
This is nice, your file now take less place on your computer, but how can you recover it ? Nothing more simple, just pass through each bit by reading your tree until you find a character, and repeat the process.

## 7. What's next?
Congratulations, now you have wrote your first compression tool, I advise you to read about the evolution of those algorithms or enhance this one. This not that difficult, you just have to recognise patterns rather than characters.

Thanks for participating into this workshop.
