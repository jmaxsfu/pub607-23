# Lecture 4: Digital Audio Fundamentals

We are now shifting from digital text to a consideration of digital audio -- a complete switch of mindset from considering digital text.

Text is a **synthetic** paradigm: we build it up from its component parts: from letters and words, by way of grammar and syntax. 

Audio -- like other continuous or time-based media -- is, by contrast, an **analytic** medium: it begins as a continuous whole, and we take it apart, bit by bit. With text, we can recombine it at will; but with time-based media, *continuity* is critical; any interruptions are jarring to the ear. In her book *Proust and the Squid* Maryann Wolf, writing about speech, says,

> we speak at a rate of about 125 to 180 continuous words per minute, with no acoustic cues at the beginning or end of our words. (Think for a moment how an unknown foreign language sounds to you; it's a continuous, incomprehensible stream of sounds.) Within any language we speak, we know how to segment speech units by virtue of their meaning, grammatical roles, and morphological units, and by the cues provided by rhythm, stress, and intonation. Such information, however, helps very little in knowing where the first sound within a word (its onset) ends and the second sound begins. This is because all sounds are co-articulated, or "shingled together," with one phoneme overlapping with and dictating the pronunciation of the next.

Sound is a pattern of waves in the air that our ears are specially attuned to. The wave pattern is regular and well understood: it goes from the lowest sounds our ears can discern, around 30 waves per second to the highest sounds we can hear, around 20,000Hz (although that upper limit gets lower when you're old, and famously higher if you're a dog).

Technically, we say "cycles per second" or "Hertz" (Hz) after Heinrich Hertz, a 19th-century scientist.

Now, because the speed of sound waves is constant (through a given medium, like air), there's a straightforward inverse relationship between **frequency** (in Hz) and **wavelength**. Lower sounds are low frequency, and have big, long waves: up to 20 metres. High-pitched sounds are high frequency and have short wavelength: a few centimetres, and even shorter if you're a dog.

All the things we hear in sound are about a few simple dynamics: the **frequency** (or pitch), the **amplitude** (or size, which is not quite the same thing as loudness), and the **waveform** shape, which makes for timbre or tone. These three things **modulating** (changing) in time make for the amazing range of things we can hear, listen to, and groove to.

While sound is a continuous waveform in the air that makes tiny hairs inside our ears wave back and forth in sympathy, *digital audio* is composed of **samples** of that waveform, arranged in sequence. 

Most digital audio is done at 44,000 (aka 44kHz) samples per second, which means that if we have one second of sound, it gets divided it up into 44,000 slices, and for each slice there is a number, indicating the amplitude of the signal. Put all those samples end to end, and you get a digital replica of the original waveform. It's not perfect, though, because it's a series of discrete steps instead of a continuous, smooth waveform; but for almost everyone, 44,000 samples per second is fine-grained enough that you can't tell the difference between the original sound and the digital recording of it. Remember, the highest sounds we can hear are about 20 kHz, so sampling at more than twice that rate does the trick.

44kHz is an industry standard; not the only one, but the usual one. There is another standard called "bit depth," which is the range of possibilities for measuring the amplitude. When people talk about "8-bit audio" from old video games, it's because the amplitude was measured with 8 bits, or the numbers 0-255 (remember the 8-bit ASCII standard from the Production lecture?). The more common audio standard today is 16-bit audio, which is a range of 0–65535. The amplitude of any one sample is a number between 0 and 65 thousand. 

Those standards: 44kHz, 16-bits, cover pretty much everything you hear on your phone, computer, etc. When audio CDs came out in the 90s, this was the standard, and it's mostly stuck around. You'll see when we start recording that higher quality is possible: often audio is recorded at 48kHz, 24 or 32 bits. Put these side by side and you won't be able to hear the difference; the higher quality does give you higher resolution for signal processing and post-production. It also makes for bigger files of course.[^sound]

Oh, we should also note that we have **two ears**. So we do everything *twice*. That's called "stereo" as opposed to "mono," which no one cares about anymore except for collectors who want the original Beatles recordings from the mid-1960s. To be honest, lots of podcasts are also mono, because there's just a single voice.

So, 44 or 48kHz; 16- or 24-bit; mono or stereo -- that's digital audio. We can put those sequences of samples in a **file**. 

A very simple and common file format is **.wav** -- which is pretty much just a sequence of numbers that corresponds to these samples. More common formats like .aac or .mp3 are **compressed** (that is, mathematically squished) to make the files smaller and faster to send over the internet.

Digital audio is pretty easy to edit and manipulate on a computer (or your phone). A typical editor (the fancy term is "Digital Audio Workstation" or DAW) like Audacity or Hindenberg or GarageBand allows you to both *hear* the audio and *see* the waveform as a graphic. You can then use familiar things like *cut*, *copy*, and *paste* to chop it up, move it around, and so on. A good DAW will also have lots of **signal processing** tools, too, that you can use to manipulate the audio: making it louder, softer, cleaner, dirtier, etc. 

Most signal processing effects have their roots in pre-digital recording studios, because it became clear by about the 1950s that you could use studio effects to make recordings sound like -- well, like something else -- and that's the world we've lived in ever since.

### On Pyschoacoustics

This little potted introduction to digital audio makes it all sound pretty simple. The complex -- and somewhat magical -- part is what happens between our ears (with their tiny hairs swaying to the sound) and our brains. Ears have evolved for millions of years -- apparently they began as fish gills -- to provide a sense of what's going on around us. Humans often think of vision as the primary sense, but ears are older, and fundamental in a different way, which we will explore a bit in this class.

The easiest example of psychoacoustics is stereo hearing. We have two ears, positioned about 20cm apart. Remember that wavelength and frequency are related; anything above about 1500Hz (e.g. bird song) has a **wavelength** of less than the distance between your ears. So your hearing is **directional** for lots of sounds. In fact, for most naturally occurring sounds, there's a big mix of frequencies involved anyway, so if we have two ears separated by our head, we hear almost everything directionally. An exception to this is the bass at the dance club, which is closer to a pure low-frequency sound. You don't discern it coming from a particular direction; it just permeates everything (and makes you wanna dance).

So here's a thing to try: Make a short recording (of anything, really), and open it up in your DAW. Copy the recording so that you have two tracks, in parallel, and make sure they start and end at the exact same point. Using the DAW, **pan** the first track hard to the left, and the second track hard to the right. Now listen to it, using earbuds or headphones. It should sound like there is only one sound, right in the middle. Because the two tracks are identical, your brain can't hear them as distinct.

But if we delay the start of one or the other of the tracks (some DAWs make this really easy to do) by just a *tiny* amount -- 5 miliseconds (5ms) or so, you will start to hear the sound on one side more than the other. If you continue to increase the delay, you will start (around 20ms) to be able to discern two distinct sounds, one on the left and the other on the right. What we're doing in this exercise is fooling our brain into thinking that the source of the sound is coming from one side because of how the sound reaches one ear before the other. If the difference gets great enough, then your brain recognizes it as two distinct sounds, or perhaps a sound with an echo.

This version of stereo hearing is only one of about a bazillion different psychoacoustic effects that recording engineers have identified. Because how we hear is so dependent on context and environment, it is also possible to create effects where sounds are closer or further away -- even above us or below us -- by playing with the relationship between the original pure sound and its reflections off surrounding surfaces (walls, floors, ceilings). **Reverb** is an effect that creates a set of artificial reflections to a sound, which gives the distinct impression of distance, and also of the apparent size of the room you're in. 

This works because of the way our hearing has evolved over millions of years, and also how your hearing has been learned over the years that you've been hearing things.

## Practical production tactics

There's a *lot* more to psychoacoustics than this, but we have enough to do some practical things with our audiobooks.

Hannah McGregor likes to say that podcasting works because it's intimate; it's someone talking to you *right inside your ear.* Partly this is true because you probably have earbuds literally in your ears. But it's also true because of some production details that Hannah -- and most other podcasters -- use.

"Close miking" means, simply, putting the microphone really close to the sound source. The effect of this is that the sound the microphone picks up is almost all the original source, and very little reflections from the room around. Compare this with putting a microphone two metres away -- in which case the microphone will pick up your voice, but also lots of **ambient** room sound, including reflections of your voice off walls and other surfaces. Your ears can easily tell the difference.

It's really common to record a single voice -- a podcaster, an audiobook narrator, a radio station DJ -- very close, to produce that intimacy. Close miking also, for some straightforward physics reasons, helps emphasize the bass frequencies in your voice, resulting in a "warmth" that you don't get if the microphone is farther away. 

On the other hand, it's common to record choirs, music ensembles, and so on with microphones placed farther away. It's not just because it's easier; choral music developed over hundreds of years, often in big stone churches -- the sound of the room itself is part of the sound of the music.

And, in fact, different kinds of microphones are suited to different kinds of recording strategies. The handheld mics we are using -- the famous Shure SM58s (the Aretha Franklin/Hannah McGregor microphone) -- are a kind of **dynamic microphone** which is powered only by the force of your voice vibrating against a membrane, which creates an electrical signal. They are also pretty strongly directional, picking up sound coming straight at it, and less from the sides. Dynamic microphones are perfect for close miking; the old advice "eat the mic" (don't actually do this, please) speaks to this... you get the best recording if you're very close.

Other kinds of microphones -- like the **condenser microphones** on the top of the Zoom recorders -- are designed for more distance, to pick up fainter sounds, and can be more "omnidirectional." They have an electric current running through them which makes the thing much more sensitive, and therefore better at capturing ambient sounds, or sounds from more diffuse sources. Different gear for different uses.

### Studios and ambient noise

Your brain is an amazing instrument. Your ears are constantly picking up every conceivable thing vibrating in the space around you, but your brain is able to single out the *one* thing you actually want to pay attention to -- like that couple at the table next to you in the busy cafe that might be having a very discreet argument about something interesting! Your brain does this so well that most of the time, you *only* hear what you are attending to, and the rest gets filtered out entirely, as if it's not even there.

When you start recording, though, you'll find that the microphone picks up *everything* indiscriminately. When you listen to the playback, you'll often be astounded -- and frustrated -- by how much ambient noise there is in your recording.

It would be nice to think that simply applying a "noise gate" filter in your DAW would solve the problem, but that's a very blunt instrument -- and it also has an effect on the sound you're trying to record as well as what you're trying to get rid of. So in practice there is no substitute for recording in a genuinely **quiet** room. 

Furthermore, you will also want to try to keep your **recording level** as high as possible (without going over the limit, of course), so you're taking advantage of all of those 65,553 possible amplitude values. Ideally, you have a strong recording level for what you want to capture, and everything else -- including the ambient "noise floor" of the room -- is as low as possible. The buzzword is "signal to noise ratio."

The first job of a recording studio is to provide a recording environment with a very low "noise floor" so that you're not fighting it. But we don't always have access to a proper, silent studio. We can, however, use our ears and our brains to improve our prospects.

First off: just forget classrooms at SFU. There is a *huge* amount of white noise in these rooms -- air conditioning, computer fans, projector fans, and so on -- that we ignore most of the time but which will be terrible if we try recording here. Your bedroom at home might be a better choice -- as long as there isn't a lot of traffic noise, or cats complaining. You can use your ears -- and you can make test recordings with the Zoom recorders, to find a place where the ambient noise is lowest.

Another thing that you should think about is the kind of surfaces in the room. Classrooms are made up of a lot of blank walls, flat ceilings, and flat tables. Flat surfaces help sound waves bounce around a lot. Soft, irregular surfaces absorb sound more than reflect it -- professional recording studios often have all sorts of interesting coverings on walls and ceilings, as well as carpets on the floors. At home, blankets, rugs, bedspreads all help. More than one MPub podcast has been recorded while sitting in a clothes closet for this exact reason.

If what we're after is the intimate "close miking" sound, we can also reduce the size of the room. One way to achieve this is to sit in your closet, but another way is to make a small room out of a box: line a cardboard box with a blanket, and place the microphone so that you're speaking into the box; that reduces reflections and ambient sounds. 

Putting something soft *behind* you also helps reduce reflections, since sounds waves go every direction. You can take this to extremes, of course. If you do find yourself spending hours redecorating your apartment for optimum recording conditions, consider another masters degree -- in audio engineering!

Next we'll look at [Digital Audio Workstations](DAW.md) and recording gear.


[^sound]: The Wikipedia page for "Sound" is actually a great primer!
