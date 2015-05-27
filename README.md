##OSX Setup (From Scratch - Mavericks)

###Index
1. **Add Home Directory to the SideBar of Finder**
2. **Install and Setup Divvy**
3. **Install and activate Hyperdock**
4. **Install XCode Command Line tool**

<br>

1. **Add Home Directory to the SideBar of Finder**

   - Press `CMD+SHIFT+H` to enter your Home folder in Finder
   - Press `CMD+ArrowUp` to get into the Users folder
   - Drag the folder of your choice to the Sidebar

2. **Install and Setup Divvy**
   - Download Divvy from [http://mizage.com/divvy/](http://mizage.com/divvy/)
   - Click the Divvy icon shown on the upper right of your screen
   
     ![divvy](images/divvy.png)
   - Click the cogwheel icon and then click `License`. Enter the following details:

     ```
     Name:	JeffreyTang
     Code:	GAXAE-F9AXC-M5EAU-UFRKM-RPMMA-NYR9E-8ZPZ9-64JH9-A9KQB-VNRHM-DU6W6-T4Y68-XEPCL-UH76Y-V7B82-H4 
     ``` 
     
3. **Install and activate Hyperdock**
   - Download HyperDock from [http://hyperdock.bahoom.com/](http://hyperdock.bahoom.com/)
   - Activate by double clicking `jeffrey.tang09@gmail.com.hdlicense` in Finder

4. **Dock Settings**
   
   ![dock settings](images/dock_settings.png)

4. **Install XCode Command Line tool**

   `xcode-select --install`

5. **Install and Setup iTerm as Guake**

   - See [`iterm_setup.md`](iterm_setup.md)

6. **Install brew**

   `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

7. **Packages to install with brew**

   ```bash
   brew install wget
   brew install Caskroom/cask/java
   brew install maven
   brew install tmux
   brew install cowsay
   brew install mongodb
   ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents # Start mongo server on start up
   launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist # Launch mongo server now
   ```

8. **Install zsh**
 
   - `wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O - | sh`
   - Restart Shell to activate zshell

9. **Download PostGres App**
   - Go to [http://postgresapp.com/](http://postgresapp.com/)
   - Click **Download**
   - Double click Postgres.app
   - Add `/Applications/Postgres.app/Contents/Versions/9.4/bin` to your $PATH

10. **Install pip**
    - `sudo easy_install pip`

11. **Pip installs**
 
    ```bash
    sudo pip install -r requirements.txt
    ```
12. **Python package patches (Run in Python)**
    
    ```python
    import nltk
    nltk.download('all')
    ```
    
13. **Python package patches (Run in Bash)**

    ```
    sudo pip install numpy --upgrade
    sudo pip install pandas
    sudo pip install scipy --upgrade
    ```
        
13. **Install PyCharm / IntelliJ**
    - Log in [https://account.jetbrains.com/login](https://account.jetbrains.com/login)
    - Download professional versions PyCharm / IntelliJ
    - **Pycharm**
      - `Preferences -> Editor -> General -> Change font size (Zoom) with Ctrl+MouseWheel is enabled`
      - `Preferences -> Editor -> General -> Appearance -> Show line numbers`
      - `Preferences -> Editor -> Color & Font -> Theme`      
      - `Preferences -> Appearance & Behavior -> Appearance -> Theme`
      
