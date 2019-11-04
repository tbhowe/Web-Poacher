Web Poacher (v1.0)

This is a pet project I created to help me find hotspots for particular fish species, to help locate good places to go fishing.

In its current iteration it is a very basic Jupyter notebook, with the following workflow:

- Define a primary keyword (fish species) and a list of prefix keywords that act as modifiers for the primary keyword.
- Download the results of a google image search for each combination of prefix and primary keyword
- scrape GPS tags from the EXIF metadata of each image.
- clean the data, such that any images outside of the area of interest (England and Wales) are removed.
- plot the valid data points on a map using GeoPANDAS. The map includes shapefiles of England and Wales, as well as of the major rivers. These came from the Environment Agency (https://data.gov.uk/dataset/4ae8ba46-f9a4-47d0-8d93-0f93eb494540/statutory-main-river-map)


There are a number of shortcomings with the current iteration, some easier to work around than others.

The most significant problem is that the vast majority of fish photos on google do not have attached GPS tags. I'm not sure whether this is due to laudible paranoia on the part of 
my fellow anglers, or to some quirk of technological adoption (iPhones statistically produce far more GPS data than Android phones for example). 
Short of some extremely inventive social engineering, I don't see a way around this apart from downloading very large numbers of files. Speeding up this process somehow is a priority.

Another desirable feature would be to throw out "rogue" images that do not contain the fish species of interest, or at least those that 
show completely unrelated content (eg. people called "Zander" when searching for the fish Stizostedion lucioperca).
The plan is to train a pattern classifier to perform this task in a future version.






Feature plan list:

- get EXIF data in a more efficient way (download just EXIF and not the entire file)
- Pattern classifier to reject spurious images (eg. to tell "fish" from "not fish").
