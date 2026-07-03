# Embedded-system task 1
// Automatic Street Light Using LDR and Arduino UNO

int ldrPin = A0;
int ledPin = 13;
int ldrValue = 0;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  ldrValue = analogRead(ldrPin);
  Serial.println(ldrValue);

  if (ldrValue < 500) {
    digitalWrite(ledPin, HIGH); // Dark - LED ON
  } else {
    digitalWrite(ledPin, LOW);  // Bright - LED OFF
  }

  delay(200);
}
