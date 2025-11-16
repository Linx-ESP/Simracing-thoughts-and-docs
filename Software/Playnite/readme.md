## Adding wheel as controller to fullscreen mode
Compliments [Playnite documentation](https://api.playnite.link/docs/manual/gettingStarted/playniteFullscreenMode.html#controller-support)
### Using my mapping (only GT Neo)
  
- Edit `%localappdata%/Playnite/gamecontrollerdb.txt`
- Add the following line (careful with the commas, might need to remove the ending one or put one prior):
  ```
  03003e10703600000508000000000000,GT Neo,a:b7,b:b8,x:b2,y:b1,back:b3,guide:b25,start:b6,leftshoulder:b0,rightshoulder:b9,leftshoulder:b13,rightshoulder:b12,leftstick:b17,rightstick:b25,dpup:b28,dpleft:b24,dpdown:b27,dpright:b29,-leftx:b16,+leftx:b22,-lefty:b21,+lefty:b19,platform:Windows,
  ```

<img width="722" height="404" alt="Sin título" src="https://github.com/user-attachments/assets/8eb3261e-1acf-4bdd-97d8-d39233a0d396" />

### Create a new mapping

- Use [SLD gamepad mapper](https://gitlab.com/ryochan7/sdl2-gamepad-mapper/-/releases)

## Launch scripts
Compliments [Playnite documentation](https://api.playnite.link/docs/manual/features/scriptingSupport/exampleScripts.html#starting-additional-applications-before-game-starts-and-killing-it-after-game-exits)
### General simracing
#### Open SimHub

Pre or post launch:  
``` pwsh
Start-Process -FilePath "C:\Program Files (x86)\SimHub\SimHubWPF.exe" -WorkingDirectory "C:\Program Files (x86)\SimHub"
```

### Game specific
#### RaceRoom Racing Experience
Open [dash.exe for custom overlay](https://github.com/sealhud/sealhud.github.io):  
- Pre or post launch
  - Don't launch if already running because it won't work
  - Change path to dash.exe
``` pwsh
if (!(Get-Process -Name "dash" -EA 0))
{
     Start-Process -FilePath "C:\path\to\dash.exe" -WindowStyle Minimized
}
```
- Exit
``` pwsh
Stop-Process -Name "dash"
```

