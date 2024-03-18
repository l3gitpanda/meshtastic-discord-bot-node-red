# meshtastic-discord-bot-node-red
This is a guide on how to setup a Meshtastic node nonitoring discord bot using node red and MQTT. 
(This is based on home assistant install but you can do this with standalone node red/MQTT broker)
My preffered MQTT Broker(you can use whatever you want): EMQX (https://github.com/emqx/emqx) 
## Premade flow: 
![image](https://github.com/l3gitpanda/meshtastic-discord-bot-node-red/assets/12003346/8895b658-5af2-4c9a-8211-bf7273b3275e)
Features:
- Discord Message Logging
- Node Location Map Plotting
- Ingestion from MQTT
- Protobufs decoding
- Message deduplication by ID
- Annotate integer-based node ids to hex
- Annotate packets with known NodeInfo
- Split for all current port numbers
- Writing Mesh, Packet, Device, Environment and Position measurements to InfluxDB
- Debug nodes for all outputs
  

1. After importing the flow, go to your config section (cog in the top right of editor) and change the credentials of your MQTT broker and Discord Token. (You do not need to update InfluxDB as I am just using that as a logging database for nodes I can go into how that works in another guide if anyone wants a tutorial!


## Make your own basic Discord Bot:
1. Make sure you have setup an MQTT broker. If you are running home assistant use either Mosquitto broker through the Addon store by default or EMQX with the community add on repository added. 
2. Install Node red. you can do it through home assistant add on store if you have the community add on repository added
3. Once you have installed node red, install these palattes (palletes can be found by going to the hamburger menu in the top right and going to manage palletes)

   @meshtastic/node-red-contrib-meshtastic

    node-red-contrib-discord-advanced
   
5. Create an MQTT in node that points towards your MQTT broker server (click on the pencil and create a new connection for your MQTT broker), and pick the topic that you want to follow(remember # is wildcard) ![image](https://github.com/l3gitpanda/meshtastic-discord-bot-node-red/assets/12003346/71ab1719-6c8a-4c5b-9ef3-d4fe71b9e9f1)
6. Connect a decode meshtastic node
7. Connect a DiscordMessageManager node, put your desired channel ID and add your discord token by clicking on the pencil icon and adding it there. (Explanation on how to create the discord bot and token coming later but its very easy)
8. More to come with this tutorial, its just late

## Coming soon: how to add short name next to message

## Credit:
Original Flow/Segmentation template that I used to make this: https://github.com/scruplelesswizard/meshtastic-node-red
