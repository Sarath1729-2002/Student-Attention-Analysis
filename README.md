# Student-Attention-Analysis
This project is implemented to provide a non-invasive attention monitoring system
for educators to better tailor their teaching approach towards the target audience ie
the students
Here I have used three main sub systems as follows:

➢ A pose recognition system to check if the student is distracted and turning his
head sideways. This is a pure OpenCV implementation. Here I used haar-cascades
files and mediapipe package to fix landmarks on the face. Then we identify the
landmark representing the nose on which we project a perpendicular line face
out of the plane of the face. Following this we try to interpret the polar angle of
the projecting line. Now using this reading, we can approximate the pitch, yaw
and roll of the user’s face

➢ An emotion recognition model which will monitor the emotion of the students
through the session. We used a Convolutional net with 4 Conv 2D layers, one
flatten layer and one fully connected dense layer to train the emotion
recognition model. The FER-2013 Dataset was used for the training and
validation. We got an adequate 96 % training accuracy and 78 % testing accuracy

➢ An eye-tracking model which will be used to check if the user's eye is focused on
the screen at all times. We use an open source repository called GazeTracking
which is used to track the movements of the user’s pupil. This is also used to
analyse if the user was feeling sleepy, bored or exasperated
Since we are processing a live video feed, we record each of the three attributes for
reach frame of the feed using a list. Then we classify each frame into 8 levels of
attention. Then all the statistics of the session is passed on to the educators for their
needed use

The 8 levels of attention in decreasing order of attentiveness are as follows:
1. Attentive and Happy
2. Attentive and Surprised
3. Attentive and Neutral
4. Writing
5. Eye away from screen
6. Sleepy / Tired / Bored
7. Totally distracted
8. Face away from the screen

The included .ipynb file includes all the codes, including the convolutional net for the emotion recognition functionalty

Before you start with the project, install opencv,medianet, pygal and tensorflow using pip
