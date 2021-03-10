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
    raycaster added (for lighting?)
    adds an invisible mousehelper 
    add mouse event handlers
    on each move, check for intersection with model 
    on pointer up, call shoot if there is intersection

checkIntersection(x,y):
    takes in event x and y as inputs
    populates mouse, vector2 
    raycaster.setFromCamera(mouse (vector2), camera)

load model: 
    glb file loaded with gltfLoader 
    has 3 texture images - map is skin color - basically skin of face without bones
    normalMap - flourescent blue 
    specularMap - black and white greyscale 
    adds to scene (declared as global)
    mesh.scale.set to scale the model 



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

glb file - can be opened with ms paint 3d, or any program that can open glTF files 
binary version of glTF 2.0

three.boxgeometry geometry of rectangular cuboid

NDC: normalized device coordinates - three based on webgl based on opengl es  

Mesh: polygon mesh verticies, edges, faces making up 3d object

Dat gui - lightweight js framework for creating ui 

