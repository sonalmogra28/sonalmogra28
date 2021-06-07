Summer - Task 04 👨🏻‍💻 

⚜️ Team Task

Task Description 📄

🔅 Task 4.1
📌 Create image by yourself Using Python Code 

🔅 Task 4.2
📌 Take 2 image crop some part of both image and swap it. 

🔅 Task 4.3
📌 Take 2 image and combine it to form single image. For example collage 
#task4.1
import cv2
import numpy as np

image = np.ones((400, 400, 4), np.uint8) * 255

pt1 = (100, 100)
pt2 = (100, 200)
pt3 = (200, 200)
pt4 = (200, 100)
pt5 = (150,50)

cv2.circle(image, pt1, 2, (0,0,0), -1)
cv2.circle(image, pt2, 2, (0,0,0), -1)
cv2.circle(image, pt3, 2, (0,0,0), -1)
cv2.circle(image, pt4, 2, (0,0,0), -1)
cv2.circle(image, pt5, 2, (0,0,0), -1)


penta = np.array( [pt1, pt2, pt3, pt4,pt5] )

cv2.drawContours(image, [penta], 0, (0,0,255), -1)


cv2.imshow("image", image)
cv2.waitKey()


#task4.2
import cv2
sinchan= cv2.imread("SINCHAN.jpg")
sinchan.shape
doremon= cv2.imreimportad("DOREMON.jpg")
doremon.shape
cv2.imshow("doremon", doremon)
cv2.imshow("sinchan", sinchan)
cv2.waitKey()
cv2.destroyAllWindows()
#Swap & Crop
crop_sinchan = sinchan[60:180,50:100]
doremon[60:180,50:100] = crop_sinchan
cv2.imshow("Swaping", doremon)
cv2.waitKey()
cv2.destroyAllWindows()
#Swap & Crop
doremon = cv2.imread("DOREMON.jpg")
crop_doremon= doremon[100:200,50:100]
sinchan[100:200,50:100] = crop_doremon
cv2.imshow("Swaping", sinchan)
cv2.waitKey()
cv2.destroyAllWindows()




#task4.3
import cv2
 #Take 4.3: take 2 image and combine it to form single image.
s=cv2.imread('SINCHAN.jpg')
d=cv2.imread('DOREMON.jpg')

d1=d[0:275,0:500]
s1=s[0:275,0:500]
combine=cv2.hconcat([s1,d1])
cv2.imshow("final_image",combine)
cv2.waitKey()
cv2.destroyAllWindows()

d1=d[:,0:399]
s1=s[:,0:399]
combine=cv2.hconcat([s1,d1])
cv2.imshow("joined_image",combine)
cv2.waitKey()
cv2.destroyAllWindows()
