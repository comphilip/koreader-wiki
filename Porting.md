Following are some notes on how to port KOReader to other platforms:

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


## Input Module



[einkfb-c]:https://github.com/koreader/koreader-base/blob/master/einkfb.c
[kb-framework]:https://github.com/koreader/koreader-base

