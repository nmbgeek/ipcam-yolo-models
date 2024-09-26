# YOLOv8 Models for IP Camera AI Detection

The easy way to get started with object detection and lots of other self-hosted AI projects is using [CodeProject.AI Server](https://www.codeproject.com/ai/docs/).

[**ipcamv8s-pva**](./ipcamv8s-pva.pt) - Detects persons, vehicles, and animals.
This model was trained using yolov8s (small) parameters to make it quick. The [COCO 2017 dataset](https://cocodataset.org/#download) was refined to include backgrounds and images with persons, vehicles, and animals. Any image which contained one of these objects that was less than 0.05% or ~200px in area (i.e., 20px x 10px) were removed from the dataset. For reference this removed 6,761 person objects however there were still over 224,978 person objects remaining in the COCO Training Dataset. I also used around 500 images from my own camera images which were labeled with [Label Studio](https://labelstud.io/). The same process was also used for the validation dataset.

[**ipcamv8n-pva**](./ipcamv8n-pva.pt) - Detects persons, vehicles, and animals. Nano model.
This model was trained on the same dataset as the small version with a patience of 20 for 300 full epochs. I resumed training after the 300 however no improvements were seen. I have tested for a day primarily with Blue Iris and am pretty happy with the results for a model of this size. It does seem to fail to recognize distant animals at times. I think one issue with this may be the large variety of animals. If there is interest I will consider retraining without the exotic animals that the COCO dataset includes.
