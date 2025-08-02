#include <GL/glut.h>
#include <cstring>

// Global variables to manage atom positions and animation
float angle = 0.0f;           // Rotation angle for scene
float h1PosX = -2.0f;         // Hydrogen 1 X position
float h2PosX = 2.0f;          // Hydrogen 2 X position
float oPosY = 2.0f;           // Oxygen Y position
bool fused = false;           // Flag to check if molecule is formed

// Function to draw 3D label near an atom
void drawLabel3D(float x, float y, float z, const char* text) {
    glDisable(GL_LIGHTING);               // Disable lighting for 2D text
    glColor3f(1.0, 1.0, 1.0);             // White color
    glRasterPos3f(x, y, z);               // Set 3D text position
    for (int i = 0; i < strlen(text); i++) {
        glutBitmapCharacter(GLUT_BITMAP_HELVETICA_18, text[i]);
    }
    glEnable(GL_LIGHTING);                // Re-enable lighting
}

// Function to draw 2D label on the screen (HUD text)
void drawLabel2D(float x, float y, const char* text) {
    glMatrixMode(GL_PROJECTION);
    glPushMatrix();
    glLoadIdentity();
    gluOrtho2D(0.0, 800, 0.0, 600);       // Set orthographic projection

    glMatrixMode(GL_MODELVIEW);
    glPushMatrix();
    glLoadIdentity();

    glDisable(GL_LIGHTING);              // Disable lighting for HUD
    glColor3f(0.0f, 1.0f, 1.0f);         // Cyan color
    glRasterPos2f(x, y);                 // Screen coordinates
    for (int i = 0; i < strlen(text); i++) {
        glutBitmapCharacter(GLUT_BITMAP_HELVETICA_18, text[i]);
    }
    glEnable(GL_LIGHTING);              // Re-enable lighting

    // Restore projection and modelview matrices
    glPopMatrix();
    glMatrixMode(GL_PROJECTION);
    glPopMatrix();
    glMatrixMode(GL_MODELVIEW);
}

// Function to draw a colored sphere representing an atom and label it
void drawSphere(float x, float y, float z, float radius, float r, float g, float b, const char* label) {
    glPushMatrix();
    glTranslatef(x, y, z);               // Move to position
    glColor3f(r, g, b);                  // Set atom color
    glutSolidSphere(radius, 40, 40);     // Draw sphere
    glPopMatrix();

    drawLabel3D(x, y + radius + 0.2f, z, label);  // Draw label slightly above
}

// Lighting configuration
void initLighting() {
    GLfloat light_pos[] = { 0.0f, 5.0f, 5.0f, 1.0f };   // Light position
    GLfloat light_diff[] = { 0.8f, 0.8f, 0.8f, 1.0f };  // Diffuse lighting

    glEnable(GL_LIGHTING);
    glEnable(GL_LIGHT0);
    glLightfv(GL_LIGHT0, GL_POSITION, light_pos);
    glLightfv(GL_LIGHT0, GL_DIFFUSE, light_diff);

    glEnable(GL_COLOR_MATERIAL);         // Allow color to control material
    glEnable(GL_DEPTH_TEST);            // Enable depth testing for 3D
}

// Main display function
void display() {
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);  // Clear screen and depth buffer

    // Setup camera and view
    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();
    gluLookAt(0.0, 0.0, 9.0,     // Eye position
        0.0, 0.0, 0.0,     // Look-at point
        0.0, 1.0, 0.0);    // Up vector

    glRotatef(angle, 0.0, 1.0, 0.0);     // Rotate the whole scene

    // If not fused yet, animate individual atoms
    if (!fused) {
        drawSphere(h1PosX, 0.0f, 0.0f, 0.3f, 1.0f, 0.0f, 0.0f, "Hydrogen");
        drawSphere(h2PosX, 0.0f, 0.0f, 0.3f, 1.0f, 0.0f, 0.0f, "Hydrogen");
        drawSphere(0.0f, oPosY, 0.0f, 0.5f, 0.0f, 0.0f, 1.0f, "Oxygen");
    }
    // If fused, render a water molecule
    else {
        drawSphere(0.0f, 0.0f, 0.0f, 0.5f, 0.0f, 0.0f, 1.0f, "Oxygen");
        drawSphere(-0.7f, 0.4f, 0.0f, 0.3f, 1.0f, 0.0f, 0.0f, "Hydrogen");
        drawSphere(0.7f, 0.4f, 0.0f, 0.3f, 1.0f, 0.0f, 0.0f, "Hydrogen");
    }

    // Display 2D info messages after fusion
    if (fused) {
        drawLabel2D(20.0f, 40.0f, "Water (H2O) molecule created!");
        drawLabel2D(20.0f, 20.0f, "2 Hydrogen + 1 Oxygen = Life's Elixir 💧");
    }

    glutSwapBuffers();  // Swap double buffers
}

// Timer-based animation update function
void update(int value) {
    angle += 0.5f;  // Rotate scene slightly for animation

    if (!fused) {
        h1PosX += 0.02f;   // Move hydrogen 1 right
        h2PosX -= 0.02f;   // Move hydrogen 2 left
        oPosY -= 0.02f;   // Move oxygen down

        // Check for collision threshold to "fuse"
        if (h1PosX >= -0.7f && h2PosX <= 0.7f && oPosY <= 0.4f) {
            fused = true;
        }
    }

    glutPostRedisplay();                 // Request redraw
    glutTimerFunc(16, update, 0);       // Call again in 16ms (~60fps)
}

// Handle window resizing
void reshape(int w, int h) {
    if (h == 0) h = 1;
    float aspect = w * 1.0f / h;

    glViewport(0, 0, w, h);              // Set viewport
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective(45.0, aspect, 1.0, 100.0);  // Perspective projection
    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();
}

// Keyboard handler: reset scene on pressing 'r' or 'R'
void keyboard(unsigned char key, int x, int y) {
    if (key == 'r' || key == 'R') {
        angle = 0.0f;
        h1PosX = -2.0f;
        h2PosX = 2.0f;
        oPosY = 2.0f;
        fused = false;
    }
}

// Main function: GLUT setup and loop
int main(int argc, char** argv) {
    glutInit(&argc, argv);                                  // Initialize GLUT
    glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB | GLUT_DEPTH); // Double buffering + Depth
    glutInitWindowSize(800, 600);                           // Initial window size
    glutCreateWindow("Water Formation - H + H + O = H2O");  // Window title

    initLighting();             // Initialize lighting and materials
    glutDisplayFunc(display);  // Register display callback
    glutReshapeFunc(reshape);  // Handle window resizing
    glutKeyboardFunc(keyboard); // Register key press callback
    glutTimerFunc(0, update, 0); // Start animation

    glutMainLoop();            // Enter GLUT event loop
    return 0;
}   
