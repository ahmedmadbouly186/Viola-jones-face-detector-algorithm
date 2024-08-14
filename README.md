# Viola-jones-face-detector-algorithm

This repo is an implementation for this prety paper : https://www.ipol.im/pub/art/2014/104/article.pdf

- we made changes in the implementation to make memory and time optimizations in both the traning process and the final frame processing
- our impelementation support parallization in CPU using multithread

# definisions

- Yo : desired overall false positive rate

- Yl : desired targeted layer false positive

- Bl : desired targeted layer false negative , 1-Bl detection rate

# How to run CPU version

after clonning the repo , inside folder viola-jons-cpu do the followig

# for traning new model

1. download the data set from the followign link https://drive.google.com/uc?id=1z2kzc5W_LMz5ubrRzvvQh1rCV2cyBf-B , and extract it.
2. download stb liberary by this command "git clone https://github.com/nothings/stb.git" and run this two commands to copy some files out of the folder " cp stb/stb_image.h ./ " and " cp stb/stb_image_write.h ./ "
3. inside main.cpp make sure inside the main function , the mode must be TRAIN_FACE_DETECTION. make sure to have this line at the beggining of the main funciton : mode current_mode = TRAIN_FACE_DETECTION;
4. in calling this fucntion train_face_detector("model", -1, 0.9, 0.9, 0.9, 0, 0); pass the name of the folder where you want to save the model in the first argument
5. in terminal run command "run.bat" wich will call script i have wrote to compile the code and generate excutable and run the excutable

# for test the model

- make step 1,2 and 3 as above in the train , but instead of TRAIN_FACE_DETECTION, make the mode current_mode = TEST_FACE_DETECTION;

4. in calling test_face_detector_threads("model", -1); make sure to pass the name of the folder that contain your model in the first argument
5. run command "run.bat" in terminal

# for process image frame and extract the faces in the iamge

- make step 1,2 and 3 as above in the train , but instead of TRAIN_FACE_DETECTION, make the mode current_mode = PROCESS_LOCAL_FRAME;

4. in calling process_local_frame("img.jpg"); make sure to pass the imag wich you want to process in the first argument process_local_frame("img.jpg");
5. run command "run.bat" in terminal
