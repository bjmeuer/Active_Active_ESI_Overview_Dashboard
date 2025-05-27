This Json can be imported as Dashboard into CloudVision and shows a List of ESIs and related Devcies, Port-Channels, Interfaces, etc.

Here is an example output:

![](assets/20250526_173158_Screenshot.png)

NOTE: After importing the json, you have to edit and adjust the first line in AQL which Filters for devices which include "-LEAF-" in the hostname. This needs to be adjusted so that it matches all your Active Active Multihoming Switches.

`let leaf_devices = merge(`analytics:DatasetInfo/Devices`) | where(strContains(_value[\"hostname\"], \"-LEAF-\"))`
