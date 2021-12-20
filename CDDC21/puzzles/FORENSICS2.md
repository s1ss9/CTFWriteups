## CATEGORY

Forensics

## Challenge

A USB key was found on one of the destroyed boats of GDC, along with a CANOIN camera that had been destroyed. Your task is to find evidence that can show the resistance where to find that yacht. They have provided you with an image of a USB key. 

Note: You have to answer the flag in the format CDDC21{answer}.

## Hint(s)

None taken

## Solution

The only data we are given is a file with the extension ".DD", supposedly the image of a USB key. Upon some research, we found this tool called Autopsy which is commonly used to analyse disk images. 

However, Autopsy is unable to open the file.DD which forced us to do more research work on how to open this USB image. 

Using the 'file' command in linux and checking the [file signature](https://www.garykessler.net/library/file_sigs.html) database, we identified the file to be an Expert Witness Compression Format (EWF) file, more specifically EWF-E01. And the extension for this file type is usually .E01. Thus by changing the extension, we can open this USB image in Autopsy.

Thereon, we obtain a few random photos related to 'spy' or 'qatar', a photo of a notepad with 'password is skipper123' written on it and lastly a password protected zip file.
Using the password to unlock the zip file, we get three photos of a yacht, whose location seems to be of interest here (as hinted by the challenge description). 

Using reverse image search, we easily identified the yacht to be [Beneteau Oceanis 54](https://www.sailingtoday.co.uk/news/tested-beneteau-oceanis-yacht-54/). Few of the photos are exactly the ones in the website linked and in the site the photos are said to be taken in 07/07/2020, Marseille (FRA,13) Beneteau Oceanis Yacht 54, by [Gilles Martin-Raget](https://www.martin-raget.com/folio/2598/beneteau-oceanis-yacht-54.html).

**BUT** here comes the catch, none of the any location we can think of is the correct flag, including Marseille, France and names of the seas near Marseille. On the brink of going crazy, we decided to just put the four random letters inscribed on the yacht, 'OLAF', as the flag and suprisingly it was correct. 

Mind you, 'OLAF' doesn't reflect anything close to a location but instead is a name as discussed on the official website of the yacht. This directly shows how inconsiderate and ignorant the organisers are as they use four arbitrary letters as the flag while rendering the task description incoherent. 

¯\\\_(ツ)\_/¯


## Flag

    CDDC21{OLAF}
