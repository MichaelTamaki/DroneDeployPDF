# DroneDeployPDF
Generates a PDF of the map shown for the DroneDeploy platform. In developer mode, add this folder to the "Annotation & Measurement" tab while viewing a map that you own (this app can not get the tile images from the provided Construction and Agriculture examples). Here is an [example PDF](https://github.com/MichaelTamaki/DroneDeployPDF/blob/master/map.pdf) for the [provided dataset](https://dronedeploy.gitbooks.io/dronedeploy-apps/content/how-to-upload-an-example-project.html).

## Design
- Largely based on the [Get Tiles as Array example](https://dronedeploy.gitbooks.io/dronedeploy-apps/content/tiles/example-tiles-as-array.html).
- A PDF with size A4 can fit 3 by 4 256px tile images (portrait), or 4 by 3 256px tile images (landscape).
  - The PDF that is generated will thus fit on one page without cutting out any details of the map.
  - Iterates through zoom levels from high to low zoom to find the highest possible resolution that will fit in the PDF
- Tile images are drawn on a HTML canvas
- The canvas can then be converted into a Data URL. This can be converted into a PDF using jsPDF.

## Resources used
- PDF icon made by [Smashicons](https://www.flaticon.com/authors/smashicons) from [www.flaticon.com](https://www.flaticon.com/) is licensed by [CC 3.0 BY](http://creativecommons.org/licenses/by/3.0/)
- jsPDF library to generate PDF from canvas dataURL ([link](https://github.com/MrRio/jsPDF))
- cors-anywhere to avoid CORS security errors when drawing tile images to the canvas ([link](https://github.com/Rob--W/cors-anywhere))
