# Dataset Information

This folder contains the data used for the "Comparative Analysis of Deep Learning and Traditional Computer Vision for Object Recognition in Robotics" project.

## Source

The data is a subset of the **RGB-D Object Dataset**.

* **Official Website & Download Link:** <https://rgbd-dataset.cs.washington.edu/>

## Usage in This Project

For this analysis, the following 15 object category folders from the dataset were used for training and evaluation:

```bash
data/rgbd-dataset/
├── ball/
├── bell_pepper/
├── bowl/
├── coffee_mug/
├── dry_battery/
├── food_bag/
├── food_can/
├── food_jar/
├── garlic/
├── glue_stick/
├── instant_noodles/
├── plate/
├── stapler/
├── tomato/
└── water_bottle/
```

The scripts in the root directory are configured to read the data from these folders.
