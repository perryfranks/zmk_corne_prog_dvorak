# ZMK Corne V3 Programmer Dvorak Layout

A simple but complete implementation of the Programmer Dvorak layout by Roland Kaufmann in the ZMK framework for the spit keyboard the Corne V3 by foostan. 

This was made by referencing [this](https://github.com/JReneHS/crkb_conf/tree/main/rene_prog_dvorak) layout by JReneHS. Apart from this I found little resources, especially for ZMK for this layout so I have dicided to host mine. 



I have included a primative layout diagram for reference in the config folder, guide.txt and print_friendly.txt.

### Deviations from the original layout: 
Apart from some adjustments made to transfer the layout to smaller number of keys. The main deviation is in the modeling of the number/symbol keys still being SHIFT + Number = SYMBOL instead of SHIFT + SYMBOL = NUMBER. This was mainly a consideration for one handed use as symbols and numbers are seperated by different layers already. 

This can be altered by changing the [mod-morph](https://zmk.dev/docs/behaviors/mod-morph) definitions and swapping the order of the keys in the bindings section and double-checking their placement. 

    bindings = <&kp N7>, <&kp LBKT>;  --> bindings = <&kp LBKT>, <&kp N7>;
## Installation

There are several ways to start using this package. 
- Incorporate into existing repo: Refer to the ZMK getting started instruction for the installation & flashing process: https://zmk.dev/docs. From there the corne.keymap can be simply copy into an existing config.
- Fork this repo, make your changes and then get the firmware in the normal way using github actions
- If you don't need to make any changes you can simply grab the firmware from the github actions and get typing


## Usage

I recommend printing off a copy of the layout guide if learning dvorak. 

This keymap features a number of Tap-dance & mod-morph defines as well as a number #defined values to make setting up the layout more readable and concise. For the most part the defined functions can be included in the keymap without needing to understand their implementations. Just their behaviour and [key codes](https://zmk.dev/docs/codes) they put out. 

Refer to the comments in corne.keymap full definitions
```
// include name or reference in keymap
// Format: 
//      name        reference  key1 key2 
#define TD_TAB      &td0    // TAB ESC
#define TD_CAPLOCK  &td1    // LSHIFT CAPSLOCK 
#define TD_SPC      &td2    // SPACE ENTER 
#define TD_SLSH     &td3    // SLASH QMARK
#define TD_QUOTE    &td4    // QUOTE DOUBLE_QUOTES
#define TD_EQL      &td5    // EQUAL PLUS
#define TD_BSLS     &td6    // BACKSLASH PIPE 
#define TD_MINUS    &td7    // MINUS UNDERSCORE
#define TD_SCLN     &td8    // SEMICOLON COLON 
#define TD_COMM     &td9    // COMMA LESS_THAN 
#define TD_DOT      &td10   // PERIOD GREATER_THAN 
#define TD_BACKF    &td11   // GRAVE TILDE
#define TD_ALT      &td12   // LALT GUI
#define TD_ARR      &td13   // Q AT (@)
#define TD_ATCAT    &td14   // AT CARET 
```
Names and references prefixed with TD refer to tap-dance functions. Those with the format [number]_[key code] are mod-morph behaviours. They will output the first keycode (the number) but will output the second when shift is held down. 

```
// include &name in keymap to use
// FORMAT
//   natural --> (on shift)
//   number --> symbols | number code --> symbol code 
// one_lpar    1 --> (  | N1 --> LPAR
// two_rpar    2 --> )  | N2 --> RPAR
// three_rbrc  3 --> }  | N3 --> RBRC
// four_pl     4 --> ]  | N4 --> PLUS
// five_lbrc   5 --> {  | N5 --> RSFT
// six_rbkt    6 --> ]  | N6 --> RBKT
// seven_lbkt  7 --> [  | N7 --> LBKT
// eight_exlm  8 --> !  | N8 --> EXCL
// nine_equal  9 --> =  | N9 --> EQUAL
// zero_s      0 --> *  | N0 --> STAR
```
Refer to the ZMK documentation for further documentaion
## Layout Diagram: 
```
 |TAB:ESC | ; : | , < | . > |  P  |  Y  |     | F   |  G   |  C  |  R  |  L  | BKSP|
 |CTRL    |  A  |  O  |  E  |  U  |  I  |     |  D  |  H   |  T  |  N  |  S  | DEL |
 |SFT:CAP | ' " | q @ |  J  |  K  |  X  |     |  B  |  M   |  W  |  V  |  Z  | TAB |
                      | GUI | LWR | SPC |     | ENT | RSE  | ALT |
           
lower_layer: numbers, navigation, and FUN keys
 |ESC    |  7   |  5  |  3  |  1  |  9  |     |  0  |  2  |  4  |  6  |  8  |     |
 |F11    |  F1  |  F2 |  F3 |  F4 |  F5 |     | LFT | DWN |  UP | RGT |     |     |
 |SHFT   |  F6  |  F7 |  F8 |  F9 |  F10|     |HOME | PGDN| PGUP| END |     |     |
                      |     |     |     |     |     |     |     |

raise_layer: symbols 
 |ESC    |  [   |  {  |  }  |  (  |  =  |     |  *  |  )  |  +  |  ]  |  !  | DEL |
 |CTRL   |  ~   |  %  |  `  | / ? | @ ^ |     |     |     |     |     |     |     |
 |SHFT   |  $   |  &  |  #  | - _ | \ | |     |     |     |     |     |     |     |
                      | GUI |     | SPC |     | ENT |     | ALT |

bt_media_layer: BT functions and media controls
 |ESC    |      |     |     |     |     |     |     |     |     |     |     |     | 
 |BTCLR  | BT1  | BT2 | BT3 | BT4 | BT5 |     | LFT | PRV | PP  | NXT |     |     |
 |SHFT   |      |     |     |     |     |     | MUTE| V-  | V+  |     |     |     |
                      | GUI |     | SPC |     | ENT |     | ALT |
```

Legends like '/ ?' are tap-dance keys. Pressing once will output '/', double tap outputs '?'. 

## Credits & References
 
Programmer-Dvorak Layout: https://www.kaufmann.no/roland/dvorak/

Original layout by [Juan René Hernández Sánchez](https://github.com/JReneHS) (JReneHS): https://github.com/JReneHS/crkb_conf/tree/main/rene_prog_dvorak

ZMK: https://zmk.dev

Corne keyboard by [Kosuke Adachi](https://github.com/foostan) (foostan): https://github.com/foostan/crkbd
 
 
## Contributing

Pull requests are welcome. This was a simple layout I wanted without knowing too much about ZMK. Expansions, remixes and so on are welcome as well as publish your own repos.  

## License

It's a single file and I don't mind what you do with it. Includes work from ZMK so refer to that. 