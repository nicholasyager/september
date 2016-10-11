# September

September is a domain awareness system that uses facial recognition and
machine learning to predict the destination of pedestrian traffic.

## System overview

This system is composed of 5 parts:

1. Pedestrian detection: A Haars cassade classifier is used to detect
   pedestrians in a frame.
2. Facial recognition: Using a bounding box around the pedestrian, a Haars
   cascade searches for a face for the pedestrian. If a face is found, it is
   compared against an existing database of faces to identify the pedestrian.
   If a sutable match is not found, the face is stored for later idenfication
   and the pedestrian is given a unique identifier.
3. Optical flow Analysis: Using markers within the pedestrian bounding box,
   search for the pedestrian in the next frame. Be sure to reset the markers in
   this frame. The movement of the person's bounding box is recorded.
4. Trajectory prediction: A model of pedestrian traffic trained on the entire
   population of observaions is used to compute all likely trajectories based
   on the previously observed movements.
5. Destination classification: Once the likely trajectories have been computed,
   use a classifier(?) trained for the individual, if available, to predict 
   what the pedestran's final destination will be.
