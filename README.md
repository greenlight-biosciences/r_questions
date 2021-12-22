# GLB Tech Questions

## Question 1
In bioinformatics, k-mers are substrings of length k contained within a biological sequence. Usually, the term k-mer refers to all of a sequence's substring of length k, such that the sequence AGAT would have four monomers (A, G, A, and T), three 2-mers (AG, GA, AT), two 3-mers (AGA and GAT) and one 4-mer (AGAT).

Question: Given a sequence ‘GTGCACAGGTGTG’, can you find the start position and stop position for all 3-mer ‘GTG’?
 
Example 1: Given a sequence 'ATGTGTCCATGT', find the positions of all 3-mer 'ATG'.
Input: 'ATGTGTCCATGT'; output: [(0,2), (8,10)]

Example 2: Given a sequence 'ATGTGTCCATGT', find the positions of all 3-mer 'TGT'. 		
Input:  'ATGTGTCCATGT'; output: [(1,3), (3,5), (9,11)]


## Question 2

In bioinformatics a common tasks related to the sequences are to calculate the GC-content of the given sequence. GC content means the proportion of the G and C nucleotides in the sequence. A set of 10 sequences are provided to you at https://github.com/greenlight-biosciences/r_questions/. Please complete the following tasks that are related to the GC-content.

1.	Use R/Python code to calculate the GC-content of the sequences in the q1.fa file
2.	Identify the sequence with the highest GC-content

* For R
  * You may use https://rdrr.io/snippets/  for writing and testing the code with a shared screen or you are welcome to use Rstudio and share the screen

* For Python
  * You may use https://colab.research.google.com/ for writing ipython/jupyter notebooks. You are welcome to use your own jupyter notebook instance to write and execute the code. Please share your screen when you write the code.


## Question 3

A common substring of a collection of strings is a substring of every member of the collection. We say that a common substring is the longest common substring if there does not exist a longer common substring. For example, `CG` is a common substring of `ACGTACGT` and `AACCGTATA`, but it is not if possible; in this case, `CGTA` is a longest common substring of `ACGTACGT` and `AACCGTATA`.

Note that the longest common substring is not necessarily unique; for a simple example, `AA` and `CC` are both longest common substrings of `AACC` and `CCAA`.

```
>Sequence_1
GATTACA
>Sequence_2
TAGACCA
>Sequence_3
ATACA
```


## Question 4 [Optional]

2.	Let's say we have a file 'sample.fa' with the following text

```
>Gene1 Protease encoding gene
AGGGGTGTAGAGCGCGCG
 
>Gene2 Trypsin
AAAAATTTATTATTATAT
 
>Gene3 Calmodulin
ATATATGTCCCCACGCG
 
```

What is the output of the following code?
```{python}
s2i = {}
fh = open('./sample.fa', 'r')
for line in fh:
    if re.match('^\s+$', line):
        continue
    elif line.startswith('>'):
        seqid = line.split('>')[1]
        seqid_split = seqid.split() 
        seqid = seqid_split[0] 
        s2i[seqid] = ''
    else:
        s2i[seqid] += line
print (s2i)
```
