import cv2 import matplotlib.pyplot as plt from deepface import DeepFace # Load the image fear = cv2.imread("C:/Users/user/Pictures/diganth/34440197-7e49-48de-b4e6-069f74af5cf7.jpeg") # Load the pre-trained face detecƟon modelfaceCascade = cv2.CascadeClassifier("C:/Users/user/Downloads/haarcascade_frontalface_default.xml") # Convert the image to grayscale gray = cv2.cvtColor(fear, cv2.COLOR_BGR2GRAY) # Detect faces in the image faces = faceCascade.detectMulƟScale(gray, 1.1, 4)# Draw rectangles around detected faces for (x, y, w, h) in faces:  cv2.rectangle(fear, (x, y), (x+w, y+h), (0, 255, 0), 2) # Display the image with detected faces plt.imshow(cv2.cvtColor(fear, cv2.COLOR_BGR2RGB)) plt.axis('off') # Hide the axis plt.show() # Path to the image file you want to analyze img_path = "C:/Users/user/Pictures/diganth/34440197-7e49-48deb4e6-069f74af5cf7.jpeg" # Analyze emoƟons in the imageresult = DeepFace.analyze(img_path=img_path, acƟons=['emoƟon'])# Print the results print("EmoƟon Analysis Result:", result)result_dict = result[0] dominant_emoƟon = result_dict['dominant_emoƟon']dominant_emoƟons = [entry['dominant_emoƟon'] for entry in result]print(dominant_emoƟons)
