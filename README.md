# Using OpenStreetMap Data to Create Dungeons and Dragons Maps


## Project Contents

- [Data Source](#data-source)
- [Project Background](#project-background)
- [Purpose](#purpose)
- ....

***

### Data Sources

[Natural Earth Data](https://www.naturalearthdata.com/)
- US State Shapefiles
    - Filtered to Kentucky
- US County Shapefiles
    - Filtered to Fayette County, Kentucky
[OpenStreetMap](https://www.openstreetmap.org/about)

* Initial Data projection: EPSG:4269 - NAD83
* Final Map projection: EPSG:3089 - NAD83 / Kentucky Single Zone (ftUS)

### Project Background

If you are interested in [other Markdown formatting options](https://www.markdownguide.org/basic-syntax/)

### Purpose

Creating a Dungeons and Dragons (D&D/DnD) Campaign is difficult.
One reason is the constant battle of creating maps that challenge the player's characters while keeping the layout of the map believable.
Another issue is when a campaign book has a specified route for the players to take, but the players end up going in twenty different directions.
This results in sessions where a Dungeon Master (DM) may have to search 20 mins for a map to use for the session while the pressure of 4 other people stacking dice ontop of each other makes the feeling urgent for an already stressed DM.
Creating maps from scratch for DnD can also be long and arduous where it might take 10-15 mins just to create one house in a city.

This lead to me getting the idea for this project.
If I could turn Real World data into a fully fledged dnd map on the fly, then this tool could save many DMs valuable time and energy that could be spent on the shenanigans of their players.

### Mapmaking Process

1. Set Project Projection to EPSG : 3089
2. Import Natural Earth Data
3. Filter US State Shapefiles to Kentucky
- "STUSPS" = 'KY'
4. Filter US County Shapefiles to Fayette County, Kentucky
- "STUSPS" = 'KY' AND "NAMELSAD" = 'Fayette County'
5. Pull OSM data using QuickOSM
- Keys:
    - amenity
    - building
    - highway
    - shop
- Layer Extent: Fayette County Outline
6. Processing Toolbox > Vector geometry > Polygons to Lines ![PtoL](https://github.com/otu222/osm-dnd/blob/main/graphics/Polygons-to-Lines_Settings.png?raw=true)
7. Processing Toolbox > Vector geometry > Offset lines ![Offset](https://github.com/otu222/osm-dnd/blob/main/graphics/Offset-Lines_Settings.png?raw=true)
8. Processing Toolbox > Vector geometry > Lines to Polygons ![LtoP](https://github.com/otu222/osm-dnd/blob/main/graphics/Lines-to-Polygons_Settings.png?raw=true)
9. Processing Toolbox > Vector creation > Random points inside polygons ![RPiP](https://github.com/otu222/osm-dnd/blob/main/graphics/Random-Points-Inside-Polygons_Settings.png?raw=true)
- Set Invalid Feature Filtering, by clicking the wrench icon. ![IFF](https://github.com/otu222/osm-dnd/blob/main/graphics/Random-Points-Inside-Polygons_IFF_Settings.png?raw=true)
10. Processing Toolbox > Vector creation > Random points on lines ![RPoL](https://github.com/otu222/osm-dnd/blob/main/graphics/Random-Points-on-Lines_Settings-Wall-Points.png?raw=true)
- Do this process twice, once for wall points and one for door points ![Doors](https://github.com/otu222/osm-dnd/blob/main/graphics/door_Settings.png?raw=true)
11. Shortest Line Between Features ![SLBF](https://github.com/otu222/osm-dnd/blob/main/graphics/Shortest-Line-Between_Features_Settings.png?raw=true)
12. Create a Hexagon Grid ![HexGrid](https://github.com/otu222/osm-dnd/blob/main/graphics/hexagon-grid_Settings.png?raw=true)

## Final Project Link

Please view the [Final Project Page](https://otu222.github.io/osm-dnd/index.html)