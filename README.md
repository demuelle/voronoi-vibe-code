# Voronoi Vibe Code
This is my first vibe coded project.

I wanted to draw a Voronoi diagram, although I didn't know this was the name of what I wanted.

The idea was, given a point, (maybe Wrigley Field in Chicago), I wanted to draw a map that shows the area that is closer to that point than any other of a set of points (say, White Sox Park, Brewers Stadium, The Twins Stadium, Tiger Stadium, etc.).

I wondered if ChatGPT could handle this.

Here's our interaction:

> **Me:** I'd like to use javascript to write a program on a webpage that draws a map. The idea is that I'd like to highlight the area that's closer to a specified location than several other specified locations. So, if the specified location was soldier field in chicago, and the other locations are the White House in Washington DC, the St. Louis Arch, the Alamo, Everglades National Park, and Chicago Botanic Gardens, the highighted area would be bounded by a pentagon, where all points within the pentagon are closer to soldier field than any other of the specified locations. Further, all points outside the pentagon are closer to at least one of the specified locations than to soldier field.

> **ChatGPT:** Done — I created a single-file webpage named Voronoi Map in the canvas (HTML + JavaScript) that:

> * Shows a Leaflet map.
> * Loads example points (Soldier Field as the focus, plus White House, St. Louis Arch, Alamo, Everglades, Chicago Botanic Garden).
> * Computes a planar Voronoi diagram using Turf.js and highlights the polygon of points closer to the focus than any other site.
> * Lets you set the focus (click), add other sites (Shift+click), recompute the region, and export the highlighted region as GeoJSON.

> Open the Voronoi Map file in the canvas, save it as voronoi_map.html and open it in your browser to run. If you want, I can:

> Add geodesic-aware (great-circle) comparisons instead of planar Turf voronoi,

> Use a different basemap or projection, or

> Turn this into an interactive React component or standalone demo page with controls.

> *ChatGPT outputs the code in `voronoi-map.html`*

> **Me:** thank you! now, turn this into a standalone demo page with controls

> **ChatGPT:** Your demo page is now fully standalone with styled controls and clear instructions. Open the file in a browser, and you’ll have buttons for loading the Soldier Field example, computing the Voronoi region, and exporting the highlighted polygon.

> Would you like me to also add a dropdown so you can pick from multiple preset focus locations (e.g. switch from Soldier Field to White House instantly)?

> **Me:** I'd like to be able to input the locations into this application. I'd also like the application to compute the area of the voronoi regoin.

> **ChatGPT:** You can now input coordinates directly into the app:

> Enter a focus location (lat,lng) and click Set Focus.

> Enter a competitor location (lat,lng) and click Add Site.

> When you compute the region, it will also display its area in square kilometers under the controls.

> Would you like me to also allow location entry by place name (e.g., “Soldier Field, Chicago”) with automatic geocoding?

> **Me:** Yes. Also, include the area in square kilometers as well as square miles

> **ChatGPT:** Now you can input either coordinates or place names (via OpenStreetMap’s geocoding).
The computed Voronoi region’s area is displayed in square kilometers and square miles.

> Would you also like me to display the perimeter length of the region?

> **Me:** Please include on the page a control that contains a list of the competitor locations, with the ability to remove each one individually with a button click. Also, if the focus region is already drawn, removing a site will update the focus region. Also, instead of exporting the geojson, export a json file that includes the names and lat,lng of the focus and the competitors, as well as the geojson of the region.

> **ChatGPT:** Got it — here’s what I’ll do for you:

> Add a competitor list control that shows all current sites by name (or “Site N” if unnamed).

> Each competitor will have a remove button. Removing one will delete it from the map and immediately recompute the Voronoi region if it’s already drawn.

> Change the export: instead of only GeoJSON, it will export a JSON file containing:
> * Focus (name + lat,lng)
> * Competitors (name + lat,lng for each)
> * The full GeoJSON of the computed focus region.

> Do you want competitor names to come from the user’s typed input string (place name or coordinates), or should I just auto-label them “Site 1, Site 2, …”?

> **Me:** the competitor names should include both the user's typed input string as a userInput property AND the actual name that was matched on the lookup as matchedLocationName

> *ChatGPT outputs the code in `voronoi4.html`*