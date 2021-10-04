Description
------
The default Arduino keyboard library calls sendReport every time a switch is pressed or released. 
That's very inefficient, so you can speed up the latency by only calling sendReport once at the end after a key scan.

How to Use
------
    #include <Keyboard.h>
    KeyReport _keyReport;

    void setup() {

      pinMode(2, OUTPUT);
      pinMode(3, OUTPUT);
      pinMode(4, OUTPUT);
      pinMode(5, OUTPUT);

      pinMode(8, INPUT_PULLUP);
      pinMode(9, INPUT_PULLUP);
      pinMode(10, INPUT_PULLUP);
      pinMode(16, INPUT_PULLUP);
      pinMode(14, INPUT_PULLUP);
      pinMode(15, INPUT_PULLUP);

      digitalWrite(2, LOW);
      digitalWrite(3, LOW);
      digitalWrite(4, LOW);
      digitalWrite(5, LOW);

    }
    void loop() {
      if(!digitalRead(8)){
        _keyReport = Keyboard.press_key(_keyReport, KEY_F10);
      }
      else if(digitalRead(8)){
        _keyReport = Keyboard.release_key(_keyReport, KEY_F10);
      }
      if(!digitalRead(9)){
        _keyReport = Keyboard.press_key(_keyReport, '-');
      }
      else if(digitalRead(9)){
        _keyReport = Keyboard.release_key(_keyReport, '-');
      }
      if(!digitalRead(10)){
        _keyReport = Keyboard.press_key(_keyReport, '[');
      }
      else if(digitalRead(10)){
        _keyReport = Keyboard.release_key(_keyReport, '[');
      }
      if(!digitalRead(16)){
        _keyReport = Keyboard.press_key(_keyReport, '\'');
      }
      else if(digitalRead(16)){
        _keyReport = Keyboard.release_key(_keyReport, '\'');
      }
    ......
    Keyboard.sendReport(&_keyReport); //only call once at the loop's end
    }
