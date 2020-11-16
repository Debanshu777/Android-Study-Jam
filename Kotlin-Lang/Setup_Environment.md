# Steps to Set-Up the Environment

- ## Installing the Java Development Kit (JDK)
  If you don't have the latest JDK already installed on your computer, follow the steps below. You will need to have the JDK installed to run Kotlin programs.
  The JDK is freely available, and you can download it here:<br>
  <a href="http://www.oracle.com/technetwork/java/javase/overview/index.html">http://www.oracle.com/technetwork/java/javase/overview/index.html</a><br>
  For Video Reference:<br>
  <a href="https://www.youtube.com/watch?v=DTZAz9rj0kU">https://www.youtube.com/watch?v=DTZAz9rj0kU</a>
  #### The JDK or the JRE?
    The JRE (Java Runtime Environment) is needed for running Java and Kotlin programs. The JDK (Java Development Kit), on the other hand, includes the JRE, plus the development tools you'll need for writing and running Java programs. You need the JDK for writing Kotlin Programs.
  ### Steps to install the JDK:
    - #### Uninstall any older versions of the JDK/JRE
      We recommend that you install only the latest JDK.
    - #### Download the JDK
      You can download the JDK for free here:<br>
      <a href= "http://www.oracle.com/technetwork/java/javase/downloads/index.html">http://www.oracle.com/technetwork/java/javase/downloads/index.html</a>
      <br>
      1. Click the "Download" button under the JDK for the latest Java SE version.
      2. Check "Accept License Agreement".
      3. Choose the JDK for your operating system.
    - #### Install the JDK:
      <b>(for Mac)</b><br>
      From either the Downloads window of the browser, or from the file browser, double-click the .dmg file to launch the install file.
      1. A Finder window appears with an icon of an open box and the name of the .pkg file.
      2. Double-click the package icon to launch the Install app, and follow the prompts as they appear.
      3. You might need to enter the administrator password to continue.
      4. Feel free to delete the .dmg file to save space after the installation is complete.<br>
      <br>
      <b>(for Windows)</b><br>
      Run the downloaded installer (e.g., jdk-10.0.x_windows-x64_bin.exe), which installs both the JDK and the JRE.<br>
      By default, the JDK will be installed in the directory "C:\Program Files\Java\jdk-10.0.x", where x denotes the version number; and the JRE in "C:\Program Files\Java\jre-10.0.x".<br>
      Accept the defaults, and follow the screen instructions to install the JDK.
    - #### Add the JDK installation path to PATH (Windows only):
      Windows searches the current directory and the directories listed in the PATH environment variable (system variable) for executable programs.
      1. Open "Control Panel" -> "System" -> "Advanced system settings" -> "Environment Variables".
      2. Under "System variables", scroll down to select "Path" and click "Edit...".
      3. Append to the existing Path value a semi-colon ";" then the JDK's "bin" directory (e.g. ";C:\Program Files\Java\jdk-10.0.0\bin").
- ## Install IDE for Development(IntelliJ or Android Studio):
  ```
  Prefered is Android Studio as it is required for your journey as Android developer.
  ```
  - ### Download and Install IntelliJ IDEA
    Reference Video:<br>
    <a href="https://www.youtube.com/watch?v=Dmswd4uN0jk">https://www.youtube.com/watch?v=Dmswd4uN0jk</a><br>
    <a href="https://www.jetbrains.com/idea/download/">Download IntelliJ IDEA</a> for your operating system.
    Do the following, depending on your operating system:
    <br>
    <b>Windows:</b><br>
      1. Run the ideaIC.exe or the ideaIU.exe file you have downloaded.
      2. Follow the instructions in the installation wizard.
    <br>
    <b>Mac:</b><br>
      &nbsp&nbsp&nbspa. Double-click the ideaIC.dmg or ideaIU.dmg file you have downloaded to mount the macOS disk image.<br>
      &nbsp&nbsp&nbspb. Copy IntelliJ IDEA to the Applications folder.
    <br>
  - ### Download and Install Android Studio
    Reference Video:(Refer only to the installation part)<br>
    <a href="https://www.youtube.com/watch?v=0zx_eFyHRU0">https://www.youtube.com/watch?v=0zx_eFyHRU0</a><br>
    Refer to the official Docs:<br>
    <a href="https://developer.android.com/studio/install">https://developer.android.com/studio/install</a><br>
    This is assuming you already have Android Studio and Java SDK installed from above instructions.
    In order to ensure Android Studio support Kotlin, the first thing is to install the Kotlin Plugin for your Android Studio.
    ```
    Open Android Studio -> Configure(Bottom Right) → Settings →Plugins → Marketplace → type “Kotlin” in search box → Install
    ```

    
