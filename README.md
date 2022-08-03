#jmeter_plugin_variabilization
This plugin aims to assist the jmeter developper during the script development
In fact, it can give a lot of informations such as how many times a parameter occurs within samplers.
![pic1](https://user-images.githubusercontent.com/2484866/182579087-59225ac5-8abb-4a87-835a-2f202b1374fd.png)

By scanning the current tree of jmeter, we can define if a parameter has multiple values within our script so we can suppose that we have to put somewhere between the alteration of the parameter value a regex or something to allow variabilization.
With a hundred of samplers to process, sometimes it is easy for the developper to forget the variabilization within one or many samplers, this plugin allows him to check easily if all the parameter values have been correctly variabilized.
![pic2](https://user-images.githubusercontent.com/2484866/182579496-d20fdd88-3419-445f-91ca-593a698b2f83.png)
The plugin can display you all the samplers that are connected to the parameter you want to analyse. With the plugin, it is easy to get to the sampler within the jmeter tree by clicking to the sampler name without having to search it and open each element of the jmeter tree. You also have a shortcut to the plugin if you want  to launch a new analysis or to reach another sampler concerned by the parameter or another parameter you want to analyse.

![pic3](https://user-images.githubusercontent.com/2484866/182579881-3ecb3753-95c8-4b2c-9687-104f1a4a5a33.png)


One particularity of this plugin is the fact that it helps you with a recording file of your transaction to know where you can extract your variable. It also can suggest you a Regular Expression Extractor to the sampler that it considers as an element where it can extract the variable. More than that, it is going to reach each sampler concerned by the variable and variabilize each parameter value automatically without having the developper to search it manually with the jmeter tree. It is a huge time saving for the developper because we all know that with hundred of samplers to look at, it can be a huge time consuming if he does it manually.

This plugin can also process Bearer Authentication Token within the HTTP Headers. It can detect where it has to extract the token and where it has to change it within the HTTP Headers.  
