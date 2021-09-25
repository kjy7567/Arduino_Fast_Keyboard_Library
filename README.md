How to Use
------

    void loop() {
      if(!digitalRead(8)){
        _keyReport = _keyReport = Keyboard.press_key(_keyReport, KEY_F10);
      }
      else if(digitalRead(8)){
        _keyReport = _keyReport = Keyboard.release_key(_keyReport, KEY_F10);
      }
      if(!digitalRead(9)){
        _keyReport = _keyReport = Keyboard.press_key(_keyReport, '-');
      }
      else if(digitalRead(9)){
        _keyReport = _keyReport = Keyboard.release_key(_keyReport, '-');
      }
      if(!digitalRead(10)){
        _keyReport = _keyReport = Keyboard.press_key(_keyReport, '[');
      }
      else if(digitalRead(10)){
        _keyReport = _keyReport = Keyboard.release_key(_keyReport, '[');
      }
      if(!digitalRead(16)){
        _keyReport = _keyReport = Keyboard.press_key(_keyReport, '\'');
      }
      else if(digitalRead(16)){
        _keyReport = _keyReport = Keyboard.release_key(_keyReport, '\'');
      }
    ......
    Keyboard.sendReport(&_keyReport); //only call once at the loop's end
    }
