#include <arduino.h>
#include <SoftwareSerial.h>
#include <nmea.h>

TinyGPS gps;
SoftwareSerial serGPS(14, 12, false, 256);     //14 é D5 ;  12 é D6

static void smartdelay(unsigned long ms);
byte month, day, hour, minute, second, hundredths;
int year;
unsigned long age;

NMEA nmeaDecoder(ALL);

void setup()
{
  Serial.begin(19200);
  serGPS.begin(9600);
}

void loop()
{
  if (serGPS.available())
  {
     if (nmeaDecoder.decode(serGPS.read()))
     {
      Serial.println(nmeaDecoder.sentence());  // print it
     }
   }
}
