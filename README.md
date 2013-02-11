C---Lingkaran
=============

Membuat lingkaran
#include <stdlib.h>
#include <glut.h>
#include <math.h>
const double PI = 3.141592653589793;
int i,radius,jumlah_titik,x_tengah,y_tengah;
void lingkaran(int x_tengah, int y_tengah, int radius, int jumlah_titik) {
  glClear(GL_COLOR_BUFFER_BIT);
	glBegin(GL_POLYGON);
	for (i=0;i<=360;i++){
        float sudut=i*(2*PI/jumlah_titik);
        float x=x_tengah+radius*cos(sudut);
        float y=y_tengah+radius*sin(sudut);
		glVertex2f(x/100,y/100);
	}
	glEnd();
	glFlush();
}
void renderScene(){
	glColor3f(1.,1.,0.);
	lingkaran(45,45,30,360);
}
void main(int Argc, char** Argv) {
	glutInit(&Argc, Argv);
	glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
	glutInitWindowSize(480, 480);
	glutInitWindowPosition(100, 100);
	glutCreateWindow("Kelompok 3");
	glOrtho(0.0, 1.0, 0.0, 1.0, -1.0, 1.0);
	glutDisplayFunc(renderScene);
	glutMainLoop();
}
