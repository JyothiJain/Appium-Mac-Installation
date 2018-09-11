# Appium-Mac-Installation

## **This is all we need for appium**

# 1.Xcode with latest version(Appium uses it to run ios tests)

     Steps: 1.Open app store on your macbook(Keys:cmd+space and type app store in the search box & press enter), search for Xcode and click the Get button.
            2.Download and complete the installation
            

# 2.Homebrew (simplifies the installation of softwares)

     Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
            2.Provide the command /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" and press enter.
            3.Test install by running $ brew --version.You should see something like Homebrew 1.7.4. 
         

# 3.Carthage (dependency check for appium-doctor but not really needed for Android. Install it anyway as you may do iOS automation in the future)

     Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter).
            2.Provide the command: brew install carthage and press enter.


# 4.Java (Programming Language)

    Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
           2.Provide the command: java -version and press enter (If the version is less than 1.8 or the command is not recognized you will have to install java by providing the command: brew install homebrew/cask-versions/java8 and press enter).
           
           

 # 5.Node (helps in parallelization)

    Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
           2.Provide the command: brew install node and press enter
           3.Test install by providing the command: npm --version. Verify version 5.6.X or greater is returned.
           
           

 # 6.Android Studio & Android SDK(helps in easy setup of sdk and setting system images required for creating emulator)
 
     **Android Studio Download & Installation Steps** 
     
           1.Open https://developer.android.com/studio/#mac-bundle to download.
           2.Open downloads folder from the Finder present in dock and double click on the Android Studio DMG file.
           3.Drag and drop the Android Studio icon over to Applications folder. Close the install dialog.
           4.Open Finder and goto Applications folder. Double click Android Studio.
           5.Select "I do not have a previous version of studio or I do not want to import my settings" and click on OK button.
           6.Click Next.
           7.Select Standard Installation and click the Next button.
           8.Click on the Finish button.
           9.Enter password to allow HAXM to make changes to your system. HAXM is very import for emulator perforamce.
           10.Click the Finish button.
           
     **Android SDK Download & Installation Steps**
     
           1.Open Android Studio from the Finder>>Applications folder
           2.Click on the Configure button. It's on the lower right side of the Android Studio welcome dialog.
           3.Click on the SDK Manager in the configuration dropdown.
           4.Select Android 6.0 (Marshmallow) SDK.(Why Android 6.0? It's the most common SDK version used throughout the world and we can use it just to begin with mobile automation and later add the rest based on requirements)
           5.Click on the "Show Package Details" checkbox on lower right.
           6.Check on the following SDK dependencies to install:
           
                   a.Android SDK Platform 23
                   b.Sources for Android 23
                   c.Intel x86 Atom System Image.
                   d.Intel x86 Atom_64 System Image.
                   e.Google API's Intel x86 Atom System Image
                   f.Google API's Intel X86 Atom_64 System Image
                   g.Click the Apply button.
                   
          7.On the next screen click the Accept radio button.
          8.Take note of your SDK Path! It's at the top of the Component Installer dialog. e.g SDK Path: /Users/YourUser/Library/Android/sdk
          9.Click on the Next button to start the installation of SDK 23 dependencies.It will take sometime, when everything is completed, click on the Finish button.
          10.Click on the OK button to close the Component Installer dialog.
          11.Close the Android Studio.



# 7.Add Environment Variables and test them(Environment variables are set to allow access to command line tools and to enable other tools to interact with SDKs more easily)
 
        Steps: 1.First determine which shell you use. Open a terminal(Keys:cmd+space and type terminal in the search box & press enter) and provide the command: echo $SHELL
               2.Based on your shell, you need to edit your profile. e.g.vim ~/.bash_profile or ~/.profile or ~/.zshrc and press enter
               3.Add the following variables by pressing i(this will change the mode of file to insert mode).
               
                      a.export ANDROID_HOME=//Users/YourUser/Library/Android/sdk  (Note:YourUser here means your username e.g. ANDROID_HOME=//Users/Steve/Library/Android/sdk)
                      b.export JAVA_HOME=$(/usr/libexec/java_home)
                      c.export PATH=$PATH:$ANDROID_HOME/platform-tools
                      d.export PATH=$PATH:$ANDROID_HOME/tools
                      e.export PATH=$PATH:$ANDROID_HOME/build-tools
                      
               4.Save profile by pressing esc button then press : and type wq & press enter.(i.e. esc + : + wq &  press enter which will save the file and closes it)       
               
               

# 8.Test adb-Android Debug Bridge(command line tool that lets us communicate with an Android device or an Emulator)

         Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
                2.Provide the command: adb and press enter, you will see Android Debug Bridge version 1.0.39 or greater along with additional menu options.
                
         

# 9.Create & test Emulator(virtual device used to run tests)

        Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
               2.Provode the command: android create avd -n EmulatorOne -k "system-images;android-23;google_apis;x86" and press enter
               3.Enter NO to not create a custom hardware profile.
               4.Change the directory where the emulator is present by providing the command:
                       cd Users/YourUser/Library/Android/sdk/tools and press enter
               5.To start the emulator provide the command: emulator -avd EmulatorOne and press enter, please verify avd output on startup includes the below:
                        a.Hax is enabled
                        b.HAX is working and emulator runs in fast virt mode.
                        c.Verify emulator fully starts and you see the android home/desktop screen.
               
 

# 10.Appium-Install via Desktop (used to start or stop the appium server)

    
       Steps: 1.Download and install Appium Desktop by clicking on the link:   https://download.sublimetext.com/Sublime%20Text%20Build%203143.dmg
       
       
       Note: We can also install appium via terminal using npm(provide the command: npm install -g appium, verify appium installed correctly by providing the command: appium -v)
         

# 11.Appium doctor -Install & test (Attempts to diagnose and fix common Node, iOS and Android configuration issues before starting Appium)


      Steps: 1.Open a terminal(Keys:cmd+space and type terminal in the search box & press enter)
             2.Provide the command: npm install -g appium-doctor and press enter
             3.Provide the command: appium-doctor (checks setup is correct on machine)
                  a.Verify "info AppiumDoctor Everything looks good, bye!" is displayed.
                  b.If there are things missing please go back to the install instructions above or environment variable setup.




