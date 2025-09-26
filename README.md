# Arduino-script-2
For saving in note 
# Sanitized Notepad Save Demo — Arduino HID (Benign)

This repository contains a **benign Arduino HID demo sketch**:  
`sanitized_notepad_save_demo.ino`

It shows how an Arduino-compatible board that can emulate a USB keyboard can send a sequence of keystrokes to Windows in order to:

1. Open the Run dialog (`Win + R`)
2. Launch Notepad
3. Type a friendly message
4. Save the file as `hello_world_demo.txt`
5. Close Notepad

This demo is **safe**: it does not disable security software, capture keystrokes, or perform any harmful action. Its only effect is creating a harmless text file with a message.

---

## Requirements

- [Arduino IDE](https://www.arduino.cc/en/software) (or `arduino-cli`)
- An Arduino-compatible board that supports native USB HID:
  - Arduino Leonardo  
  - Arduino Micro  
  - SparkFun Pro Micro  
  - Any other ATmega32u4-based board
- A USB cable and a test machine (preferably isolated)

---

## How to Use

1. Open Arduino IDE.  
2. Create a new sketch and paste the contents of `sanitized_notepad_save_demo.ino`.  
3. Select your board type (e.g., **Arduino Leonardo**) under **Tools → Board**.  
4. Select the correct **Port** under **Tools → Port**.  
5. Click **Verify** to compile.  
6. Click **Upload** to flash the board.  
7. Connect the board to your Windows test machine.  
8. After a short delay, the board will:
   - Open Notepad  
   - Type `Hello, world!`  
   - Save it as `hello_world_demo.txt`  
   - Close Notepad  

---

## Safe Testing Checklist

- ✅ Use a test machine or an isolated VM with USB passthrough.  
- ✅ Take a snapshot/backup before testing.  
- ✅ Do not keep sensitive documents open.  
- ✅ Do not run this on production systems.  
- ✅ Obtain permission if using on a device you don’t own.  

---

## Troubleshooting

- **Message appears too early / Notepad not open:**  
  Increase `delay()` values after launching Notepad.

- **Filename typed incorrectly / Save dialog too slow:**  
  Increase the delay after `Ctrl+S` before typing the filename.

- **Notepad doesn’t close with Alt+F4:**  
  Some keyboard libraries don’t support `KEY_F4`. Use the alternative File → Exit sequence if needed (see comments in the sketch).

---

## Disclaimer

This project and its contents are provided **for educational and defensive research purposes only**.  

- Provided **"as is"**, without warranty of any kind.  
- The maintainers are **not responsible** for any damage, data loss, or legal issues caused by misuse of this material.  
- You are solely responsible for ensuring that your use complies with applicable laws and organizational policies.  
- Do **not** use this repository to perform unauthorized testing or compromise systems you do not own or lack explicit permission to test.  

---

## License

Choose a license appropriate for your use case. Suggested:  
- [MIT License](https://opensource.org/licenses/MIT) for permissive reuse  
- [CC BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/) for educational-only sharing
