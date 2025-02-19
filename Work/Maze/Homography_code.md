```C
#include <stdio.h>
#include <stdlib.h>
#include <math.h>

// Define the size of the input image
#define INPUT_WIDTH  400
#define INPUT_HEIGHT 300

// Define the four corner points of the input image
float src_pts[4][2] = {{56, 65}, {368, 52}, {28, 387}, {389, 390}};

// Define the four corner points of the output image
float dst_pts[4][2] = {{0, 0}, {1, 0}, {0, 1}, {1, 1}};


// Compute the homography matrix
void compute_homography(float H[3][3], float x, float y)

{
	float A[8][9];
	for (int i = 0; i < 4; i++) {
	    A[2*i][0] = A[2*i+1][3] = src_pts[i][0];
		A[2*i][1] = A[2*i+1][4] = src_pts[i][1];
		A[2*i][2] = A[2*i+1][5] = 1;
		A[2*i][3] = A[2*i][4] = A[2*i][5] = 0;
		A[2*i][6] = -src_pts[i][0] * dst_pts[i][0];
		A[2*i][7] = -src_pts[i][1] * dst_pts[i][0];
		A[2*i][8] = -dst_pts[i][0];
		A[2*i+1][6] = -src_pts[i][0] * dst_pts[i][1];
		A[2*i+1][7] = -src_pts[i][1] * dst_pts[i][1];
		A[2*i+1][8] = -dst_pts[i][1];
    }
  
	// Add the constraints for the point (x, y)
	A[8][0] = x;
	A[8][1] = y;
	A[8][2] = 1;
	A[8][3] = A[8][4] = A[8][5] = 0;
	A[8][6] = -x * dst_pts[3][0];
	A[8][7] = -y * dst_pts[3][0];
	A[8][8] = -dst_pts[3][0];
  
	// Use singular value decomposition to solve for H
	float U[8][8], V[9][9], S[8];
	cv::SVD::compute(A, U, S, V, cv::SVD::FULL_UV);
	H[0][0] = V[8][0]; H[0][1] = V[8][1]; H[0][2] = V[8][2];
	H[1][0] = V[8][3]; H[1][1] = V[8][4]; H[1][2] = V[8][5];
	H[2][0] = V[8][6]; H[2][1] = V[8][7]; H[2][2] = V[8][8];
}
  
int main()
{
	// Compute the homography matrix for the point (200, 150)
	float H[3][3];
	compute_homography(H, 200, 150);
  
	// Print the homography matrix
	printf("Homography matrix:\n");
	for (int i = 0; i < 3; i++) {
		for (int j = 0; j < 3; j++) {
			printf("%f ", H[i][j]);
		}
		printf("\n");
	}
  
	return 0;
}
```
