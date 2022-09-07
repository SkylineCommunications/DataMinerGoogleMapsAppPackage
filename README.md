# SkylineGoogleMapsAppPackage
This Application Package installs the Skyline Google Maps on your DataMiner system.

It will show normal alarms for Germany. The Country France is in Major alarm state.(you'll have to enable the filter 'Major' in the Google Maps top-left pane to see the alarm for France).

It will also show the Regions for France and Belgium. The region Vlaanderen is in Major alarm state.

Provinces for Belgium are in a normal alarm state.

You can also drill down to the cities of Belgium, these are not configured to be monitored in the alarm template.

## Flow

### Upload

It will upload the Skyline Google Maps protocol and Alarm Template called 'Standard' to your DataMiner system.

A Visio file(Skyline Google Maps.vsdx) will also be uploaded that links to your Maps config file.

Data needed for the element will also be uploaded(CSV files).

Icons needed for the Visio, and Serverconfig.xml, RT_QA_Maps.xml files will also be uploaded.

### Create

1. It will create a view 'Skyline Google Maps' below the root view.
1. Next up is the creation of an element 'Skyline Google Maps' in above mentioned view and assigns the alarm template 'Standard' to this element.
1. The element reads in the necessary data from it's CSV files.
1. The table parameter 'Country alarm' at index '2'(so France) of the Country table will be set to an Major alarm.
1. The table parameter 'Region alarm' at index '1'(Vlaanderen) of the Regions table will be set to an Major alarm.
1. The RT_QA_Maps file is updated with the dma-id and element-id of the element(created in step 2) of your DataMiner system.
1. The Visio file is assigned to the Skyline Google Maps view.
1. Depending on the zoom-level, you will see various icons in the Google Maps.