![noise_tor88_spheres_0](https://user-images.githubusercontent.com/39986899/126071555-ba04def2-03fd-4dab-8fe1-e6ccd085bf3e.jpg)

# About

  This project (t01) was a part of education.
  It created to do render of complex objects faster and easier with GPU with Ray Marching and Signed Distance Functions (SDF).
  ( Also if u want, there is part of Ray Tracing in 'shaders/rt'.
    Actived it by rebuilt project with prefix of shader 'rt' as directory in 'shaders/' )
    
# Short guide
![process](https://user-images.githubusercontent.com/39986899/126071557-e383c54c-8096-426a-b6ad-6938dec50161.jpg)

  To build project u need to configure your platform to x86 in VS.

  U can run project with 't01.exe' and folder 'shaders'.
  In the 'shaders' u can find all shader, but u may be interested only in one file 'shaders/sdf/SDF.GLSL'
  In this file u can find some sort of script, that allow u to create different virtual scenes.
  File reloading in realtime, u dont need to rerun app.
  If u feel confident, u can try configure scene right in 'FRAG.GLSL' in function 'sceneSDF' with varible 'mint' ( the closest object from Cam ).

# SDF description

Based on mathematical description of objects, we can determ the distance between object's surface and point in the space.

<img src="https://user-images.githubusercontent.com/39986899/126071777-5bd5454d-f793-429a-994f-a0a9f8867c43.png" width="100" height="100">
![sphere](https://user-images.githubusercontent.com/39986899/126071777-5bd5454d-f793-429a-994f-a0a9f8867c43.png)
![tor](https://user-images.githubusercontent.com/39986899/126071779-04c4f986-df4b-4ad8-aec0-053022c94064.png)
![tor88](https://user-images.githubusercontent.com/39986899/126071781-538140cb-1a09-405c-acbc-30255d74819b.png)

  \< 0 - in object;
  \= 0 - on the object's surface;
  \> 0 - out of object;

**Operators:**
1.  Union (opU) - add new object to the scene ( objs may have intersections )
2.  Subtraction (opS) - cut from 1st object 2nd ( all points, that has 1st obj and don't have at the same time 1st and 2nd objs)
3. Intersection (opI) - all point that have 1st and 2nd objects at the same time
4. Smooth union (opUs) - add two new objects to the scene and makes a smooth conversion from one to the other obj depending on the coefficient 'k'

![tor88_spheres_box_smooth](https://user-images.githubusercontent.com/39986899/126071561-edd772b5-d3f1-45e1-b023-a2d600530ea0.jpg)

  # Script description

  - \#  - separator
  - @  - repeater -- @i\<number of repetitions>(\<function>)
  - '  - comment all string
  - // - comment all string
  - !  - embed all string

 
  **create the object:**
   -  \#\<position>#\<matrix>#\<object_function>()#\<material>
   
  **add to scene:**
  -   #\<function>\<obj>[\<obj>]
   
  **create material:**
  - #material{\<ambient>, \<diffuse>, \<specular>, \<gloss>}
 
![sin_plane_sphere](https://user-images.githubusercontent.com/39986899/126071559-d9868d9a-461d-401c-bc3e-de5f5be37faa.jpg)
![sin_plane_tor88_smooth](https://user-images.githubusercontent.com/39986899/126071560-7c2f047e-7c12-4ca9-9098-e95db5b3073d.jpg)
![noise_tor88_spheres_1](https://user-images.githubusercontent.com/39986899/126071556-2b2f8be8-8659-408b-aba9-de1da93da3ad.jpg)
![repeat](https://user-images.githubusercontent.com/39986899/126071558-bea9865c-ddc9-4d85-a2c7-83a680c2c061.jpg)
