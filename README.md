# RVGM : Retro/Retropie Video Game Museum


![RVGM Logo](_art/system-logo.png)


- **XVGM** was an old project i've started in 2014 on the first XBOX. It was a video theme for **UnleashX** to launch Madmab and other emulators.
The *Xbox Video Game Museum* was abandoned because i have so many memory problems/crash and the xbox is now too old ... with old gamepad, no HDMI support, no real 1080p support, not enough power for some new systems like Nintendo DS, and so on.
Forum url : [EmuXtra](http://www.emuxtras.net/forum/viewtopic.php?f=289&t=1293)

- **RVGM** : *Retro/Retropie Video Game Museum* is the new project name, designed to work on PI with Retropie that use EmulationStation. It use a recent ES version, minimum **2.7.4** to use theme *variable*, *video* support, *caroussel* support, *thumbnail* support and so on.
The recent ES version also correct the old memory problems, now all is really better than on the old Xbox.
Forum url : [Retropie](https://retropie.org.uk/forum/topic/16454/rvgm-retro-video-game-museum-skin-in-developpement)


## General informations

This theme is designed to display most important information about systems and games, and support HD rendering up to 1080p.
For each game it display a big **front cover** with 720 pixel height, a **video preview** in 640 x 480 pixel, a **game title** with 400 pixel width and all the most important **game text informations** possible. 
The theme is build with percent size to auto fit your screen resolution. But it will be better if it use a 16/9 format.

The theme is also **multi language**, and you can switch from US to FR with only a *variable* to modify on the *theme.xml*.
I will also share the *description* and *informations* PSD files for people who want to help with other language like ES, DE, IT, and so on. We can add them to the main project.

* **1080p** / *720p* native resolution
* *Adaptive* percent object position
* **Multi languages**
* Separate *Background image*, big *Sprite*, *Logo*, machine *Photo* and information *text* for each system
* Front *cover*, *logo*, **video** preview and information *text* support for each game
* **Vectorial logo** for *player number* and multi-player *game style*

![RVGM system screen](https://retropie.org.uk/forum/assets/uploads/files/1519069059766-cps-720-us-resized.jpg)

## Not supported systems by Retropie (10/03/2018)

- Apple 2e
![RVGM Apple 2e](https://retropie.org.uk/forum/assets/uploads/files/1521063978162-apple2e.jpg)
- Apple 2gs
![RVGM Apple 2gs](https://retropie.org.uk/forum/assets/uploads/files/1521063993634-apple2gs.jpg)
- Supervision, Watara
![RVGM Supervision, Watara](https://retropie.org.uk/forum/assets/uploads/files/1521064024576-supervision.jpg)
- Creativision : Maybe trying with **lr-mess** driver **crvision** : 80-100% speed
![RVGM Creativision](https://retropie.org.uk/forum/assets/uploads/files/1521063998237-creativision.jpg)
- Interton VC4000 : Maybe trying with **lr-mess** driver **scv**
![RVGM Interton VC4000](https://retropie.org.uk/forum/assets/uploads/files/1521064038911-vc4000.jpg)
- Amstrad GX4000 : Maybe trying with **lr-mess** driver **gx4000** : **65%** speed, some games still feel very playable
![RVGM Amstrad GX4000](https://retropie.org.uk/forum/assets/uploads/files/1521064016743-gx4000.jpg)

I include a readme file in these systems to explain how to use with **MESS**.

### Prerequisites

You must use it on a PI with the [Retropie](https://retropie.org.uk/) system installed on you MicroSD.

You can find the **es_systems.cfg** used by EmulationStation to show *system list* here :

```/opt/retropie/configs/all/emulationstation/es_systems.cfg```

And you can find the **gamelist.xml** used to show *games informations* here :

```/opt/retropie/configs/all/emulationstation/gamelists/ SYSTEM NAME / gamelist.xml```

If you want to modifiy the systems order, or the games informations, you must modify these files on your PI.


### Installing

- Download the theme [here](https://github.com/Darknior/RVGM/archive/master.zip)
- Unpack it to your computer
- Upload it to your pi by SSH with for exemple [WinSCP](https://sourceforge.net/projects/winscp/) here :

```/etc/emulationstation/themes/RVGM```

- Restart your EmulationStation
- And choose it on the theme selection menu


### Customising

You can customise some options on this theme.

- Change the **language** on the master *theme.xml* file by switching one variable.

```
  <variables>
    <langue>us</langue>    <!-- fr / us    ${langue}    Translate ES -->
  </variables>
```

- Display or not the **help** information bar in the *game selection* screen, to have a biger *description size* and 2 more games display on the *game list*.

```
    <include>./_art/nohelp.xml</include>    <!-- help / nohelp    Bottom help bar on game selection screen -->
```

- Display the **Player number** and the game **Multiplayer style**. For this special RVGM feature i designed a special font to replace letters and numbers by better *icons* i've created for. You can use normal numbers and text by replacing the font like this :

```
  <text name="md_players">
    ...
    <fontPath>./_art/Players.ttf</fontPath>    <!-- Replace by Roboto-Bold.ttf -->
    <fontSize>0.09</fontSize>
    ...
  </text>
```

![RVGM Multiplayer style](https://retropie.org.uk/forum/assets/uploads/files/1519648544191-sans-titre-2.jpg)

But if you want to use them, you must respect these two rules.
Only one number on the **players** tag. No *1-2* players and other text. Only :

```
<players>1</players>
<players>2</players>
<players>4</players>
```
And for the **multiplayer style**, 3 words are available: *Alt, Coop, Versus* with the Upercase first letter. You will see them when you will use the ES player filter option. On game selection screen letters *l t o p s* will be hide. First **upercase** letter will be replace by the icon and if you use **lowercase** letter i have also include an alternative logo for *Vs* and *Coop*.

```
<players>2 Alt</players>   <!-- Alternative player game, for scorring battle -->
<players>2 Coop</players>  <!-- Real 2 player game in cooperative mode like Sonic 3 -->
<players>5 Vs</players>    <!-- Versus game in battle mode, like Street Fighter 2 or here Bomberman -->
```
![RVGM Multiplayer icons](https://retropie.org.uk/forum/assets/uploads/files/1519352342645-sans-titre-2.jpg)


## Built With

* [Photoshop](https://www.adobe.com/fr/products/photoshop/free-trial-download.html) - Use to create images
* [Notepad++](https://notepad-plus-plus.org/) - Use to write XML code
* [Webtropie](https://github.com/gazpan/WebtroPie) - Used to generate XML informations

Webtropie is a fantastic EmulationStation editor designed for Retropie. You can use it to manage all your games and media. I try to help the developer **Gazpan** to improve it.
And now he include a theme editor that help me to release mine. To place my images and test my code with my Webroser on PC and save me many time...


## Contributors

* **Gazpan** with Webtropie


## Authors

* **Darknior** - *Initial work* - Release the theme


## License

This project is licensed under the GNU GENERAL PUBLIC LICENSE - see the [LICENSE](LICENSE) file for details

