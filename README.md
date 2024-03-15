# meshtastic-discord-bot-node-red
This is a guide on how to setup a Meshtastic node nonitoring discord bot using node red and MQTT. 
V1(based on home assistant install):
My preffered MQTT Broker(you can use whatever you want): EMQX (https://github.com/emqx/emqx) 


1. Make sure you have setup an MQTT broker. If you are running home assistant use either Mosquitto broker through the Addon store by default or EMQX with the community add on repository added. 
2. Install Node red. you can do it through home assistant add on store if you have the community add on repository added
3. Once you have installed node red, install these palattes (palletes can be found by going to the hamburger menu in the top right and going to manage palletes)
   @meshtastic/node-red-contrib-meshtastic
   node-red-contrib-discord-advanced
4. Create an MQTT in node that points towards your MQTT broker server (click on the pencil and create a new connection for your MQTT broker), and pick the topic that you want to follow(remember # is wildcard) ![image](https://github.com/l3gitpanda/meshtastic-discord-bot-node-red/assets/12003346/71ab1719-6c8a-4c5b-9ef3-d4fe71b9e9f1)
5. Connect a decode meshtastic node
7. Connect a DiscordMessageManager node, put your desired channel ID and add your discord token by clicking on the pencil icon and adding it there. (Explanation on how to create the discord bot and token coming later but its very easy)
8. More to come with this tutorial, its just late

Coming soon: how to add short name next to message
