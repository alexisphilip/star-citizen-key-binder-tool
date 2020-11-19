# Star Citizen Key Binder

Links:
- https://keycode.info/

## XML structure

### XML structure

```xml
<ActionMaps version="1" optionsVersion="2" rebindVersion="2" profileName="keybinding_name">
    <!-- Automatic header -->
    <CustomisationUIHeader label="all_bidings_set" description="" image="">
        <!-- List of user input devices -->
        <devices>
            <keyboard instance="1"/>
            <mouse instance="1"/>
            <joystick instance="1"/>
            <joystick instance="2"/>
        </devices>
    </CustomisationUIHeader>
    <!-- Each 'actionmap' is a section of actions -->
    <actionmap name="spaceship_general">
        <!-- Each 'action' is an action -->
        <action name="v_close_all_doors">
            <!-- There is one 'rebind' per user input -->
            <rebind input="kb1_0"/>
        </action>
    </actionmap>
</ActionMaps>
```

### XML 'action' parameter

Each `action` has the *user input keyword* concatenated with its *instance number*, an *underscore* `_` and the *device's input ID*.

*User input keywords*:
- keyboard: `kb`
- mouse: `mo`
- joystick: `joy`

*Instance number*: `<CustomisationUIHeader>` -> `<devices>` -> `<DEVICE_TYPE instance="INSTANCE_NUMBER">`

*Device input ID*:
- keyboard: keypress `F`, ID = `f`
- mouse: press button 1, ID = `mouse1`

// TODO : describe combo keys, double tap

## List of keys
- **numerical**: [0-9]
- **aphabetical**: [a-zA-Z] (with accents)
- **special char**: &{-]<);
- **modifiers**: F[1-12], Left Alt, Right Ctrl, Tab, Backspace...
- **action keys**: Insert, Home, Arrow Up, ...
  - [see keyboard layout at the end](https://en.wikipedia.org/wiki/Function_key)
- **mouse**:
  - axis: X and Y 
  - buttons: [1-5] and button 3 scroll up & down/up/down

## Things to take into account
- key types:
  - single tap
  - double tap
  - key combo (A + B + C, Left Alt + A, ...)
  - hold
- key heritage
  - gimbal mode (works for flight and mining...)
  - when biding a key (ex: exit seat) ask if the user wants to set it to different types (spaceship + ground vehicle)

## TODO
- show the keybind map for:
  - spaceships:
    - flying (all modes)
    - flying mode (default)
    - scanning mode
    - mining mode
  - ground vehicles:
    - driving (all modes)
    - driving mode (default)
    - mining mode
  - human:
    - movement (all types)
    - on foot
    - EVA
- show the keymap for:
  - keyboards
  - joysticks Thrustmaster T16000M
- add description to all keybindings
- add description to default keyboard keys (write the name and keycode? key ID, SC key ID?)
- add Pause/Break key
- create a new optimized keymap (with double tap (open, close, etc...), and key combos)
- translate to french
- explain how input works : when taping a key, the OS will receive the default american keycode, and then translate it
  to whatever keyboard layout the user is currently using. 