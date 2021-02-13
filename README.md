# MATLAB - research - Point Cloud:

***

## 1. Measure and analyze a 3D scene using point clouds: 
- source: https://www.mathworks.com/discovery/point-cloud.html

A point cloud is a collection of data points where the individual points of the dataset represent the *coordinates for surface points* of the objects being scanned in the real world. 

Point clouds are used to measure real-world scenes and are commonly produced by lidar scanners and other devices. 

Point cloud processing is used for augmented reality (AR) and virtual reality (VR) applications and for perception and navigation in robotics and automated driving.

**Common point cloud processing tasks include:**
- Reading and writing point cloud data for analysis and display
- Transforming, filtering, and registering 3D point clouds
- Segmenting 3D point clouds into clusters and fitting them to geometric shapes

**The major components for a point cloud processing workflow are:**
- Reading and visualizing the data
- Registering and stitching a series of point clouds
- Segmenting point cloud data into clusters

### 1.1 Registering and stitching a series of point clouds example: 3D reconstruction of a scene using the iterative closest point (ICP) algorithm:
- source: https://uk.mathworks.com/help/vision/ref/velodynefilereader.html

```
veloReader = velodyneFileReader('lidarData_ConstructionRoad.pcap','HDL32E');
xlimits = [-60 60];
ylimits = [-60 60];
zlimits = [-20 20];
player = pcplayer(xlimits,ylimits,zlimits);
xlabel(player.Axes,'X (m)');
ylabel(player.Axes,'Y (m)');
zlabel(player.Axes,'Z (m)');
veloReader.CurrentTime = veloReader.StartTime + seconds(0.3); 
while(hasFrame(veloReader) && player.isOpen())
    ptCloudObj = readFrame(veloReader);
    view(player,ptCloudObj.Location,ptCloudObj.Intensity);
    pause(0.1);
end
```
![plot3(A(:,1),A(:,2),A(:,3),'or')](/images/fig-lidarData_ConstructionRoad.pcap.png)


Topics - links:
- Lidar Toolbox Supported Hardware (Lidar Toolbox): 
https://uk.mathworks.com/help/lidar/supported-hardware.html
- Velodyne LiDAR Sensors Data Acquisition (Lidar Toolbox Support Package for Velodyne LiDAR Sensors):  
https://uk.mathworks.com/help/supportpkg/velodynelidar/lidar-sensors-data-acquisition.html
- Build a Map from Lidar Data (Automated Driving Toolbox): 
https://uk.mathworks.com/help/driving/ug/build-a-map-from-lidar-data.html


### 1.2 Segmenting point cloud data into clusters example: organized lidar data that is segmented into clusters. The points in black represent ground points, and the colored points represent potential obstacles:

[...]

### 1.3 Segmenting point cloud data into clusters example: organized lidar data that is segmented into clusters. The points in black represent ground points, and the colored points represent potential obstacles:

[...]

***

Links: 
- https://pointclouds.org/documentation/tutorials/hdl_grabber.html
- https://velodynelidar.com/
- https://data.kitware.com/#collection/5b7f46f98d777f06857cb206
- https://pointclouds.org/
- https://github.com/pglira/Point_cloud_tools_for_Matlab
- https://drive.matlab.com/files/

***

- view - Display point cloud:
https://www.mathworks.com/help/vision/ref/pcplayer.view.html

- pointCloud - Object for storing 3-D point cloud: 
https://www.mathworks.com/help/vision/ref/pointcloud.html

- Lidar and Point Cloud Processing:
https://www.mathworks.com/help/vision/lidar-and-point-cloud-processing.html

- pcshow - Plot 3-D point cloud:
https://www.mathworks.com/help/vision/ref/pcshow.html

- Point cloud tools for Matlab:
https://www.mathworks.com/matlabcentral/fileexchange/54412-point-cloud-tools-for-matlab

- pcplayer - Visualize streaming 3-D point cloud data:
https://www.mathworks.com/help/vision/ref/pcplayer.html

- pcshowpair - Visualize difference between two point clouds:
https://www.mathworks.com/help/vision/ref/pcshowpair.html

- pcread - Read 3-D point cloud from PLY or PCD file:
https://www.mathworks.com/help/vision/ref/pcread.html

-  Various tools for working with large point clouds:
https://github.com/pglira/Point_cloud_tools_for_Matlab

<br /><br />

### Research - Point Cloud:

- source: https://uk.mathworks.com/help/matlab/ref/fscanf.html

```
fileID = fopen('points-170.txt','r');
formatSpec = '%f';
sizeA = [3 Inf];
A = fscanf(fileID,formatSpec,sizeA);
A=A';
size(A);
plot3(A(:,1),A(:,2),A(:,3),'or');
```
![plot3(A(:,1),A(:,2),A(:,3),'or')](/images/fig-points-example.png)
- ...
