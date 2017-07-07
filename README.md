# ISL
Irish Sign Language - Hand shape dataset (ISL-HS)

The ISL-HS dataset contains real hand imagea composed of 23 hand gestures (English alphabet except ’J’, ’X’ and ’Z’) and 3 dynamic gestures (’J’, ’X’ and ’Z’). The typology is one-handed finger spelling.

To build this dataset, short videos were filmed. In total 6 people (3 males and 3 females) performed the finger spelling ISL alphabets. Each shape was recorded 3 times.

Each static gesture (hand shape) was performed by moving the arm in an arc from the vertical to the horizontal position. This was performed to simulate rotated gestures that can occur in real word conversations. The videos were converted into frames. Frames were converted to grayscale and the background was removed from the frame using a pixel-value threshold. This produced frames that contain only the arm and the hand.

The number of frames for each video depends on its length. Videos were recorded at 30 frames per second (fps) and a resolution of 640 × 480 pixels. The device used to record the videos was an Apple iPhone 7. The videos were saved with .mov extention. The video format is RGB24. In total, dataset contains 468 videos. Videos are available at https://github.com/marlondcu/ISL

From these videos, se selected only the static shapes (23) obtaining a total of 52,688 frames. From this total of frames we design a method to filter redundant frames (i.e. frames with insignificant difference). Our filtering method works as follows: Each image I_u of the original dataset is represented with a compact feature vector V_u. Then, a 'diversity score' is calculated for the image and used to make iterative image selection from the original dataset in a manner to optimise dataset diversity. Please refer to file iterations.txt for diversity_score.

Directory's structure: Videos are stored in different folders, one for each person, consisting of Person1, Person2, Person3, Person4, Person5 and Person6. Inside each folder there are 78 files being 3 for each alphabet letter. File name is given by letter followed by 1, 2 or 3 between brackets. This number represents the shot. For example: "a (1).mov" means shape "a" first shot.

Frames are stored into different zip files, one for each person. The file name structure is "Person" + person's number + shape + shot number + frame number, separated by hyphen (-). For example, "Person1-A-1-1.jpg" refers to Person 1, shape A, first shot, first frame.

The folder DiscardedFrames contais the frames that were discarded. 