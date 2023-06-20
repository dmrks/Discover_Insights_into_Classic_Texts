# Discover_Insights_into_Classic_Texts

Discover Insights into Classic Texts
Novels and text contain insights into ideologies and places that are often originally unknown to the reader. 
By reading a written piece, you uncover the opinions of the author on their chosen topic and come to understand both the topic and how the author thinks.

In this project you will perform a natural language parsing analysis to gain deeper insight into one of two famous and often discussed novels in the public domain: 
Oscar Wilde’s The Picture of Dorian Gray or Homer’s The Iliad! 
Fear not if you haven’t heard or read the novels, 
one of the beauties of natural language parsing with regular expressions is the ability to gain insight into lengthy pieces of text without a formal read!

By the end of this project, you will find out the main topics of discussion in the novel of your choosing and can begin to discern some of the author’s thoughts and beliefs!


# Import and Preprocess Text Data

1.
Given to you in the code editor are text files for the The Picture of Dorian Gray, named dorian_gray.txt, and The Iliad, named the_iliad.txt, sourced from Project Gutenberg. 
Import the text of your choosing, convert it to lowercase.


2.
With the text imported, now you need to split the text into individual sentences and then individual words. This allows you to perform a sentence-by-sentence parsing analysis!

Provided to you in the code editor is a customized function word_sentence_tokenize() that will sentence tokenize a text and then word tokenize each sentence, returning a list of word tokenized sentences. Call the function with text as an argument and save the result to a variable named word_tokenized_text.



3.
Save any word tokenized sentence in word_tokenized_text to a variable named single_word_tokenized_sentence. Print single_word_tokenized_sentence as a check to visualize what you have done so far!

# Part-of-speech Tag Text

4.
Next you can part-of-speech tag each sentence to allow for syntax parsing! Begin by creating a list named pos_tagged_text that will hold each part-of-speech tagged sentence from the novel.


5.
Loop through each word tokenized sentence in word_tokenized_text and part-of-speech tag each sentence using nltk‘s pos_tag() function. Append the result to pos_tagged_text.


6.
Save any part-of-speech tagged sentence in pos_tagged_text to a variable named single_pos_sentence. Print single_pos_sentence as a check to visualize what you have done so far!


# Chunk Sentences
7.
Now that you have part-of-speech tagged your text, you can move on to syntax parsing!

Begin by defining a piece of chunk grammar np_chunk_grammar that will chunk a noun phrase. Remember, a noun phrase consists of an optional determiner DT, followed by any number of adjectives JJ, 
followed by a noun NN.


8.
Create a nltk RegexpParser object named np_chunk_parser using the noun phrase chunk grammar you defined as an argument.


9.
Define a piece of chunk grammar named vp_chunk_grammar that will chunk a verb phrase of the following form: noun phrase, followed by a verb VB, followed by an optional adverb RB.


10.
Create a nltk RegexpParser object named vp_chunk_parser using the verb phrase chunk grammar you defined as an argument.


11.
Create two empty lists np_chunked_text and vp_chunked_text that will hold the chunked sentences from your text.


12.
Loop through each part-of-speech tagged sentence in pos_tagged_text and noun phrase chunk each sentence using your RegexpParser‘s .parse() method. Append the result to np_chunked_text.


13.
Within the same loop you defined in the previous task, verb phrase chunk each part-of-speech tagged sentence using your RegexpParser‘s .parse() method. Append the result to vp_chunked_text.


# Analyze Chunks
14.

Now that you have chunked your novel, you can analyze the chunk frequencies to gain insights!

A function np_chunk_counter() that returns the 30 most common NP-chunks from a list of chunked sentences has been imported to the workspace for you. 
Call np_chunk_counter() with np_chunked_text as an argument and save the result to a variable named most_common_np_chunks. 
Print most_common_np_chunks. What sticks out to you about the most common noun phrase chunks? Are you surprised by anything? Open the hint to see our analysis.

Want to see how np_chunk_counter() works? Use the file navigator to open chunk_counters.py and inspect np_chunk_counter().

15.
A function vp_chunk_counter() that returns the 30 most common VP-chunks from a list of chunked sentences has been imported to the workspace for you. 
Call vp_chunk_counter() with vp_chunked_text as an argument and save the result to a variable named most_common_vp_chunks. Print most_common_vp_chunks. 
What sticks out to you about the most common verb phrase chunks? Are you surprised by anything? Open the hint to see our analysis.

Want to see how vp_chunk_counter() works? Use the file navigator to open chunk_counters.py and inspect vp_chunk_counter().
