# imgprocess
import cv2  
import numpy as np  
import pytesseract
pytesseract.pytesseract.tesseract_cmd=r'C:Program FilesTesseract-OCRtesseract.exe'
  
cap = cv2.VideoCapture(0)  
  
while(True):  
    ret, frame = cap.read()    
    img = cv2.imread(frame)

text = pytesseract.image_to_string(img)
print(text)
    if cv2.waitKey(1) & 0xFF == ord('q'):  
        break   
cap.release()  
cv2.destroyAllWindows()  
