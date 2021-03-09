# threejs

sandbox for learning three

downloaded the threejs source for sandboxing

### webgl decals example

html - just a div id="container"

decalGeometry - helper file that creates a decal mesh 

intersection - a point and a normal (both three vectors (x,y,z))

mouse is a vector2

two textures loaded (png and jpg files) - has the entire paint splash image 
loaded with THREE.textureLoader

these two files are fed into a 
THREE.meshPhongMaterial
props: 
    map - color map 
    normalMap - texture to create normal map 
    specular - specular color - defines how shiny and color of shine

orientation set to Three.Euler - three angles, one for each axis 

initialization:
    WebGLRenderer created
    size and pixelRatio added to it
    scene created 
    camera created (PerspectiveCamera)
    OrbitControl created passing in camera and renderer.domElement - allows camera to orbit around target
    AmbientLight, DirectionalLight x2 added to scene 
    loads model (loadPerryLeeSmith)
    creates a buffer geometry, creates a line from it, and adds the line to the scene

### definitions

decal - a sticker that conforms to another surface 

GTLF - gl transmission format 

normal - the perpendicular line or ray to a given object

phong material - material that uses phong reflection model and phong interpolation  (phong shading)
Bui Tuong Phong - researcher in computer graphics

phong shading - better results than gourand model (MeshLambertMaterial) - cost of performance
more performant than MeshStandardMaterial/MeshPhysicalMaterial

specular - having properties of a mirror

device pixel ratio: ratio between physical and logic pixels

buffergeometry: representation of mesh, ilne or point