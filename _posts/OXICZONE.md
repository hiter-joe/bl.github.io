In ParaView, you can extract the points at a specific concentration by using the "Threshold" filter. To do this, follow these steps:

Load your concentration data into ParaView
Apply the "Threshold" filter to the data by clicking on the "Filters" menu and selecting "Threshold".
In the Threshold filter properties, set the "Threshold By" property to "Concentration" and the "Threshold Range" property to [0.5, 0.5]. This will extract the points with a concentration value of 0.5.
Apply the filter by clicking the "Apply" button.
To export the points, click on the "File" menu and select "Export Data". Choose the format you want to export the data to (e.g. CSV, VTK, etc.).
After you've exported the data, you can open it in a spreadsheet program or another application that can handle the chosen format to view the coordinates of the points.
