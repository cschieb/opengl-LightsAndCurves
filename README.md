opengl-LightsAndCurves
======================

A few programs that demonstrate OpenGL's lighting/shading functions and drawing of B-Spline curves


Regarding Lights.cpp:

This program utilizes OpenGL's lighting and shading features to show their affects on different materials.
The controls for the program are simple..

-Right clicking opens the main menu, which has 4 selections:
    
    -Exit: exits the program.
    
    -Toggle Lights Mode: Choosing this will enable/disable lights mode, allowing the user to press the '1' and '2'
    key to move through the 5 different light configurations. (The program with light 1, so pressing the '2' key
    will advance to the next light, and the '1' key will go to the previous light)
    
    -Display Mode: This will bring up a sub menu which has 3 options:
    
        -WireFrame: In this mode, the object will be rendered as a wireframe, and the shading will be very flat.
        (Note that when using the default bunny.poly file, the bunny will not appear to be wireframe because it
        consists of so many small triangles, but there will be a noticeable difference in the shading.)
        
        -Constant Shading: This mode will have much nicer shading than WireFrame mode, but will still be somewhat
        flat; this is a result of using only 1 normal from each triangle of the object rather than using the normal
        generated by all 3 of the vertices.
        
        -Interpolative Shading: This is the smoothest(and most demanding) shading option. In this mode, each vertex
        of each triangle is used for normal calculation.
        
    -Materials: This will bring up a sub menu with 3 sub menus inside of it, each of which contain 3 materials of which
    the oject being drawn can be rendered as:
    
        -Gems: Emerald, Obsidian, Ruby
        
        -Metals: Bronze, Chrome, Gold
        
        -Plastics, Cyan Plastic, White Plastic, Yellow Plastic
        
There are a ton of combinations to experiment with, however I have found that the default light works best when trying to
examine the difference in quality between display modes.

In addition, this program <I>should</I> be able to read any .poly file and draw the object correctly to the screen,
as long as the other .poly file follows the same format as bunny.poly.

This program makes use of OpenGL's auto normalization, which hinders performance somewhat, although it is not apparent in
this small scale example. However, manual vector normalization can be implemented to improve performance.


Regarding Curves.cpp:

Left clicking on the screen adds points to a list of control points to be used when drawing the B-Spline curve.

Once finished adding points, right click to call the function that will draw the B-Spline curve.

Press the 'q' key to clear the list of control points and start a new curve.

NOTE: The program is not fully functional at this point. There is an issue drawing the curve, which I am currently looking
into. The issue is with the blending functions, but at the moment I am not completely sure what must be done.
