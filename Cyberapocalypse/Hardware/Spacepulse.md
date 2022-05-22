## Title: Spacepulses

#### Category: Hardware
#### Challenge Files: hw_space_pulses.zip 


We were given a zip file as part of this challenge and told to figure out a message that was coming from deep space. Unziping our challenge reveals a .sal file inside.


A .sal file is a sort of zip archive file that contains a json file inside along with a binary file. Usually, .sal files contain signals that can be read by Saleae Logic Analyzers. 


<p align="center">
<img src=https://user-images.githubusercontent.com/73745039/169673936-f76a23bf-f4e7-43b8-a07b-d5f6e9e6e7f0.PNG>
</p>


Downloading and opening this up in the Saleae Logic Analyser, we can see our space pulses!


<p align="center">
<img src=https://user-images.githubusercontent.com/73745039/169674762-57870001-ba2e-4a38-8ce1-bdcdc3105e48.PNG>
</p>


For someone who has never analysed signals before, these are standard digital signals. When the signal is "up" it is a binary 1, when it is "down" it is a binary 0. Its through these signals that many computers, IOT devices and the like communicate, and the first thing you usually do with a signal like this is trying to understand its baud rate and what communication protocol it is.

A baud rate is just the rate at which bits are sent, which in this case was quite off because the signal was pretty damn irregular and it matched none of the communication protocols I was familiar with.

A closer manual investigation revealed something interesting however:

<p align="center">
<img src=https://user-images.githubusercontent.com/73745039/169675026-d2dd3729-0603-4080-8918-7122bf9b51ef.PNG>
</p>

I noticed that the "ups" in the signal were familiar. 110, 114, 97... these are ascii values! So I decided to collect all the timing values from the signals (you can export these values using the Saleae logic analyser) and pass them directly tp ascii. 

And I got the flag:

<p align="center">
<img src=https://user-images.githubusercontent.com/73745039/169675063-5e61bb43-f9e4-4f74-8c4f-c68a9e11a974.PNG>
</p>

