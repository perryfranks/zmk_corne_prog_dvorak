# ZMK Corne V3 Programmer Dvorak Layout

A simple but complete implementation of the Programmer Dvorak layout by Roland Kaufmann in the ZMK framework for the spit keyboard the Corne V3 by foostan. 

This was made by referencing [this](https://github.com/JReneHS/crkb_conf/tree/main/rene_prog_dvorak) layout by JReneHS. Apart from this I found little resources, especially for ZMK for this layout so I have dicided to host mine. 

### Deviations from the original layout: 
Apart from some adjustments made to transfer the layout to smaller number of keys. The main deviation is in the modeling of the number/symbol keys still being SHIFT + Number = SYMBOL instead of SHIFT + SYMBOL = NUMBER. This was mainly a consideration for one handed use as symbols and numbers are seperated by different layers already. 

This can be altered by changing the [mod-morph](https://zmk.dev/docs/behaviors/mod-morph) definitions and swapping the order of the keys in the bindings section and double-checking their placement. 

    bindings = <&kp N7>, <&kp LBKT>;  --> bindings = <&kp LBKT>, <&kp N7>;
## Installation

Refer to the ZMK getting started instruction for the installation & flashing process: https://zmk.dev/docs. From there the corne.keymap can be simply copy into an existing config.


## Usage

```python
import foobar

# returns 'words'
foobar.pluralize('word')

# returns 'geese'
foobar.pluralize('goose')

# returns 'phenomenon'
foobar.singularize('phenomena')
```
## Credits & References
 
Programmer-Dvorak Layout: https://www.kaufmann.no/roland/dvorak/

Original layout by [Juan René Hernández Sánchez](https://github.com/JReneHS) (JReneHS): https://github.com/JReneHS/crkb_conf/tree/main/rene_prog_dvorak

ZMK: https://zmk.dev

Corne keyboard by [Kosuke Adachi](https://github.com/foostan) (foostan): https://github.com/foostan/crkbd
 
 
## Contributing

Pull requests are welcome. This was a simple layout I wanted without knowing too much about ZMK. Expansions, remixes and so on are welcome as well as publish your own repos.  

## License

It's a single file and I don't mind what you do with it. Includes work from ZMK so refer to that. 