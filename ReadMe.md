# Localization Project





## Run 
```
cmake .
make
./run_carla.sh
// Create new tab
./cloud_loc // Might have core dump on start up, just rerun if so. Crash doesn't happen more than a couple of times
```


## Project Steps

All of your work for the project can be contained within c3-main.cpp, although you can also add additional files as necessary (while making sure to update CMakeLists.txt where necessary).  

There are three major steps to the project, and within one of the steps you are able to make a choice of which localization technique to use from the lesson. You will find the TODOs for these steps near the bottom of the c3-main.cpp file.  

### Step 1: Filter scan using voxel filter
The first step is fairly short - make use of cloudFiltered and scanCloud to filter the point cloud using a voxel grid.

### Step 2: Find pose transform by using ICP or NDT matching
The second step is the main portion of the exercise. You can choose to use either ICP or NDT matching in order to find the pose transformation. It is suggested to keep the code for this fairly short within the main() function, and instead call out to a separate function you create either elsewhere within c3-main.cpp or in a separate .cpp file. Note also that you can make use of the getPose() function in helper.cpp if you output a 4D transform matrix from your ICP or NDT function in order to get the Pose object.

### Step 3: Transform the scan so it aligns with ego's actual pose and render that scan
In the final major step, you should be able to transform the filtered scan using your calculated transform into a new point cloud using pcl.  
Note that you will also want to update what is fed into renderPointCloud to change scanCloud into your newly transformed point cloud, or else your transform will not be appropriately rendered.

### Submission
If you have appropriately implemented the steps above, you should be able to drive the vehicle at least 170 meters without the pose error rising above 1.2 meters, at an at least medium speed (three up arrow taps in the workspace). Additionally, the transformed point cloud should be appropriately rendering.  

Lastly, make sure that your project meets all specifications as outlined in the project rubric.  

To submit your project, you can create a zip file containing your c3-main.cpp file, along with any other .cpp or .h files you created to run your code. If you made updates to CMakeLists.txt, make sure to include it as well. To be safe, you may consider just zipping the entire /home/workspace directory. Then, use the "Submit Project" button on the final page in this lesson to submit.
