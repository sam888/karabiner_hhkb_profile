# karabiner_hhkb_profile

**Karabiner-Elements profile for HHKB or 60% keyboard**

This project will provide HOW-To instructions to configure Karabiner-Elements in Mac so user can press a single number key
(i.e. 1, 2, 3,... 9, 0, -, =) to trigger a function key (i.e. F1, F2,... , F9, F10, F11, F12) on a HHKB(i.e. Happy Hacking
Keyboard) or 60% keyboard.

![](profile/images/hhkb-pro-2.jpg)

<br/>

**Motivation**

By default, A function key (e.g. F1) can be registered by pressing down the Fn key on bottom right corner and Number 1 key
on top left at the same time. This required two hands to pull it off. Things only get worse if you need to press three keys
involving a function key at the same time, e.g. F7+Ctrl+Shift. And yes, good developers do enjoy pressing three keys as
shortcut in their favorite IDE(e.g. IntelliJ) to make things happen instead of using mouse to navigate and click around.
But with a 60% keyboard, that is really pushing the limit of your hand doing Mudra. 🙌

So what's the point of using an expensive(_supposedly cool_) **HHKB** keyboard if it's only going to make your life
difficult during development in your favorite IDE?... No point actually except for the [bragging right](https://www.youtube.com/watch?v=uHt01D6rOLI) in the office! 😆
<br/>

Naturally anyone with good common sense will start looking for a free open source key remapping software. Out of this
comes the tested solution in this guide, something I wish I had known much earlier when I first got my HHKB several years
ago... _You are welcome_.

<br/>

**Design**

A mechanism will be required to switch the layout of keyboard such that the following keys

* 1, 2, 3, 4, 5, 6, 7, 8, 9, 0, -, = <br/>
  will be remapped to the following function keys
* F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, F11, F12 <br/>

Then user can simply press a key to register a function key **with a single hand** before quickly switching back to
original layout.

Switching layout will be done by pressing down both the right Command + right Alt keys(these are what's called the
modifier keys) then click right Shift. See highlighted keys in image above. Repeating it again will switch back to
original layout.

<br/>

**Instructions**

Instructions provided here will be for Mac so no luck for Windows user, time to get on with the programme... 😁
Actually for Windows user, your best bet is to use either AutoHotKey or SharpKeys.

1. Install Karabiner-Elements. I am using 14.4.0 at time of writing this.
2. Open the folder **~/.config/karabiner/assets/complex_modifications** then drop the following files in from the provided 'profile' folder

* default-profile.json
* my-profile.json
* number-to-fn.json

3. Open *Karabiner-Elements*, go to *Profiles* tab and add two profiles, 'MyProfile' and 'default profile'. See

   ![](profile/images/profiles.jpg)
4. Select 'Default profile' as in screenshot above. Click 'Complex modifications' tab to bring up the panel showing a
   list of rules you imported in JSON files above. Click the 'Enable' button for the rule 'Change Profile to MyProfile'.
   See
   ![](profile/images/complex-modifications-0.jpg)

   After that you should see
   ![](profile/images/complex-modifications-1.jpg)

<br/>

5. Repeat step 4 above for MyProfile except this time, pick the rule "Change profile to 'Default profile'" to enable in
   'Complex modifications' tab. Also enable the rule 'Exchange numbers to Fn keys...' while you are at it. Now you should
   have
   ![](profile/images/complex-modifications-2.jpg)

If you make it this far, congratulation, you can now quickly do Cmd+Shift+F9 as if you are using a full size or 80% keyboard
in IntelliJ after quickly switching layout to confuse the hell out of your colleague who is watching. If colleague asks
how, let him try and fails then tell him he needs to be the chosen ONE to make it work. 😆

<br/>

**Issues...**

One flaw of using Karabiner-Elements with HHKB in Mac is that the character **`** will get interpreted as **§**. But this can be
solved by adding more customization in Karabiner-Elements. In 'Simple modifications' tab, simply add the config below.

![](profile/images/simple-modifications.jpg)

<br/>

**Exercises**

Many mechanical keyboards have dedicated knob or buttons to adjust and mute volume to justify its high price.
These can be replicated easily in Karabiner-Elements by remapping

* _Print Screen_ key to Mute Sound
* _Num Lock_ key to Increase volume
* _Pause_ key to Decrease volume

Do these by adding three elements in 'Simple modifications' tab. Will leave it as exercise to the user. ;)

Note if you want to create your own rules in JSON files to import into 'Complex modifications' tab, Karabiner-EventViewer
lets you click the key you want and print out the key code of pressed key. Handy for remapping keys.
