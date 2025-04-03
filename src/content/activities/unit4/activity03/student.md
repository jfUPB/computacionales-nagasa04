``` c++
#include "ofApp.h"

//--------------------------------------------------------------
void ofApp::setup() {
    ofBackground(0);
}

//--------------------------------------------------------------
void ofApp::update() {
    backgroundHue += 0.2;
    if (backgroundHue > 255) backgroundHue = 0;

    // Agregar un nuevo trazo si el mouse está presionado.
    if (ofGetMousePressed()) {
        float x = ofGetMouseX();
        float y = ofGetMouseY();
        float radius = ofRandom(5, 15);
        ofColor color = ofColor::fromHsb(ofRandom(255), 200, 255);
        float opacity = ofRandom(100, 255);
        strokes.enqueue(x, y, radius, color, opacity);
    }
}

//--------------------------------------------------------------
void ofApp::draw() {
    // Fondo con gradiente dinámico
    ofColor color1, color2;
    color1.setHsb(backgroundHue, 150, 240);
    color2.setHsb(fmod(backgroundHue + 128, 255), 150, 240);
    ofBackgroundGradient(color1, color2, OF_GRADIENT_LINEAR);

    // Dibujar los trazos almacenados en la cola.
    Node* current = strokes.front;
    while (current != nullptr) {
        ofSetColor(current->color, current->opacity);
        ofDrawCircle(current->x, current->y, current->radius);
        current = current->next;
    }
}
```

``` c++
#pragma once
#include "ofMain.h"

// Nodo de la cola
struct Node {
    float x, y;
    float radius;
    ofColor color;
    float opacity;
    Node* next;

    Node(float _x, float _y, float _radius, ofColor _color, float _opacity)
        : x(_x), y(_y), radius(_radius), color(_color), opacity(_opacity), next(nullptr) {
    }
};

// Implementación manual de una cola (FIFO)
class BrushQueue {
public:
    Node* front;
    Node* rear;
    int size;
    int maxSize;

    BrushQueue(int _maxSize);
    ~BrushQueue();

    void enqueue(float x, float y, float radius, ofColor color, float opacity);
    void dequeue();
    void clear();
    bool isEmpty();
};

// Constructor
BrushQueue::BrushQueue(int _maxSize) : front(nullptr), rear(nullptr), size(0), maxSize(_maxSize) {}

// Destructor
BrushQueue::~BrushQueue() {
    clear();
}

// Agregar un nodo al final y eliminar el más antiguo si excede `maxSize`
void BrushQueue::enqueue(float x, float y, float radius, ofColor color, float opacity) {
    Node* newNode = new Node(x, y, radius, color, opacity);

    if (rear == nullptr) {
        // Si la cola está vacía
        front = rear = newNode;
    }
    else {
        rear->next = newNode;
        rear = newNode;
    }

    size++;

    // Si la cola supera el tamaño máximo, eliminar el nodo más antiguo
    if (size > maxSize) {
        dequeue();
    }
}

// Eliminar el nodo más antiguo
void BrushQueue::dequeue() {
    if (front == nullptr) return; // La cola está vacía

    Node* temp = front;
    front = front->next;
    delete temp;
    size--;

    // Si la cola queda vacía, actualizar `rear`
    if (front == nullptr) {
        rear = nullptr;
    }
}

// Eliminar todos los nodos de la cola
void BrushQueue::clear() {
    while (!isEmpty()) {
        dequeue();
    }
}

// Retorna si la cola está vacía
bool BrushQueue::isEmpty() {
    return front == nullptr;
}

// Clase principal de la aplicación
class ofApp : public ofBaseApp {
public:
    BrushQueue strokes; // Cola de trazos
    float backgroundHue = 0;

    ofApp() : strokes(50) {} // Tamaño máximo de la cola

    void setup();
    void update();
    void draw();
};
```
![image](https://github.com/user-attachments/assets/f09b4366-be84-44bb-af7e-aafe1d8d3876)
