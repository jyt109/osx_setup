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

6. **Install gfortran** 

   - Download relevant dmg from [https://gcc.gnu.org/wiki/GFortranBinaries#MacOS](https://gcc.gnu.org/wiki/GFortranBinaries#MacOS)

7. **Install XQuartz**

   - Download the relevant dmg from [http://xquartz.macosforge.org/landing/](http://xquartz.macosforge.org/landing/)

8. **Download PostGres App**
   - Go to [http://postgresapp.com/](http://postgresapp.com/)
   - Click **Download**
   - Double click Postgres.app
   - Add `/Applications/Postgres.app/Contents/Versions/9.4/bin` to your $PATH

9. **Install brew**

   `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

10. **Packages to install with brew**

   ```bash
   brew install wget
   brew install Caskroom/cask/java
   brew install maven
   brew install tmux
   brew install cowsay
   brew install postgis
   brew install osm2pgsql
   brew install graphviz
   brew link --overwrite gcc
   brew tap homebrew/science
   brew install r
   brew install mongodb
   ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents # Start mongo server on start up
   launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist # Launch mongo server now
   ```

11. **Install zsh**
 
    - `wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O - | sh`
    - Restart Shell to activate zshell


12. **Install pip**
    - `sudo easy_install pip`

13. **Pip installs**
 
    ```bash
    sudo pip install -r requirements.txt
    sudo easy_install --upgrade numpy
    sudo pip install pandas
    sudo rm -rf /System/Library/Frameworks/Python.framework/Versions/2.7/Extras/lib/python/scipy
    sudo pip uninstall scipy
    sudo pip install scipy # Should be the lastest scipy
    sudo pip install scikit-image
    sudo pip install scikit-learn
    sudo pip install setuptools --upgrade # have to upgrade setuptools before gensim install
    sudo pip install gensim
    pip install PIL  --allow-unverified PIL --allow-all-external # For wordcloud
    ```

14. **Install Lasagne and Nolearn**
    
    ```bash
    cd ~
    git clone https://github.com/Lasagne/Lasagne.git
    cd Lasagne
    pip install -r requirements.txt
    sudo python setup.py install
    sudo pip install -U -r https://raw.githubusercontent.com/dnouri/kfkd-tutorial/master/requirements.txt
    # Don't delete Lasagne at ~
    ```

15. **Install statsmodels 0.7dev**

    ```bash
    git clone https://github.com/statsmodels/statsmodels.git
    cd statsmodels
    python setup.py build_ext --inplace
    sudo python setup.py install
    ```
 
16. **Download opencv**
    ```bash
    brew install opencv
    ln -s /usr/local/Cellar/opencv/2.4.11_1/lib/python2.7/site-packages/cv.py cv.py
    ln -s /usr/local/Cellar/opencv/2.4.11_1/lib/python2.7/site-packages/cv2.so cv2.so
    ```
        
17. **Download NLTK data**
    
    ```python
    import nltk
    nltk.download('all')
    ```

18. **Install boilerpipe**
    ```bash
    cd ~
    git clone https://github.com/originell/jpype.git
    cd jpype
    sudo python setup.py install
    sudo pip install bolierpipe
    ```
    
19. **Install PySpark**

    ```bash
    cd ~
    wget http://d3kbcqa49mib13.cloudfront.net/spark-1.3.1-bin-hadoop1.tgz
    tar -xzvf spark-1.3.1-bin-hadoop1.tgz    

    # Add the following lines to ~/.zshrc
    export SPARK_HOME=/Users/jeffreytang/spark-1.3.1-bin-hadoop1
    export PYTHONPATH=$PYTHONPATH:/Users/jeffreytang/spark-1.3.1-bin-hadoop1/python/
    ```
20. **Install PyCharm / IntelliJ**
    - Log in [https://account.jetbrains.com/login](https://account.jetbrains.com/login)
    - Download professional versions PyCharm / IntelliJ
    - **Pycharm**
      - `Preferences -> Editor -> General -> Change font size (Zoom) with Ctrl+MouseWheel is enabled`
      - `Preferences -> Editor -> General -> Appearance -> Show line numbers`
      - `Preferences -> Editor -> Color & Font -> Theme`      
      - `Preferences -> Appearance & Behavior -> Appearance -> Theme`

21. **Install Cassandra**

    ```bash
    wget http://psg.mtu.edu/pub/apache/cassandra/2.1.5/apache-cassandra-2.1.5-bin.tar.gz
    tar -xzf apache-cassandra-2.1.5-bin.tar.gz
    cd apache-cassandra-2.1.5/bin
    sudo ./cassandra
    ./cqlsh
    ```
    
22. **Install igraph**
    ```bash
    brew install igraph
    sudo pip install python-igraph
    ```
    
23. **Install graph-tool**
    - `brew install graph-tool #Takes 30 mins to an hour`
    - `mkdir -p /Users/jeffreytang/Library/Python/2.7/lib/python/site-packages`
    - `echo 'import site; site.addsitedir("/usr/local/lib/python2.7/site-packages")' >> /Users/jeffreytang/Library/Python/2.7/lib/python/site-packages/homebrew.pth`    

22. **Install pyqt (for ete2 plotting)**

    ```bash
    brew install sip
    brew install pyqt
    ```

    ```python
    # Testing if pyqt4 is installed properly
    from ete2 import Tree
    t = Tree( "((a,b),c);" )
    t.show()
    ```


