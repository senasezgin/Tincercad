# Tincercad
// pin to which the RGB LED pins are connected
const int GREEN = 9;
const int BLUE = 10;
const int RED = 11;
  
// color transition time
const int delayTime = 20;
  
void setup () {
  
  // set the digital pin as output
  pinMode (GREEN, OUTPUT);
  pinMode (BLUE, OUTPUT);
  pinMode (RED, OUTPUT);
  
  
  // set the GREEN, BLUE, RED pins to HIGH
  // initially the RGB LED will be off
  digitalWrite (GREEN, HIGH);
  digitalWrite (BLUE, HIGH);
  digitalWrite (RED, HIGH);
}
  
// definition of global variables
int ValGreen;
  
void loop () {
  // gradual turning off of the green
  
  // RGB coordinates of red: 0, 255, 0
  
  ValGreen = 255;
  
  for (int i = 0; i <255; i += 1) {
  
    ValGreen -= 1;
  
    /* for every cycle the difference
     255 - ValVerde INCREASES
     causing a gradual shutdown of the green
     */
  
    analogWrite (GREEN, 255 - ValGreen);
  
    // wait for 20 ms to perceive the color
    delay (delayTime);
  }
}
