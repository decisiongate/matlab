## Matlab - research

#### Point Cloud - resources:

- Measure and analyze a 3D scene using point clouds:
https://www.mathworks.com/discovery/point-cloud.html

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
