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

# Artificial Data Synthesis
* Create large data set/ increase the size of dataset
* For photo orc, create artificial data from computer fonts with image postprocess to make them look similar to the real data.
* Another way, it take the real character pictures and apply distortions/filters on those pics to get new dataset.
* Synthetic data can provide you unlimited database.
* Conclusion:
  1. Create new data from scratch (fonts).
  2. Create data by introducing distortions.
  3. Introducing noise should be meaningful and may appear in real examples.
  4. Before you get more data, make sure you have a low bias classifier(no underfitting).
  5. Other ways to generate data:collect data yourself; Crow source(Amazon Mechanical Turk)
  
 # Ceiling Analysis
* For each phase, manually provide correct input instead of learned input, measure the system accuracy.
* This helps you figure out the upside potential if you perfectly accomplish each phase.
