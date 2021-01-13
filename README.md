#include <opencv2/highgui/highgui.hpp>
#include <opencv2/imgproc/imgproc.hpp>
#include <iostream>

using namespace cv;
using namespace std;

Mat rotate(Mat src, double angle)
{
	Mat dst;      //Mat object for output image file
	Point2f pt(src.cols / 2., src.rows / 2.);             
	Mat r = getRotationMatrix2D(pt, angle, 1.0);    
	warpAffine(src, dst, r, Size(src.cols, src.rows));
	return dst;       
}

int main()
{
	Mat src = imread("C:\\Users\\User123\\Downloads\\yy.jpeg"); 
        Mat dst;      
	dst = rotate(src, 30);      
        imshow("src", src);       
	imshow("dst", dst);        
	waitKey(0);                   
	return 0;
}
