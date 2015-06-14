## Contents

[TOC]

# Overview

This is my first attempt at mark a backbone app. [http://mapbrite.com/stoa](http://mapbrite.com/stoa)

Every thing below here was stolen from shapefile.py github site.


# Examples

Before doing anything you must import the library.


    >>> import shapefile



## Reading Shapefiles



### Reading Shapefiles from File-Like Objects




    >>> for name in dir(shapes[3]):
    ...     if not name.startswith('__'):
    ...         name
    'bbox'
    'parts'
    'points'
    'shapeType'

  * shapeType: an integer representing the type of shape as defined by the shapefile specification.


        >>> shapes[3].shapeType
        5

  * bbox: If the shape type contains multiple points this tuple describes the lower left (x,y) coordinate and upper right corner coordinate creating a complete box around the points. If the shapeType is a Null (shapeType == 0) then an AttributeError is raised.


        >>> # Get the bounding box of the 4th shape.
        >>> # Round coordinates to 3 decimal places
        >>> bbox = shapes[3].bbox
        >>> ['%.3f' % coord for coord in bbox]
        ['-122.486', '37.787', '-122.446', '37.811']

  * parts: Parts simply group collections of points into shapes. If the shape record has multiple parts this attribute contains the index of the first point of each part. If there is only one part then a list containing 0 is returned.

        >>> shapes[3].parts
        [0]

 