# Wordle Stats

## Introduction

These are statistics and analysis that I've used in determining the best word 
score based on an algorithmically-sorted word list I developed to play the 
game, Wordle. All of these files are available for anyone to digest and can be 
freely used non-commercially.

This was created by Cariad Keigher on January 16th, 2022.

## Contents

This is an explanation of what is in this repository:

* `Unprocessed/` contains JSON files of unprocessed data
* `Processed/` contains JSON files of processed data which also correct a bug
* `wordlist.txt` is a plaintext file separated by newlines of all words tested

All files stored in the two directories are compressed using GZip.

## The Data

If you're looking to work with the JSON files, here is a brief explaniner.

### Unprocessed Data

Unprocessed data is in a simple format with the filename indicating the starting 
word and then within the files themselves are a key value array showing attempts.

A file such as `zowie_output_efficient.json` will be for scenarios where the 
starting word "zowie" was used. Contained within will be candidate word of which 
must be found and then an accompanying array of all words tried until success.

There are a lot of words where the final word is not arrived upon. This is the 
result of the array not having the final word appended when complete and it 
should be safely presumed that you can add it to the data should you run into 
this scenario.

In the processed data, this above problem does not exist.

### Processed Data

This is the data where a lot of my stats are built from. As per before, a file 
named `pucks_output_efficient.json.processed.json` would indicate a starting word 
of "pucks".

Here are what the parent keys mean:

* `attempts` are the number of overall attempts were made with the word
* `average` is the average number of attempts per word
* `quickest` is the shortest attempts possible with the word (should be `2`)
* `results` contains key value pairs with the key indicating the number of 
attempts and then subsequent keys being the target words
* `score` is the word score based on my blog post
* `scores` is just a summary of what is contained in `results` for easy 
processing
* `starting` is the starting word as per the filename
* `worst` is the worst score the starting word received

