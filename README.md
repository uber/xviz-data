# XVIZ example Dataset

The data provided in this repo is being processed into [XVIZ](https://github.com/uber/xviz). The original data is available at the following URLs:

- [Kitti](http://www.cvlibs.net/datasets/kitti/raw_data.php)
- [nuTonomy](https://www.nuscenes.org/download) 

## How to convert

- kitti
    ```bash
    yarn start 
    -d <your_path_to_source_data>/kitti/2011_09_26/2011_09_26_drive_0005_sync 
    -o <your_path_to_xviz-data>/kitti/2011_09_26_drive_0005_sync
    --fake-streams=true
    --disable-streams=image_00, image_01
    ```

   - Available image streams are `image_00`, `image_01`, `image_02`, `image_03`
   - Default `--image-max-width` is 400, `--image-max-height` is 300 (actual conversion will preserve aspect ratio)


- nuTonomy

    ```bash
    yarn start 
    -d <your_path_to_source_data>/streetscape.gl/data/nutonomy/nuscenes_teaser_meta_v1/v0.1
    -o <your_path_to_xviz-data>/nutonomy --samples-directory=~/dev/streetscape.gl/data/nutonomy/samples 
    --scenes=6
    ```
    
    - `-d/--data-directory` is metadata and annotations
    - `--samples-directory` is lidar, radar and images
    - `--scenes` also supports multiple numbers, `--scenes=1,2,6`
    - Default `--image-max-width` is 400, `--image-max-height` is 250 (actual conversion will preserve aspect ratio)
