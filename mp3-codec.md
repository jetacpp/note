# MP3 Encoder / Decoder in C

## MAD (`libmad`)

```
$ sudo apt-get install madplay libmad0-dev
```

MAD (`libmad`) is a high-quality MPEG audio decoder. It currently supports MPEG-1 and the MPEG-2 extension to Lower Sampling Frequencies, as well as the so-called MPEG 2.5 format. All three audio layers (Layer I, Layer II, and Layer III a.k.a. MP3) are fully implemented.

MAD does not yet support MPEG-2 multichannel audio (although it should be backward compatible with such streams) nor does it currently support AAC.

MAD has the following special features:

- 24-bit PCM output
- 100% fixed-point (integer) computation
- completely new implementation based on the ISO/IEC standards
- distributed under the terms of the GNU General Public License (GPL)

> http://m.baert.free.fr/contrib/docs/libmad/doxy/html/index.html

## `mpg123` / `libmpg123`

```
$ sudo apt-get install mpg123 libmpg123-dev
```

`mpg123` is a console mpeg audio decoder/player.

`libmpg123` is the decoder part of mpg123 is usable as a library in application.

Features include:
- decoding of MPEG 1.0/2.0/2.5 layer I/II/III audio streams to interleaved PCM, also free-format bitrates over 320 kbit/s
- sample-accurate seeking and gapless playback (via LAME Info frame)
- choice of sample encoding (from 8 bit µlaw to 32 bit float), mono mix
- build-time choice for integer or floating-point synth
- assembly/SIMD optimisations for common sample encodings and decoding modes
- choices between accuracy and efficiency (rounding modes, dithering)
- efficient 2:1 or 4:1 downsampling, sparing decoder work to evaluate the dropped samples
- n:m pseudo-resampler (repeat/drop samples without interpolation) as last resort to enable playback with enforced sample rate
- tune frequency scale factors for zero-cost equaliser (with 32 linearly-spaced bands given my MPEG; not pretty, but hey, it's free!)
- tune volume via scale factors, again without extra CPU cost
- parse and apply relative volume adjustment read from metadata (RVA2, ReplayGain)
- parse ID3v1, ID3v2 and ICY stream metadata (with configured interval), silenty skip other stuff
- graceful handling of stream errors (silence instead of whiny twittering)
- disabling of features to enable smaller builds for embedded systems (a generic x86-64 float-output binary of from mpg123-1.23.0 using gcc-4.9.2 with -Os is 118 KiB stripped, still with all the essential sample-accurate codec functionality)

> http://www.mpg123.de

## LAME

```
$ sudo apt-get install lame libmp3lame-dev
```

LAME is a high quality MPEG Audio Layer III (MP3) encoder licensed under the LGPL.

LAME features:
- Many improvements in quality in speed over ISO reference software. See history.
- MPEG1,2 and 2.5 layer III encoding.
- CBR (constant bitrate) and two types of variable bitrate, VBR and ABR.
- Encoding engine can be compiled as a shared library (Linux/UNIX), DLL , Directshow filter or ACM codec (Windows).
- Free format encoding and decoding.
- GPSYCHO: a GPL'd psycho acoustic and noise shaping model.
- Powerful and easy to use presets.
- Quality better than all other encoders at most bitrates.
- Fast! Encodes faster than real time on a PII 266 at highest quality mode.
- MP3x: a GTK/X-Window MP3 frame analyzer for both .mp3 and unencoded audio files.

> http://lame.sourceforge.net

## Reference

- https://en.wikipedia.org/wiki/MPEG_Audio_Decoder
- https://en.wikipedia.org/wiki/Mpg123
- https://en.wikipedia.org/wiki/LAME
- https://www.mars.org/mailman/public/mad-dev/2001-October/000369.html