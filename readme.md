
 ## Bevy Mesh Terrain
 
 A very bevy-centric terrain plugin that takes advantage of entities, components and systems as much as possible to be as easy to understand and interact with as possible. 
 
 You spawn an entity and give it the 'TerrainConfig' and 'TerrainData' components, and then the plugin systems will spawn child entities which are each of the rendered chunks. 
 In this way, it works similarly to a voxel chunking system ( a la minecraft) except using heightfields (2d) instead of voxels (3d). 
 

 ![terrain1](https://github.com/ethereumdegen/bevy_mesh_terrain/assets/6249263/12264e98-5928-4987-a6a2-b22645f14279)

  
 
 
 ## How it works 
 
 ( See examples folder )
 
 1. You load a heightfield image into bevy asset server (R16 format - single color channel of 16 bits per pixel) 
 
 2. Pass this handle into this terrain plugin so that it will generate the heightfield data (Note: you could also set the heightfield data yourself manually)
 
 3. The plugin systems automatically spawn 'chunk' entities by sampling the heightfield data.  Chunks are only built and spawned when they are near the TerrainView component. 
 

## Bevy versions

Currently supports bevy 0.11 
 



### TODO 
- fix the visual bug with the missing strip  -- is it due to rotation ?  
- add texture support with splatting for grass/dirt/ etc  (upgrade shader material code) 
- add collision using parry (should be simple since heightmap is already the exact same format of parry heightfield ! )
- add various LOD levels so far-away chunks will render but at a lower sampling rate 
