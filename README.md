# Wikimedia Wallpaper Manager

## About

Wikimedia Wallpaper Manager is a simple script based on [vyshuks](https://github.com/vyshuks)' wiki-wallpaper script to set and manage pictures from the "Picture of the day" section of [Wikimedia Commons](http://commons.wikimedia.org). 

## Requirements

- Python3
- feh

### Python modules

- beautifulsoup4 (4.8.0)
- certifi (2019.6.16)
- chardet (3.0.4)
- idna (2.8)
- requests (2.22.0)
- soupsieve (1.9.3)
- urllib3 (1.25.3)
- unicode

## Usage

By default, all images will be downloaded in the following folder:
```
/users/{USER}/Pictures/wiki-wallpapers
```

### Preview today's picture of the day

To preview the picture of the day, just launch with the argument "-p" ("--preview")

```bash
$ wikimedia-wallpaper -p
```

The program will attempt to open the image using feh.

### Set today's wallpaper

By launching the script without any arguments, it will download the picture of the day to your wallpapers folder. It will be saved as "current-wallpaper.jpg"

```bash
$ wikimedia-wallpaper
```

### Save the wallpaper for later use

Since the script is supposed to run daily, it will always overwrite the file "current-wallpaper.jpg". If you like an image and would like to save it for later use, relaunch the script with the "-s" ("--save") argument. 

The "-s" ("--save") argument will make a copy of the current wallpaper image (current-wallpaper.jpg). 

```bash
$ wikimedia-wallpaper -s 
>> Describe the image using just a couple of words: 
```
The script will then wait the user's input to generate a file name. Do not insert a file name! 

i.e. the input "snowy trees" will generate the file name "snowy-trees.jpg"

### Temporarily set a previously downloaded image as wallpaper

If you don't like the picture of the day, you can always set a previously saved image as wallpaper. This is possible by using the "-c" ("--custom") argument

```bash
$ wikimedia-wallpaper -c
>> Type the exact file name of the picture you'd like to set as wallpaper:
```
The script will wait the user's input to set the wallpaper.

## Tips

To launch the program like a normal shell script without having to invoke python, just add Python's path to your shell rc file (i.e. .bashrc or .zshrc)

Example:

```bash
export PATH=/usr/bin/python3:$PATH
```
