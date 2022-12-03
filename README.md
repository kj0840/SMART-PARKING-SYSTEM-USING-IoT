# SMART-PARKING-SYSTEM-USING-IoT
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 15, 16, 17, 18, 19); int ir1 =
2; int ir2 = 3; int ir3 = 4;
int ir4 = 5; int ir5 = 6; #define a 10 #define b 11 
void setup()
{
Serial.begin(9600); lcd.begin(16, 2); 
lcd.clear(); pinMode(ir1, INPUT); pinMode(ir2, 
INPUT); pinMode(ir3, INPUT); pinMode(ir4, INPUT); 
pinMode(ir5, INPUT);
pinMode(a, OUTPUT); pinMode(b, OUTPUT);
}
void loop()
{
lcd.setCursor(0, 0); lcd.print("Slot1:");
lcd.print(digitalRead(ir1)); lcd.setCursor(7, 0); 
lcd.print(" Slot2:"); lcd.print(digitalRead(ir2)); 
lcd.setCursor(0, 1); lcd.print("Slot3:");
lcd.print(digitalRead(ir3)); lcd.setCursor(7, 1); 
lcd.print(" Slot4:"); lcd.print(digitalRead(ir4)); 
if ((digitalRead (ir1) == 1) && ( digitalRead (ir2)
== 1) && ( digitalRead (ir3) == 1) && ( digitalRead 
(ir4) == 1))
{
lcd.clear(); lcd.print("parking full"); 
delay(1000); digitalWrite(a, LOW); 
digitalWrite(b, LOW);
}
else if ( digitalRead (ir5) == 1)
{
digitalWrite(a, HIGH);digitalWrite(b, LOW); 
delay(280); digitalWrite(a, LOW); 
digitalWrite(b, LOW); delay(5000); 
digitalWrite(a, LOW); digitalWrite(b, HIGH); 
delay(280); digitalWrite(a, LOW); 
digitalWrite(b, LOW); }
digitalWrite(a, LOW); digitalWrite(b, LOW); }
