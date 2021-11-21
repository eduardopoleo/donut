LEVEL 1

Video 1: Donut Base
- PREP torus
  - Set size (10cm)
    Major and minor radius
  - Set resolution
    Major and minor segments
    - TIPs: 
      - Use the lowest resolution possible and then use sub surface modifers.
      - Keep size of face close to squares. Much easier to do displacements with squares
      displacements are for making the donut look irregular
- Make donut more irregular
  - Edit mode (tab)
  - Use proportional editing (so that we do not have to grap point by point) (O)
  - Mishape it by learning how to use ^
- Make it smoother
  - Shapes
    - Shape smooth: organic shape (we choose this one)
    - Shape flat: hard shapes like buildings etc
  - Edges
    - Sub surface modifier
      Viewport -> number of subdivisions (higher = smoother but more computationally expensive)

Video 2: Icing Base
  - Side views:
    - Gizmo X, Y
  - Creating the Icing
    - x-ray selection
    - shift + D
    - make it it's own object
      p -> selection
  - Outliner: sidebar where we have holistic view of the scene
      - rename objects accordingly
  - Clip start: for better zooming
    - right side pane little arrow to be able to better zoom in
  - Thickening the icing:
    - Add modifier -> Solidify, gives thickness to any mesh.
      - Play around with thickness and Offset
    - Reorder the modifier, so that the sub surf gets applied to the thickness
      - Solidifier first 
      - sub surf 

Video 3: Improving icing
  - Problems visualing mesh with solidify:
    - Disable square icon in the modifier
  - Increase mesh size:
    - Select all the mesh -> Click on point and press A
    - Right click -> subdivide 
      - (What's the difference with sub surf modifier?)
      - He gives an tech explanation not important for now
    - Smooth it out (1)
  - Create drops:
    - Hide Upper part of icing
      - Keep proportional editing
      - Select 1 line of nodes (alt + left click)
      - Invert (cmd + I)
      - Hide (H) -> so that we don't affect the other part of the mesh
      - Unhide (alt + H)
    - Create variaty in the icing
      - Use snap magnet -> face -> project individual elements. Makes sure edges don't come into the donut when pulled
      - Pull around with sharp edges
    - Create drops
      - Choose 2 or 3 edges + E (extrude) and pull down
      - Use s to scale the size of the drop
    - Drops hug the donut
      - Adjust crease (1) in the solify  modifier to make icing hug the donut

Video 4: Sculpting
  - Increasing details:
    - Need to apply -> create copy first
    - Select both icing and onuts from the outliner and press M to add to collection
    - Apply subdivision surf (Why applying does reapply?)
  - Sculpting Donut center  :
    - Press F to adjust size of the brush
    - Holding down cmd will push inwards the sculpting
    - Go around from the middle
    - Add another subsurf modifier and go around a bit more
  - Sculpting Icing:
    - Apply the solidify modifier
    - Increase the sub surf modifier to 3 to get more detail and apply
    - Use inflate brush -> to create a bit of dripping effect.
    - In general change to smooth step if it looks too odd.
    - Grab brush + inflate (secon pass) to pinch in the inner part of the donut
    - Draw mode all over the icing to create displacement
  - Fix the sticking icing pieces
    - Edit mode go around the sticking pieces and rotate them into the donut

Video 5: Rendering
  - Adding Plance
    - Rendering mode. Top right side of the screen
    - 3D cursor make sure it's in the middle
    - Add a plane -> mesh -> plane
  - Group icing + donut:
    - Select child
    - Shift click on the master object
    - Cmd P -> Object (Keep transform)
  - Move Donut on top the plane
  - Rendering Engines:
    - Move light closer to the donut
    - We won't see much shadows or details due to the rendering engine we're choosing
      - Evee is fast but one really has to work to make details like shadow show
      - Cycles is best but it's a LOT more costly
    - We could make them use GPU but I do not have so fuck it CPU
  - Camera:
    - Determine what you'll see when you hit render
    - Click the camera icon to see the final image preview
    - Use the side options to lock camera to view
    - Place camera where it should be
  - Render
    - Render image
  - Better lighting:
    - Move light away to have it be more uniform
    - Adjust the power
  - Change color of plane
    - Select it
    - Select material -> new
    - Base color -> blue

Video 6: Materials:
  - Three main properties that we ever change:
    - Base color -> change to pink
    - Roughness (how it reflecting something is)
      - Low -> almost like a mirror
      - High -> almost like play doh
    - Subsurface (scattering).
      - Lights enters the material and bounce inside it
      - Human skin, food has this property
      - Increase to aoubt 0.28
    - Subsurface color
      - Tweak until it looks decent
    - Subsurface Radius
      - 3 values for every channel (rgb)
      - 0.3, 0.15, 0.15
  Donut:
    - Give base color bready, orangy color
    - A bit of subsurface 0.105
    - Color: yellow
    - 0.1 0.1 0.1
  Split view
    - Go to wherever is a border and right click split view
  Denoiser
    - Render menu -> Increasing the Render will reduce the noise but it'll take a lot more to render.
    - From comments:
      - Go to Render properties
      - Open Denoising
      - Check OpenImageDenoise
      - Click on the checkbox
    - Also, View layer properties
      - Data -> Denoising Data
