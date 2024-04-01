# Face-Swapping-for-a-Specific-Character
Video Creation with a Face Swapping of a specific character


In this project, a Face Swapping video is presented, featuring the transformation of a specific face in a video with another face.

The project is divided into three thematic sections for implementing Face Swapping: **1) Face Detection, 2) Face Recognition, and 3) Face Swapping**. To create and process the video, the cv2 library is used. Specifically, each video is divided into frames, where individual parts are processed, resulting in a set of modified frames. In the end, the new video with the Face Swapping of a specific character is saved.

***Face Detection***: This involves finding a face in a frame. The InsightFace library was used for this task. Among the available Face Detectors, RetinaFace was preferred as, although slower, it yields better results and provides ideal facial angle cropping compared to others (e.g., OpenCV, YOLO, etc.).

***Face Recognition***: This involves identifying a face compared to existing data. Implementation was done using the DeepFace library using FaceNet. Specifically, identification is made between the detected Face and images of characters from the F.R.I.E.N.D.S series, which are sorted into subfolders by their names. From this image pool, face detection is also performed, followed by a comparison of the two faces (i.e., the Face from the detected frame and the face in the image from the dataset, both extracted by the face detector), resulting in a true or false outcome. The image pool was obtained from https://www.kaggle.com/datasets/amiralikalbasi/images-of-friends-character-for-face-recognition. If the result is false, it proceeds to the next image/face until all are checked. If true, the check stops, and it proceeds to the Face Recognition stage.

***Face Swapping***: This involves changing one face with another. Again, with the help of the InsightFace library. The face extracted from the Face Detection stage and matched with a character in the Face Recognition stage is replaced with another of our choice. The process is repeated for each frame.

The project structure includes separate examples for each section (Face Detection, Face Recognition, Face Swapping), and at the end, a combination of all three is used to generate a video with the face of a specific character swapped (VIDEO SWAPPING FOR SPECIFIC CHARACTER (INSIGHT FACE & DEEP FACE)).


Useful links containing the techniques we employed, for further understanding.

1.RetinaFace: Single-stage Dense Face Localisation in the Wild https://arxiv.org/pdf/1905.00641.pdf
2.FaceNet: A Unified Embedding for Face Recognition and Clustering https://arxiv.org/pdf/1503.03832.pdf 
3.ONNX Face Swapper: https://github.com/onnx/onnx 



