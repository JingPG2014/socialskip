# Installing SocialSkip #

This article will show you how to compile and run SocialSkip on your computer using the Eclipse IDE.


---


# Prerequisites #

SocialSkip is a web application designed to run on Google App Engine therefore to change and experiment with the source code you have to prepare your computer for compiling and running GAP applications.

Here is a list of what you need
  * JDK 5 or JDK 6 (Google App Engine supports only Java 5 and Java 6...)
  * Eclipse IDE for Java Developers
  * Google App Engine SDK for Java
  * Google Plugin for Eclipse

## JDK ##

If you have already installed a JDK on your computer make sure it is version 5 or 6 otherwise your GAP projects will not run.  To check your JDK version locate the java compiler and in the command-line of your operating system type `javac -version` (Make sure you are in the correct folder).

This command will print on your screen your JDK version. You should see something like these

> "_javac 1.5.x\_x_" for JDK 5

> "_javac 1.6.x\_x_" for JDK 6

If your JDK is older or newer then you should download and install JDK 6 ([Java SE Downloads](http://www.oracle.com/technetwork/java/javase/downloads/index.html)). In the rest of this article we will assume that you have JDK 6 (1.6.x) installed on your computer.

## Eclipse IDE ##

At this time there is a Google Plugin for each of the following Eclipse versions
  * 4.2 (Juno)
  * 3.7 (Indigo)
  * 3.6 (Helios)
  * 3.5 (Galileo)
If you don't have Eclipse IDE or your IDE's version doesn't match the above versions you can download an appropriate version from here "[Eclipse Downloads](http://www.eclipse.org/downloads/)".

## Google Plugin for Eclipse & Google App Engine SDK ##

For instructions on how to install the Google Plugin for Eclipse and the Google App Engine SDK directly from you Eclipse IDE visit the following page "[Downloading and Installing the Plugin](http://code.google.com/eclipse/docs/download.html)".

> _Note! If you're having trouble installing the Google Plugin try running Eclipse as administrator._


---


# Importing SocialSkip to Eclipse #

If your computer matches the above requirements then you are ready to compile and run SocialSkip.
First download the SocialSkip source code from the "[Downloads](http://code.google.com/p/socialskip/downloads/list)" section.

After downloading the source code archive extract it's contents and open the Eclipse IDE.

From the "File" menu click the "Import..." option. On the appearing dialog select "General > Existing Projects into Workspace" and press the "Next" button.

If it's not already selected, check the "Select root directory" option and use "Browse..." to find the extracted archive. Then Eclipse will automatically detect the project and will add it to the Projects list below.

Check or uncheck the "Copy projects into workspace" option according to your needs and click on the "Finish" button.

Now you should be able to see the SocialSkip project in the project/package explorer.

Eclipse will automatically compile the project for you. If there are errors during this process then a small red "X" icon will appear beside your project's name and beside every file that Eclipse can't compile. If so consult the [Troubleshooting](Installation#Troubleshooting.md) section of this article. If  there are no errors then you are ready to run SocialSkip.

To run SocialSkip just right click on the project's name in the package explorer and select the "Run As > Web Application" option. Now SocialSkip should be running and you should see the following message in the Eclipse Console.

`INFO: The server is running at http://localhost:8888/`

To see SocialSkip in action just open this address with your internet browser.


---


# Troubleshooting #

If Eclipse can't compile the "`.jsp`" files of the project then you probably have other JREs or JDKs installed on your system along with JDK 6. If so, you have to configure Eclipse to compile SocialSkip with the appropriate JDK.

First of all make sure that Eclipse is aware of your JDK 6 existence. To check this go to the "Window" menu and click on the "Preferences" option. Then expand the "Java" item and click on the "Installed JREs". In the appearing list you should see "`jdk1.6.x`". If no, then add your JDK to the list by clicking to the "Add..." button and following the "Add JRE" wizard.

After adding your JDK to Eclipse close the "Preferences" dialog and right click on the SocialSkip project in the package explorer. Select the "Properties" option (should be the last option in the pop-up menu) and go to "Java Build Path". By selecting the "Libraries" tab you should see these two items.
  * App Engine SDK [...]
  * JRE System Libraries [...]
If in the brackets of the JRE System Libraries item is not jdk1.6.x then you have to remove this item from the list and add the JDK 6 libraries to the project. To do so press the "Add Library..." button, select "JRE System Library" and in the following screen select jdk1.6.x. If jdk1.6.x is not your default JRE then you will find it in the Alternate JREs list.

Now your project will use the JDK 6 libraries but there is one more step before you are ready to work with SocialSkip. You have to set the compiler compliance level to 1.6 . To the project properties dialog select the "Java Compiler" tab, check the "Enable project specific settings" option and from the "Compiler compliance level" drop down list select "1.6".