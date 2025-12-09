# miniRT - My First RayTracer

miniRT is a basic ray tracer implemented in C. The goal of this project is to generate computer-generated images using the Raytracing protocol, rendering a scene defined by simple geometric objects with a specific lighting system.

<img width="643" height="504" alt="myakumyaku" src="https://github.com/user-attachments/assets/a8cc262d-cb34-40f8-8d87-e14b9034b96e" />
<img width="638" height="505" alt="threeObjs" src="https://github.com/user-attachments/assets/a902fb3c-2ad0-48a3-a1a3-6f1c871b4e8e" />
<img width="651" height="506" alt="coloredLights2" src="https://github.com/user-attachments/assets/cac12a94-383b-4312-bd0f-87a150e928cc" />
<img width="638" height="509" alt="coloredLights" src="https://github.com/user-attachments/assets/70c918f4-ccb9-4868-aada-aa6ab45f7b98" />
## 📝 About

This project introduces the basics of Ray Tracing (as opposed to Rasterization). It parses a scene description file (`.rt`), calculates ray-object intersections, and renders the scene using the **MiniLibX** library.

**Key Features:**
* [cite_start]**Geometric Objects:** Renders Planes, Spheres, and Cylinders[cite: 106].
* [cite_start]**Lighting:** Implements Ambient and Diffuse lighting with Hard Shadows[cite: 110, 111].
* [cite_start]**Transformations:** Supports translation and rotation of objects, cameras, and lights[cite: 109].
* [cite_start]**Camera:** Computes the image from a specific viewpoint defined by coordinates, orientation, and FOV[cite: 130].

## 🛠 Requirements

* **OS:** Linux / macOS
* [cite_start]**Language:** C (Norminette compliant) [cite: 22, 23]
* [cite_start]**Graphics Library:** MiniLibX (libmlx) [cite: 99]
* [cite_start]**Math Library:** standard math library (`-lm`) [cite: 97]

## 🚀 Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/miniRT.git](https://github.com/your-username/miniRT.git)
    cd miniRT
    ```

2.  **Compile the program:**
    Use the `Makefile` to compile the source code.
    ```bash
    make
    ```
    *This generates the `miniRT` executable.*

3.  **Run the program:**
    [cite_start]Provide a scene description file (extension `.rt`) as an argument[cite: 116].
    ```bash
    ./miniRT scenes/example.rt
    ```

## 🎮 Controls

* [cite_start]**ESC**: Close the window and quit the program[cite: 113].
* [cite_start]**Red Cross (Window Frame)**: Close the window and quit[cite: 114].

## 📄 Scene Description Format (.rt)

The program takes a file with the `.rt` extension. [cite_start]Elements are separated by line breaks, and parameters by spaces[cite: 117, 118].

### Mandatory Elements
*Only declared once per scene.*

* **Ambient Lightning (A):** `A <ratio> <R,G,B>`
    * *ratio:* [0.0, 1.0]
    * *color:* [0-255]
* **Camera (C):** `C <x,y,z> <orientation_vector> <FOV>`
    * *orientation:* [-1, 1] for x,y,z axis
    * *FOV:* [0, 180] degrees
* **Light (L):** `L <x,y,z> <brightness> <R,G,B>`

### Objects

* **Sphere (sp):** `sp <x,y,z> <diameter> <R,G,B>`
* **Plane (pl):** `pl <x,y,z> <orientation_vector> <R,G,B>`
* **Cylinder (cy):** `cy <x,y,z> <orientation_vector> <diameter> <height> <R,G,B>`

**Example Scene:**
```text
A 0.2 255,255,255
C -50.0,0,20 0,0,1 70
L -40.0,50.0,0.0 0.6 10,0,255
pl 0.0,0.0,-10.0 0.0,1.0,0.0 0,0,225
sp 0.0,0.0,20.6 12.6 10,0,255
cy 50.0,0.0,20.6 0.0,0.0,1.0 14.2 21.42 10,0,255
