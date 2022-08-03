## Atakama Variabilization Plugin  :

This plugin aims to assist the jmeter developper during the script development. 
By putting it inside a thread Group with a module controller, it can go through all the samplers that are subelements of the module controller

![image](https://user-images.githubusercontent.com/2484866/182611112-19605d2d-40e1-4cf4-a114-0e2dfe54cf3a.png)

It can give a lot of informations such as how many times a parameter occurs within samplers.

![pic1](https://user-images.githubusercontent.com/2484866/182579087-59225ac5-8abb-4a87-835a-2f202b1374fd.png)

In fact, by scanning the current tree of jmeter, we can define if a parameter has multiple values in our script so we can suppose that we have to put somewhere between the alteration of the parameter value a regex or something to allow variabilization.
With a hundred of samplers to process, sometimes it is easy for the developper to forget the variabilization in one or many samplers, this plugin allows him to check easily if all the parameter values have been correctly variabilized.

![pic2](https://user-images.githubusercontent.com/2484866/182579496-d20fdd88-3419-445f-91ca-593a698b2f83.png)

The plugin can display you all the samplers that are connected to the parameter you want to analyse. With the plugin, it is easy to get to the sampler in the jmeter tree by clicking to the sampler name without having to search it and open each element of the jmeter tree. You also have a shortcut to the plugin if you want  to launch a new analysis or to reach another sampler concerned by the parameter or another parameter you want to analyse.

![pic3](https://user-images.githubusercontent.com/2484866/182579881-3ecb3753-95c8-4b2c-9687-104f1a4a5a33.png)

One particularity of this plugin is the fact that it helps you with a recording file of your scenario to know where you can extract your variable. It can also suggest you a Regular Expression Extractor to the sampler that it considers as an element where it can extract the variable. More than that, it is going to reach each sampler concerned by the variable and variabilize each parameter value automatically without having the developper to search it manually in the jmeter tree. It is a huge time saving for the developper because we all know that with hundred of samplers to look at, it can be a huge time consuming if he does it manually. 
There are a few prerequisites to optimize the analyze with the plugin. First, you need to know how to create the recording file that your are going to give to the plugin for analysis. To do so,to avoid having a lot of samplers that are not useful for your test, you have to put the correct filters for the HTTP(S) Test Script Recorder
![image](https://user-images.githubusercontent.com/2484866/182613159-9c8b6b39-aa1c-4187-854c-3f49464a5316.png)


Under the HTTP(S) Test Script Recorder, you put a View Results Tree that allows you to build a file that stores the capture. You configure the View Results Tree like below. It will create an XML file with all the necessary informations for our analysis

![pic5](https://user-images.githubusercontent.com/2484866/182613715-4cf8359d-b9e0-4fc7-a506-2065816dd24c.png).

The generated XML file can be loaded with the plugin so it can return you:
- A list of samplers with parameters that you can potentially variabilize. It gives a list of samplers  where you can potentially extract the parameter value.
With the example below, we can make the following  analogy:
The sampler **0168--[/planning/tournee.cgi]** has a parameter which calls session, we can potentially extract its parameter value for variabilization by putting a Regular Expression Extractor to the sampler **0148--[/login.cgi]**

![image](https://user-images.githubusercontent.com/2484866/182615004-337f2f39-2ba4-4383-b420-b6510615f6a2.png)

- All the parameters name, in which samplers they are and where you can extract the parameter value. For example,here we have the parameter session. At the right, the list of samplers where you can put an extractor and at the left all the samplers which contain the parameter "session"

![image](https://user-images.githubusercontent.com/2484866/182621023-af41db7a-65cd-4099-abb3-06fe046e476c.png)

- This plugin can also process the Bearer Authentication Token within the HTTP Headers. It can detect where it has to extract the token and where it has to change it within the HTTP Headers.  It is going to go through the jmeter tree and variabilize each parameter value that contains a token within the HTTP Headers

![pic4](https://user-images.githubusercontent.com/2484866/182610057-609aecb5-b2b7-41d9-9719-3603b796bc79.png)

- It can display a list of potential parameters that you can variabilize with the CSV Data Set Config, so it helps for the creation of the CSV Data Set config and the variabilization within the samplers. You have to create a CSV DataSet Config in an element of the jmeter tree that is a subelement of the module controller.

![pic6](https://user-images.githubusercontent.com/2484866/182652259-18d67f55-ed3e-4493-8362-180a6403941f.png)
