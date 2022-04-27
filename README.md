# News Ticker Program

| entry            | value                  |
| ---------------- | ---------------------- |
| customer |MRS|
| projectnumber (SAP) ||
| drawing number ||
| quotation number ||
| platform |Linux, Windows|
| target hardware |none|
| first contact |Maham Qureshi|
| second contact |Umer Farooq|


## Project Description 
OpenCV program that generates "News Ticker" on any video given by the user. The user will give "N" number of news text description. The scrolling speed of the text is adjusted in a way that all the news tickers complete by the end of the video.

## Getting Started
### Prerequisities
This main program is a python script. It requires some libraries to be installed within the Python environment you are running this script in.
* OpenCV
* numpy
* moviepy.editor
* pydub


### Setup, Building, Testing and Debugging
Create  a separate python environment on Linux / Windows , install the following libraries: 
* OpenCV
```bash
$ python --version   # If python is already installed, then it's version will be displayed otherwise install python first
$ pip -V             # If pip is already installed then it's version will be displayed otherwise you need to install pip 
$ pip install opencv-python
```
* numpy 
```bash
$ pip install numpy
```
* moviepy.editor
```bash
$  (sudo) pip install moviepy
```
* pydub
```bash
pip install pydub
```

### Using the Application
We need to provide 
two arguments while running the main.py file.
1. path to video file
2. path to news headings text file
The output video with news ticker will be saved by the name of "news_ticker_video.mp4" in the video folder. 
