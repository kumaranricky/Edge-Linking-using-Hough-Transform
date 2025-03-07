# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
```python
/*
developed by: Kumaran.B 
reg no : 212220230026
*/

# Read image and convert it to grayscale image
img=cv2.imread("line.jpg",cv2.IMREAD_COLOR)
img=cv2.resize(img,(500,400))
g_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow("Road",img)
cv2.imshow("GrayRoad",g_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Find the edges in the image using canny detector and display
img1=cv2.GaussianBlur(g_img,(3,3),0)
canny = cv2.Canny(g_img, 70, 150)
cv2.imshow("Canny edge detector",canny)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(canny,1,np.pi/180, threshold=100, minLineLength=50,maxLineGap=250)


# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(img,(x1, y1),(x2, y2),(0, 0, 255),3)
 
# Display the result
cv2.imshow("Hough transform",img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output

### Input image and grayscale image
![Screenshot (307)](https://user-images.githubusercontent.com/75243072/173773475-00d91bdc-1932-4d65-a3ff-d94f13a68b5d.png)


### Canny Edge detector output
![Screenshot (185)](https://user-images.githubusercontent.com/75243072/173773667-7e0bae2a-017c-4844-a8cc-568b711333a6.png)


### <br><br>Display the result of Hough transform
![Screenshot (202)](https://user-images.githubusercontent.com/75243072/173773735-a7f85695-cf7c-40a0-96ed-da16dd7472b8.png)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
