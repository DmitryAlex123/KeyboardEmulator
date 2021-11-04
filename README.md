# KeyboardEmulator
Управляемый эмулятор клавиатуры на микроконтроллере STM32xxx 
Запуск команд происходит по отсылке запроса libusb_bulk_transfer(dev_handle, 0x01, data, 64, NULL, 1000); 0x01 - конечная точка приема, data - просто массив 64 байт на третьем месте которого что угодно, но не ноль.

После создания проекта для своего микроконтроллера в Stm32CubeMx вы можете скопировать эти файлы с заменой, точно подойдет для stm32f103c8t6. 
Чтобы установить свои нажатия выберите скан код клавиши и подставьте в pressButton(код клавиши, таймаут до след нажатия).
Если хотите сделать просто кликер без управления по usb, то можете просто убрать if(usb_recive_buf[2] != 0x00) в главном цикле и тогда как только вы подключите устройство, то команды начнут исполняться.


Скан коды: 
  0x04	Keyboard a and A
	0x05	Keyboard b and B
	0x06	Keyboard c and C
	0x07	Keyboard d and D
	0x08	Keyboard e and E
	0x09	Keyboard f and F
	0x0A	Keyboard g and G
	0x0B	Keyboard h and H
	0x0C	Keyboard i and I
	0x0D	Keyboard j and J
	0x0E	Keyboard k and K
	0x0F	Keyboard l and L
	0x10	Keyboard m and M
	0x11	Keyboard n and N
	0x12	Keyboard o and O
	0x13	Keyboard p and P
	0x14	Keyboard q and Q
	0x15	Keyboard r and R
	0x16	Keyboard s and S
	0x17	Keyboard t and T
	0x18	Keyboard u and U
	0x19	Keyboard v and V
	0x1A	Keyboard w and W
	0x1B	Keyboard x and X
	0x1C	Keyboard y and Y
	0x1D	Keyboard z and Z
	0x1E	Keyboard 1 and !
	0x1F	Keyboard 2 and @
	0x20	Keyboard 3 and #
	0x21	Keyboard 4 and $
	0x22	Keyboard 5 and %
	0x23	Keyboard 6 and ^
	0x24	Keyboard 7 and &
	0x25	Keyboard 8 and *
	0x26	Keyboard 9 and (
	0x27	Keyboard 0 and )
	0x28	Keyboard Return (ENTER)
	0x29	Keyboard ESCAPE
	0x2A	Keyboard DELETE (Backspace)
	0x2B	Keyboard Tab
	0x2C	Keyboard Spacebar
	0x39	Keyboard Caps Lock
	0x3A	Keyboard F1
	0x3B	Keyboard F2
	0x3C	Keyboard F3
	0x3D	Keyboard F4
	0x3E	Keyboard F5
	0x3F	Keyboard F6
	0x40	Keyboard F7
	0x41	Keyboard F8
	0x42	Keyboard F9
	0x43	Keyboard F10
	0x44	Keyboard F11
	0x45	Keyboard F12
	0x46	Keyboard PrintScreen
	0x47	Keyboard Scroll Lock
	0x48	Keyboard Pause
	0x49	Keyboard Insert
	0x4A	Keyboard Home
	0x4B	Keyboard PageUp
	0x4C	Keyboard Delete Forward
	0x4D	Keyboard End
	0x4E	Keyboard PageDown
	0x4F	Keyboard RightArrow
	0x50	Keyboard LeftArrow
	0x51	Keyboard DownArrow
	0x52	Keyboard UpArrow
	0x53	Keypad Num Lock and Clear
	0x54	Keypad /
	0x55	Keypad *
	0x56	Keypad -
	0x57	Keypad +
	0x58	Keypad ENTER
	0x59	Keypad 1 and End
	0x5A	Keypad 2 and Down Arrow
	0x5B	Keypad 3 and PageDn
	0x5C	Keypad 4 and Left Arrow
	0x5D	Keypad 5
	0x5E	Keypad 6 and Right Arrow
	0x5F	Keypad 7 and Home
	0x60	Keypad 8 and Up Arrow
	0x61	Keypad 9 and PageUp
	0x62	Keypad 0 and Insert
	0x63	Keypad . and Delete
	0x64	Keyboard Non-US \ and |
	0x65	Keyboard Application
	0x66	Keyboard Power
	0x67	Keypad =
	0x68	Keyboard F13
	0x69	Keyboard F14
	0x6A	Keyboard F15
	0x6B	Keyboard F16
	0x6C	Keyboard F17
	0x6D	Keyboard F18
	0x6E	Keyboard F19
	0x6F	Keyboard F20
	0x70	Keyboard F21
	0x71	Keyboard F22
	0x72	Keyboard F23
	0x73	Keyboard F24
	0x74	Keyboard Execute
	0x75	Keyboard Help
	0x76	Keyboard Menu
	0x77	Keyboard Select
	0x78	Keyboard Stop
	0x79	Keyboard Again
	0x7A	Keyboard Undo
	0x7B	Keyboard Cut
	0x7C	Keyboard Copy
	0x7D	Keyboard Paste
	0x7E	Keyboard Find
	0x7F	Keyboard Mute
	0x80	Keyboard Volume Up
	0x81	Keyboard Volume Down
	0x82	Keyboard Locking Caps Lock
	0x83	Keyboard Locking Num Lock
	0x84	Keyboard Locking Scroll Lock
