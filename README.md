# gwenWithMaven
### Automated gwen using maven

###### Steps to build the project

1. Clone the project

2. With this POM and your Gwen settings in place you can have Maven download, install, and launch the latest version of Gwen with the following command (where <args> is a space separated list of arguments that you want to pass to Gwen):
   
   **mvn verify -Dgwen.args=\"\<args\>\"**
   
   So if your executable tests are in a folder named ‘features’ relative to your POM file, then you can execute them with a Maven command like this:
   
   **mvn verify -Dgwen.args="features"** 
  
   And to also generate html and junit style reports in the target/reports folder..
   
   **mvn verify -Dgwen.args="-ret/reports -f html,junit features"**
   
   Similarly, any arguments can be passed to Gwen in this manner through the gwen.args -D command line argument. Note that the -b batch mode switch is implicitly passed to Gwen and therefore you do not need to explicitly specify it as an argument. The gwen profile will only be activated if gwen.args is specified in the call to Maven.
   
 3. To run wth particular properties file
 
    **mvn verify -Dgwen.args="-r reports -f html,junit -p \"gwen.properties\" features/floodio"**

4. To run with particular tag,

    **mvn verify -Dgwen.args="-r reports -f html,junit -p \"gwen.properties\" -t \"@Robot\" features/floodio"**
     
    you can give multiple tags as per cucumber rules
