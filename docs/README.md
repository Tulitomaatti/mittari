# Placeholder planning file. 




### Testing PlantUML embedding: Network diagram. 

<div hidden> 
```
@startuml NetworkFig
!define osaPuml https://raw.githubusercontent.com/Crashedmind/PlantUML-opensecurityarchitecture2-icons/master
!include osaPuml/Common.puml
!include osaPuml/User/all.puml
!include osaPuml/Hardware/all.puml
!include osaPuml/Misc/all.puml
!include osaPuml/Server/all.puml
!include osaPuml/Site/all.puml


' Users together {
osa_user_green(Scientist, "Scientist", "User")
osa-user_green_operations(Admin, "Admin", "Admin") 
}

' Devices
together{
osa_desktop(pc, "Desktop")
osa_laptop(laptop, "Laptop")  
osa_server(server, "MQTT + TIG-stack") 
}
together{
osa_mobile_pda(SensorNode, "Sensor Nodes")
}

together{
}

' Network
together{
osa_device_wireless_router(wifiAP, "WiFi Routers") 
osa_hub(router, "Router") 
}


Scientist --> pc: configure measurements
Scientist --> laptop: query measurements
Admin --> server: setup new nodes

pc --> router
server --> router
wifiAP --> router
laptop --> wifiAP
SensorNode --> wifiAP


@enduml
```
</div>


![NetworkFig.svg]


