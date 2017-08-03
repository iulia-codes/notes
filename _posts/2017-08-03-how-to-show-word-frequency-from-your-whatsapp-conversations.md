Data science is beautiful. It is so beautiful that it offers you the possibility to understand what you actually feel. In this article,
I will show you how to export your whatsapp conversation and make something meaningful of it. At the end, we will have a word cloud created.

Step1: Export your WhatsApp conversation 

To export your WhatsApp conversation, choose your wished chat. Click on "More" and choose "Export". You can either e-mail it to yourself or
save it to a Google Drive.

Step2: Data cleanup

This step is the largest one, as it requires us to clean the data that we want to analyze. For this step you need Sublime Text and Excel.

Open your WhatsApp text file in Sublime text. Every conversation has a pattern with time+name. To remove time+name simply do a REGEX search 
by using Sublime. 

Numbers are not important so:
* start by removing the numbers from the conversation, as shown here: <a href="https://forum.sublimetext.com/t/deleting-digits-after-a-specific-character/14620/2" target="_blank"> Remove timestamp and name </a>

What the above does, is simply to remove every number it finds inside the conversation. Great, now you have removed numbers ... there 
are some other things to do:
* remove other special characters like ":" by selecting the characters and replacing it with blank

By now, you should have a cleaned up file that contains only the conversation.

Step3: Analyze words

Clone this repository and run it locally. <a href="https://github.com/DaleSeo/word-frequency" target="_blank"> Github repository </a> 

There is one more step in able to run the program: a word must be on each line. <a href="https://forum.sublimetext.com/t/split-into-lines/10196" target="_blank"> Split text into lines </a> 

* Highlight your space, press Alt+F3 (windows) to select all, hit return.
* If the whitespace varies, use a regex search, then select all as above and hit return.

Finally, analyze the words by running:

node analyze input.txt out.txt

The file generated will be like this: 

```
 Easy occurred 1 times
  Nb occurred 43 times
  Omg occurred 4 times
```

Step4: Cleanup occurence results

Once you have a file as in the sample shown above, the next step is to import it into Excel. 

Open Excel and go to <b>Data > From Text</b>, Delimited > Spaces.

Cleanup and filter the occurence results. Remove column occurence and filter the columns by word count... The result should look like this:
```
ca	303
in	260
```

Step5: Visualize your data

A few words and their occurences would not give us a lot of information. Therefore, let's use two tools to visualize your data:

1) Semantic Word Cloud Vizualization

http://wordcloud.cs.arizona.edu/

Paste the words and you will have a nicely presented cloud of words. This is nice because it is an academical tool looking at the
importance of words.

2) Word clouds

http://www.wordclouds.com/

Paste the words and their frequency and you will be presented with a word cloud.

