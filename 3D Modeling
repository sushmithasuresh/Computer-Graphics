#include <Windows.h>  
#include <GL/glut.h>
GLfloat anglecube = 0.0f;
int refreshMills = 15; 
void initGL() 
{
   glClearColor(0.0f, 0.0f, 0.0f, 1.0f); // Set background color to black and opaque
   glEnable(GL_DEPTH_TEST);   
}
void display() {
   glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT); // Clear color and depth buffers
   glMatrixMode(GL_MODELVIEW);     // To operate on model-view matrix
 
   glLoadIdentity(); 
    glTranslatef(1.5f, 0.0f, -7.0f); 
  
  
   glRotatef(anglecube, 1.5f, 1.0f, 1.0f);  // Rotate about (1,1,1)-axis [NEW]
 
   glBegin(GL_QUADS);        // Draw The Cube Using quads

		  // Top face (y = 1.0f)
		glColor3f(0.0f,1.0f,0.0f);    // Color Blue
			glVertex3f( 1.0f, 1.0f,-1.0f);    // Top Right Of The Quad (Top)
			 glVertex3f(-1.0f, 1.0f,-1.0f);    // Top Left Of The Quad (Top)
			glVertex3f(-1.0f, 1.0f, 1.0f);    // Bottom Left Of The Quad (Top)
			glVertex3f( 1.0f, 1.0f, 1.0f);    // Bottom Right Of The Quad (Top)
 
			
		// Bottom face (y = -1.0f)
		glColor3f(1.0f,0.5f,0.0f);    // Color Orange
			glVertex3f( 1.0f,-1.0f, 1.0f);    // Top Right Of The Quad (Bottom)
			glVertex3f(-1.0f,-1.0f, 1.0f);    // Top Left Of The Quad (Bottom)
			glVertex3f(-1.0f,-1.0f,-1.0f);    // Bottom Left Of The Quad (Bottom)
			glVertex3f( 1.0f,-1.0f,-1.0f);    // Bottom Right Of The Quad (Bottom)
    
      // Front face  (z = 1.0f)
		glColor3f(1.0f,0.0f,0.0f);    // Color Red    
			glVertex3f( 1.0f, 1.0f, 1.0f);    // Top Right Of The Quad (Front)
			glVertex3f(-1.0f, 1.0f, 1.0f);    // Top Left Of The Quad (Front)
			glVertex3f(-1.0f,-1.0f, 1.0f);    // Bottom Left Of The Quad (Front)
			glVertex3f( 1.0f,-1.0f, 1.0f);    // Bottom Right Of The Quad (Front)
    
      // Back face (z = -1.0f)
		glColor3f(1.0f,1.0f,0.0f);    // Color Yellow
			glVertex3f( 1.0f,-1.0f,-1.0f);    // Top Right Of The Quad (Back)
			glVertex3f(-1.0f,-1.0f,-1.0f);    // Top Left Of The Quad (Back)
			glVertex3f(-1.0f, 1.0f,-1.0f);    // Bottom Left Of The Quad (Back)
			glVertex3f( 1.0f, 1.0f,-1.0f);    // Bottom Right Of The Quad (Back)

	// Left face (x = -1.0f)
    
		glColor3f(0.0f,0.0f,1.0f);    // Color Blue
			glVertex3f(-1.0f, 1.0f, 1.0f);    // Top Right Of The Quad (Left)
			glVertex3f(-1.0f, 1.0f,-1.0f);    // Top Left Of The Quad (Left)
			glVertex3f(-1.0f,-1.0f,-1.0f);    // Bottom Left Of The Quad (Left)
			glVertex3f(-1.0f,-1.0f, 1.0f);    // Bottom Right Of The Quad (Left)
    
	  // Right face (x = 1.0f)
    	glColor3f(1.0f,0.0f,1.0f);    // Color Violet
			glVertex3f( 1.0f, 1.0f,-1.0f);    // Top Right Of The Quad (Right)
			glVertex3f( 1.0f, 1.0f, 1.0f);    // Top Left Of The Quad (Right)
			glVertex3f( 1.0f,-1.0f, 1.0f);    // Bottom Left Of The Quad (Right)
			glVertex3f( 1.0f,-1.0f,-1.0f);    // Bottom Right Of The Quad (Right)
  
glEnd(); 
   
   //  glutWireTeapot(2.0);
  // glutSolidCube(2.0);   
//   glutWireCube(2.0);
  // glutWireTorus(2.0, 2.0, 8,3);
	 //glutSolidCone(2, 4, 3, 2);
	
	glutSwapBuffers();  
   
   anglecube += 0.2f;
   
}
void timer(int value) {
   glutPostRedisplay();      // Post re-paint request to activate display()
  glutTimerFunc(refreshMills, timer, 0); // next timer call milliseconds later
}
 
void reshape(GLsizei width, GLsizei height) {  
   
   if (height == 0) height = 1;                // To prevent divide by 0
   GLfloat aspect = (GLfloat)width / (GLfloat)height;
 
   // Set the viewport to cover the new window
   glViewport(0, 0, width, height);
 
   glMatrixMode(GL_PROJECTION);  // To operate on the Projection matrix
   glLoadIdentity();             // Reset
   gluPerspective(45.0f, aspect, 0.1f, 100.0f);
}
 
int main(int argc, char** argv) {
   glutInit(&argc, argv);            
   glutInitDisplayMode(GLUT_DOUBLE); 
   glutInitWindowSize(640, 480);   
   glutInitWindowPosition(50, 50); 
   glutCreateWindow("3d animation");          
   initGL();                       
   glutDisplayFunc(display);       
   glutReshapeFunc(reshape);      
 
   glutTimerFunc(0, timer, 0);     // First timer call immediately
   glutMainLoop();                 
   return 0;
}
