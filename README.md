
# About

  This project (t01) was a part of education.
  It created to do render of complex objects faster and easier with GPU with Ray Marching and Signed Distance Functions (SDF).
  ( Also if u want, there is part of Ray Tracing in 'shaders/rt'.
    Actived it by rebuilt project with prefix of shader 'rt' as directory in 'shaders/' )

# Short guide

  To build project u need to configure your platform to x86 in VS.

  U can run project with 't01.exe' and folder 'shaders'.
  In the 'shaders' u can find all shader, but u may be interested only in one file 'shaders/sdf/SDF.GLSL'
  In this file u can find some sort of script, that allow u to create different virtual scenes.
  File reloading in realtime, u dont need to rerun app.
  If u feel confident, u can try configure scene right in 'FRAG.GLSL' in function 'sceneSDF' with varible 'mint' ( the closest object from Cam ).

# SDF description

Based on mathematical description of objects, we can determ the distance between object's surface and point in the space.
  \< 0 - in object
  \= 0 - on the object's surface
  \> 0 - out of object

**Operators:**
1.  Union (opU) - add new object to the scene ( objs may have intersections )
2.  Subtraction (opS) - cut from 1st object 2nd ( all points, that has 1st obj and don't have at the same time 1st and 2nd objs)
3. Intersection (opI) - all point that have 1st and 2nd objects at the same time
4. Smooth union (opUs) - add two new objects to the scene and makes a smooth conversion from one to the other obj depending on the coefficient 'k'

  # Script description

  - \#  - separator
  - @  - repeater -- @i\<number of repetitions>(\<function>)
  - '  - comment all string
  - // - comment all string
  - !  - embed all string

 
  **create the object:**
   -  \#\<matrix>#\<object_function>()#\<material>
   
  **add to scene:**
  -   #\<function>\<obj>[\<obj>]
   
  **create material:**
  - #material{\<ambient>, \<diffuse>, \<specular>, \<gloss>}
  
   
