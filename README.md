// lcd_running_animation
#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27, 16, 2);

byte run1[8] = {
  B00100,
  B01110,
  B10101,
  B00100,
  B01110,
  B01100,
  B10010,
  B00000
};

byte run2[8] = {
  B00100,
  B01110,
  B10101,
  B00100,
  B01110,
  B00110,
  B01001,
  B00000
};

void setup() {
  lcd.init();
  lcd.backlight();

  lcd.createChar(0, run1);
  lcd.setCursor(0, 0);
  lcd.write(byte(0));
}

void loop() {
  lcd.createChar(0, run1);
  delay(180);
  
  lcd.createChar(0, run2);
  delay(180);
}
