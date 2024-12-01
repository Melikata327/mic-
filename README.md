# mic-
### نام ازمایش 
  ماشین حساب  با key pad
  ----
### ابزار مورد نیاز:
key pad،برد اردینو ،سیم مخابراتی


### شرح ازمایش:
از keypadپایه 1 به پایه دیجیتال9 اردینو و همین طوربه پایه 2 کی پد به پایه8 اردینو   
به همین ترتیب تا اخر ادامه پیدا کند
سپس کتابخانه را ادد میکنیم در قسمت اسکیچ 
با ادد کردن کتابخانه 
کد:
```cpp
#include <Keypad.h>

const byte ROWS = 4; //four rows
const byte COLS = 4; //four columns

char keys[ROWS][COLS] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};

byte rowPins[ROWS] = {9, 8, 7, 6}; //connect to the row pinouts of the keypad
byte colPins[COLS] = {5, 4, 3, 2}; //connect to the column pinouts of the keypad

//Create an object of keypad
Keypad keypad = Keypad( makeKeymap(keys), rowPins, colPins, ROWS, COLS );

void setup(){
  Serial.begin(9600);
}
  
void loop(){
  char key = keypad.getKey();// Read the key
  
  // Print if key pressed
  if (key){
    Serial.print("Key Pressed : ");
    Serial.println(key);
  }
}
# mic-
