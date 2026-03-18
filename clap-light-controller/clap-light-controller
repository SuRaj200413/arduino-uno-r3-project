int soundPin = 2;    // Digital pin connected to the sound sensor's DO pin
int ledPin = 13;     // Pin connected to the LED
int soundState = 0;  // Variable to store the sound sensor state
int lastSoundState = 0; // To detect when the sound changes
bool ledState = LOW; // Track the state of the LED (on/off)

void setup() {
  pinMode(soundPin, INPUT);  // Set sound sensor pin as input
  pinMode(ledPin, OUTPUT);   // Set LED pin as output
  Serial.begin(9600);        // Initialize serial communication
}

void loop() {
  soundState = digitalRead(soundPin);  // Read the sound sensor's digital output

  // Detect the change in sound (a "clap" should cause a short change)
  if (soundState == HIGH && lastSoundState == LOW) {
    ledState = !ledState;  // Toggle the LED state (if it's ON, turn it OFF and vice versa)
    digitalWrite(ledPin, ledState);  // Set the LED to the new state
    delay(500);  // Debounce delay to prevent multiple toggles from one clap
  }

  lastSoundState = soundState;  // Update last sound state
}

