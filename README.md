# lukkojuttu
Lukkojuttu Ardulle napit pinneihin 0-3 ledit tms outputit pinneihin 5-8 ja viimeinen pin 9siin.
9 pin aktivoituu kun pinnit 5-8 on aktiivisia.
Lankkuna Uno, napeissa käytetty sisäisiä Pullup vastuksia.

**********Koodi alkaa************************

int buttonPin0 = 0;
int buttonPin1 = 1;
int buttonPin2 = 2;
int buttonPin3 = 3;

int ledPin6 = 5;
int ledPin7 = 6;
int ledPin8 = 7;
int ledPin9 = 8;

int lukko = 9;

int held = 5;

int ledState6 = LOW;
int ledState7 = LOW;
int ledState8 = LOW;
int ledState9 = LOW;
int lukkoState = LOW;

int buttonState0;
int buttonState1;
int buttonState2;
int buttonState3;

int lastButtonState0 = HIGH;
int lastButtonState1 = HIGH;
int lastButtonState2 = HIGH;
int lastButtonState3 = HIGH;

long lastDebounceTime0 = 0;
long lastDebounceTime1 = 0;
long lastDebounceTime2 = 0;
long lastDebounceTime3 = 0;

long debounceDelay = 50;

void setup()
{
  pinMode(buttonPin0, INPUT_PULLUP);
  pinMode(buttonPin1, INPUT_PULLUP);
  pinMode(buttonPin2, INPUT_PULLUP);
  pinMode(buttonPin3, INPUT_PULLUP);

  pinMode(ledPin6, OUTPUT);
  pinMode(ledPin7, OUTPUT);
  pinMode(ledPin8, OUTPUT);
  pinMode(ledPin9, OUTPUT);
  pinMode(lukko, OUTPUT);

  digitalWrite(ledPin6, ledState6);
  digitalWrite(ledPin7, ledState7);
  digitalWrite(ledPin8, ledState8);
  digitalWrite(ledPin9, ledState9);
  digitalWrite(lukko, lukkoState);
  Serial.begin(9600);
}

void loop()
{

  int reading0 = digitalRead(buttonPin0);
  int reading1 = digitalRead(buttonPin1);
  int reading2 = digitalRead(buttonPin2);
  int reading3 = digitalRead(buttonPin3);
  Serial.write(buttonPin0);

  if (reading0 != lastButtonState0)
  {
    lastDebounceTime0 = millis();

  }
  if (buttonState0 == LOW )
  {
    ledState6 == HIGH;
  }

digitalWrite(ledPin6, ledState6);
lastButtonState0 = reading0;

if (reading1 != lastButtonState1)
{
  lastDebounceTime1 = millis();
}

if ((millis() - lastDebounceTime1) > debounceDelay)
{

  if (reading1 != buttonState1)
  {
    buttonState1 = reading1;
    if (buttonState1 == LOW && held == 5)
    {
      ledState7 == LOW;
    }


  }
}
digitalWrite(ledPin7, ledState7);
lastButtonState1 = reading1;


if (reading2 != lastButtonState2)
{
  lastDebounceTime2 = millis();
}

if ((millis() - lastDebounceTime2) > debounceDelay)
{

  if (reading2 != buttonState2)
  {
    buttonState2 = reading2;
    if (buttonState2 == LOW && held == 5)
    {
      ledState8 == LOW;
    }


  }
}
digitalWrite(ledPin8, ledState8);
lastButtonState2 = reading2;


if (reading3 != lastButtonState3)
{
  lastDebounceTime3 = millis();
}

if ((millis() - lastDebounceTime3) > debounceDelay)
{

  if (reading3 != buttonState3)
  {
    buttonState3 = reading3;
    if (buttonState3 == LOW && held == 5)
    {
      ledState9 == LOW;
    }


  }
}
digitalWrite(ledPin9, ledState9);
lastButtonState3 = reading3;



if (ledState6 && ledState7 && ledState8 && ledState9) {
  lukko == LOW ;
}
}


*************koodiloppuu*********************************
