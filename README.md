# Learning WebGL

##### Lecture 1
- Use standard template for html file
- Create a main.js and embed it as a script in html
- For webserver install
```npm install express```
- For running webserver
```node server.js```

##### Lecture 2
- WebGL uses Right handed coordinate system
	- x: right
	- y: top
	- z: out of the screen

- Shader program. Shader is something that decides what shade of colour it will output to the screen. 
	- Vertex shader: Take incoming vertex data, determines XYZ position.
	- Fragment shader: Runs once per pixel on the screen. Interpolates all coordinates in between another vertex, until all vertices. Coordinates to Colour mapping.

- Double buffer: To ensure all pixels change at the same time. One is hidden, one is visible.

- Uniforms: Global variables for the CPU to communicate with Shader programs

##### Lecture 3
- Outline of program
	- vertexData = [...]
	- create Buffer
	- load vertexData into Buffer
	- create vertex shader
	- create fragment shader
	- create program
	- attach shaders to program
	- enable vertex attributes
	- draw

- Bind to tell GL that the buffer is a array of vertices
- bufferData: STATIC_DRAW or DYNAMIC_DRAW for third argument
- shaderSource: GL shading language created by OpenGL, as string
- ```attribute vec3 position``` specifies that it can always take next 3 components and put it into a vec3
- ```getAttribLocation``` finds the WebGL index of the position in the shaders.
- All attributes start off as disabled, need to enable.
- ```vertexAttribPointer``` arguments : how many data pts at a time, and of what type
- gl_Position and gl_FragColor are case sensitive