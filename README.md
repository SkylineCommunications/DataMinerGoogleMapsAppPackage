# DataMinerGoogleMapsAppPackage
This Application Package installs the Skyline Google Maps on your DataMiner system.

It will show normal alarms for Germany. The Country France is in Major alarm state.(the filter 'Major' in the Google Maps top-left pane is enabled by default to see the alarm for France).

It will also show the Regions for France and Belgium. The region Vlaanderen is in Major alarm state.

Provinces for Belgium are in a normal alarm state.

You can also drill down to the cities of Belgium, these are not configured to be monitored in the alarm template.

You can select the following in the top-right corner:

1. Layers: Country, Regions, Province, City

1. SourceInfo: Element Parameters and Element Properties where Element Properties is enabled by default.

1. Objects: Individual Element Markers and Individual Service Markers

1. Traffic: Displays the traffic

## Flow

### Upload

It will upload the Skyline Google Maps protocol and Alarm Template called 'Standard' to your DataMiner system. The Generic Dummy protocol is also uploaded.

A Visio file(Skyline Google Maps.vsdx) will also be uploaded that links to your Maps config file.

Data needed for the element will also be uploaded(CSV files).

Icons needed for the Visio, and Serverconfig.xml, RT_QA_Maps.xml files will also be uploaded.

### Create

1. It will create a view 'Skyline Google Maps' below the root view.
1. Next up is the creation of an element 'Skyline Google Maps' in above mentioned view and assigns the alarm template 'Standard' to this element.
1. The element reads in the necessary data from it's CSV files.
1. The table parameter 'Country alarm' at index '2'(so France) of the Country table will be set to an Major alarm.
1. The table parameter 'Region alarm' at index '1'(Vlaanderen) of the Regions table will be set to an Major alarm.
1. For the 'Skyline Google Maps' element, element properties('Latitude' and 'Longitude') are created and assigned with a value. If these element properties would exist on your system, then the property values are set for the 'Skyline Google Maps' element.
1. Another element, 'Generic Dummy_ParameterCoordinates' is created from protocol 'Generic Dummy', version 1.0.2.3(also available on catalog.dataminer.services) and Dummy Parameter 01 & Dummy Parameter 02 are set to Latitude and Longitude values. This element is added below the 'Skyline Google Maps' view.
1. The 'Skyline Google Maps' element is added to a service 'Skyline Google Maps Service' in the 'Skyline Google Maps' view.
1. The RT_QA_Maps file is updated with the dma-id and element-id of the element(created in step 2) of your DataMiner system. For the 'Individual Element Markers' layer, the id attribute of the element tag is set to the correct dmaid/elementid of the 'Skyline Google Maps' element. For SourceInfo --> 'Element Parameters', the id attribute of the 'ViewFilter' tag is updated.
1. The Visio file is assigned to the Skyline Google Maps view.

### Result

- Depending on the zoom-level, you will see various icons/markers in the Google Maps. These can be grouped or individual.
- On the Skyline Park location there should be a flag marker when major alarm filter and Objects --> 'Individual Element Markers' is enabled.
- In the Zandstraat(old Skyline building) there should be a star marker when major alarm filter and Objects --> 'Individual Service Markers' is enabled.
- Not far from Skyline on the pitch of KFC Mandel United, there should be a flag icon when major alarm filter and SourceInfo --> 'Element Properties' is enabled.
- When SourceInfo --> 'Element Parameters' is enabled, a flag should also be shown, not far from 'Centrum West'.