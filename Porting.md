Following are some notes on how to port KOReader to other platforms.

There are mainly two modules that you need to take care of: input and output.
After you finish these two, KOReader should have no problem running on your
platform.


## Output Module

KOReader uses framebuffer to control EInk devices, so the output module here is
[einkfb.c][einkfb-c]. You can find this file in koreader-base framework. The
koreader-base framework used to be part of KOReader, but we later factored it
out and use it in KOReader as submodule.

Following are the framebuffers that `einkfb.c` currently supports:
  * 4BPP inverted framebuffer
  * 16 scale 8BPP inverted framebuffer
  * 16 scale 8BPP framebuffer

For 4BPP framebuffer, it means every pixel is represented with 4 bits, so we
have 2 pixels in 1 byte. So the color depth is 16. The inverted part means all
the bits are flipped in the framebuffer. For example, two pixels `[0x00, 0xf0]`
will be stored as `0xff0f` in framebuffer.

For 16 scale 8BPP framebuffer, it means each pixel is instead stored in 1 byte,
but the color depth is still 16 (4bits). Since 1 byte has 8 bits, so to fill
up the remaining space, the most significant 4 bits is a copy of the least
significant one. For example, pixel with grey scale 15 will be represented as
`0xffff`. If it's a inverted 16 scale 8BPP framebuffer, then all the bits are
flipped in the same way as 4BPP inverted framebuffer does.

If your device's framebuffer does not fit into any of the categories above,
then you need to add a new transformation function in `einkfb.c`.

The `einkfb.c` module works in following ways for non 4BPP framebuffers;
  * a shadow buffer is created and structured as 4BPP inverted framebuffer.
  * all updates on screen bitmap are temporally written into the shadow buffer.
  * each time we want to reflect the updated bitmap on screen, we translate
    the shadow buffer into a format that the real framebuffer understands and
    write into the mapped memory region. (varies on devices)
  * call ioctl system call to refresh EInk screen. (varies on devices)

KOReader will handle the 4BPP shadow buffer for you, all you need to do is to
teach `einkfb.c` how to control the EInk screen and translate the 4BPP inverted
bitmap into the format that your framebuffer understands.

In `openFrameBuffer()` function, the value for a function pointer
`einkUpdateFunc` is assigned according to devices' model. This function is
called on every screen refresh. It transforms the shadow buffer and write the
result into framebuffer. Then it calls ioctl to refresh the screen.

So you need to write a einkUpdateFunction for your device's framebuffer and
assigned it to `einkUpdateFunc` on eink open. You may want to refer to
`kindle51einkUpdate()`, `kindle4einkUpdate()` and `kindle3einkUpdate()`
functions for real examples.



## Input Module

We have a `input.c` module in [koreaer-base][bk-framework] that reads input
events from Linux's input system and pass to Lua frontend. Basically, you don't
need to change on that module because it should support most of the events.

For this part, the file you have to hack on is [inputevent.lua][inputev].

Firstly, you need to tell which input deivce to open on KOReader start. All the
input devices are opened in `Input:init()` function.

Next, you might need to define `Input:eventAdjustHook()` function in
`Input:init()` method. We use this hook function to translates events into a
format that KOReader understands. You can look at the KindleTouch initialization code for real example.

Linux supports two kinds of Multi-touch protocols:
 * http://www.kernel.org/doc/Documentation/input/multi-touch-protocol.txt

Currently, KOReader only supports protocol B, so if your device sends out
protocol A, you need to adapt it in the hook function and simulate protocol B.
Also you are welcome to send a PR that adds protocol A support to KOReader.

More information on Linux's input system:
 * http://www.kernel.org/doc/Documentation/input/event-codes.txt
 * http://www.kernel.org/doc/Documentation/input/input.txt



[einkfb-c]:https://github.com/koreader/koreader-base/blob/master/einkfb.c
[kb-framework]:https://github.com/koreader/koreader-base
[inputev]:https://github.com/koreader/koreader/blob/master/frontend/ui/inputevent.lua

