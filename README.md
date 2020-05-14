# ffmpeg-python-wrapper
ffmpeg-python-wrapper is a lightweight python binder built for the FFmpeg library. Unlike most of the other Ffmpeg python bindings,
ffmpeg-python-wrapper supports a limited set of ffmpeg tools designed for quick and easy video & music editing with very clear 
python syntax.

## Prerequisites
You need FFmpeg to be installed on your computer. If not, please follow the instructions below to get it. 

#### Installing FFmpeg in Windows
1. Download a static build from [here](http://ffmpeg.zeranoe.com/builds/).
2. Use [7-Zip](http://7-zip.org/) to unpack it in the folder of your choice.
3. [Open a command prompt with administrator's rights](Just-Enough-Command-Line-for-Installing).  
<b>NOTE: Use CMD.exe, do not use Powershell!</b> The syntax for accessing environment variables is different from the command shown in Step 4 - running it in Powershell will overwrite your System PATH with a bad value.
4. Run the command (see note below; in Win7 and Win10, you might want to use the Environmental Variables area of the Windows Control Panel to update PATH):  
``setx /M PATH "path\to\ffmpeg\bin;%PATH%"``  
**Do not run setx if you have more than 1024 characters in your system PATH variable. See <a href="https://superuser.com/questions/387619/overcoming-the-1024-character-limit-with-setx">this post on SuperUser</a> that discusses alternatives.**
Be sure to alter the command so that ``path\to`` reflects the folder path from your root to ``ffmpeg\bin``.  
(<a href="http://www.wikihow.com/Install-FFmpeg-on-Windows" target="_blank">Here's another explanation with pictures.</a>)

#### Installing FFmpeg in OS X  
Here are a couple of links to instructions:  
<a href="http://www.idiotinside.com/2016/05/01/ffmpeg-mac-os-x/" target="_blank">http://www.idiotinside.com/2016/05/01/ffmpeg-mac-os-x/</a>  
<a href="http://macappstore.org/ffmpeg/" target="_blank">http://macappstore.org/ffmpeg/</a>

#### Installing FFmpeg in Ubuntu

    sudo add-apt-repository ppa:mc3man/trusty-media  
    sudo apt-get update  
    sudo apt-get install ffmpeg  
    sudo apt-get install frei0r-plugins  

Helpful links for Ubuntu users:
http://wiki.razuna.com/display/ecp/FFmpeg+Installation+for+Ubuntu#FFmpegInstallationforUbuntu-Installlibfdk-aac  
http://www.webupd8.org/2014/11/ffmpeg-returns-to-official-ubuntu.html  
http://linuxg.net/how-to-install-ffmpeg-2-6-1-on-ubuntu-15-04-ubuntu-14-10-ubuntu-14-04-and-derivative-systems/  
http://ffmpeg.org/download.html  
http://askubuntu.com/questions/432542/is-ffmpeg-missing-from-the-official-repositories-in-14-04  

## Usage Examples

#### Creating a subclip of a video 
``` 
video = Media('path_to_video')
video.subclip(10,30)
```

#### Setting duration 
```
music = Media('path_to_music')
music.set_duration(80)
```

#### Looping Video
```
video = Media('path_to_video')
target_duration = 120
video.loop(target_duration)
```

#### Reshaping Media
```
image = Media('path_to_image')
new_size = [720,360]
image.set_size(new_size)
```

## Contributing
This project is in the very early stages of development. Please feel free to fork the repository and mess around with it.

- <b>For small changes,</b> please open a pull request
- <b>For larger changes,</b> please start an issue so other people can weigh in. Otherwise, feel free to contact me at my email.

## License
This project is licensed under the MIT License - see the LICENSE.md file for details


