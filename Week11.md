# Machine Learning Application -- Photo OCR

* Photo OCR -- Photo Optical Character Recognition.   
* Steps:
  1. Text Detection
  2. Extract characters and Character Segmentation 
  3. Character Classification
* Image --> Text Detection --> Character Segmentation --> Character Recognition

## Sliding Windows
* Pedestrian Detection can be detected much easier than ORC.
* Steps:
  1. Learn fixed aspect-ratio images, some of which are postive and some are not.
  2. After get all parameters, run a sliding window(rectangle) shifting several pixels at a time.
  * Then run a larger sliding window, scan through the whole picture.

* For OCR, similar to pedestrian detection, train pictures with/without characters
  1. Run sliding windows through pictures and get all potential characters spotted as white markers
  2. Expanse those white pixels, exclude those white groups that their shapes are wired.
  3. Extract those white groups.

* 1D simple sliding window to recognize characters in white groups.
  * Train the classifier to get dividers between characters. (the seperation is postive example)

* Character Classification --> supervised learning
