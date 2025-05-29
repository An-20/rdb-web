## Numbers
Types of number:
- The **integers**, $\mathbb{Z}$, are whole numbers.
- The **natural numbers**, $\mathbb{N}$, are counting numbers (nonnegative integers). In maths, these are $1, 2, 3\dots$. In computer science, these are $0, 1, 2\dots$.
- The **rational numbers**, $\mathbb{Q}$, are numbers that can be represented as a fraction $\frac{p}{q}$, where $p$ and $q$ are integers.
- The **irrational** numbers are numbers that cannot be represented as a fraction $\frac{p}{q}$, where $p$ and $q$ are integers. This includes numbers such as $\sqrt{2}$ and $\pi$.
- The **real numbers**, $\mathbb{R}$, lie upon the real line and represent 1-dimensional quantities or real-world measurements. They include both rational and irrational numbers.
- **Ordinal** numbers indicate the position of an element in a sequence (1st, 2nd, etc.).
### Bases
###### Binary
**Binary** is base 2. There are two digits: 0 and 1. One binary digit is a bit, and eight digits are a byte. $n$ bits can represent $2^n$ different values. 

To convert a number from decimal to binary. repeatedly write down the remainder when divided by two, then integer divide by two. The first number corresponds to the least significant bit.

**Unsigned** binary numbers are represented with normal place values:
$$
1010_2 = (1\times2^3 + 0\times2^2 + 1\times2^1 + 0\times2^0)_{10}
$$
Unsigned binary numbers with a fractional part can be represented in fixed point binary by having place values of $2^{-n}$, e.g. $\frac{1}{2}, \frac{1}{4}, \frac{1}{8}\dots$.

**Signed** binary numbers are typically represented with **two's complement**, where the leftmost place value has a negative value. This means an $n$ bit two's complement number can represent $-2^{n-1}$ to $2^{n-1}-1$ inclusive.

To convert a positive number to it's two's complement negative equivalent, invert every bit to the left of the least significant 1. 

###### Hexadecimal
**Hexadecimal** is base 16, where decimal numbers 10-15 are represented by digits A-F. Each hex digit corresponds to 4 binary digits, which makes hex easier to remember or type for humans.

#### Units
- Kibibyte (KiB) - $2^{10}$ bytes
- Mebibyte (MiB) - $2^{20}$ bytes
- Gibibyte (GiB) - $2^{30}$ bytes
- Tebibyte (TiB) - $2^{40}$ bytes
- Kilobyte (kB) - $10^3$ bytes
- Megabyte (MB) - $10^6$ bytes
- Gigabyte (GB) - $10^9$ bytes
- Terabyte (TB) - $10^{12}$ bytes

## Character encodings
#### ASCII
**ASCII** (American Standard Code for information Interchange) uses 7 bits to represent all the characters on a standard English-language keyboard, including all uppercase and lowercase Latin characters, numbers, and some symbols. The first 32 codes are non-printable control characters. 

Numbers in ASCII are not represented as their actual binary number value - the digit '3' is represented by a binary character code equivalent to 51 in decimal.
#### Unicode
**Unicode** was created to allow more alphabets for different languages to be represented, including Greek, Arabic, and Cyrillic. UTF-16 and UTF-32 use 16 and 32 bits respectively per character[^1]. UTF-8 is variable width, using between 8 and 32 bits per character. It is the most commonly used Unicode encoding.

## Error checking and correction
#### Parity bits
A **parity bit** uses an additional bit that is set at transmission and later compared to identify if there were errors in transmission. Under **odd parity**, the parity bit is set so the total number of 1s per byte is odd. Similarly, under **even parity**, the parity bit is set so the total number of 1s per byte is even.
#### Majority voting
In **majority voting**, each bit is sent a minimum of three times. If a bit is flipped, the recipient assumes that the most commonly received bit is correct.
##### Checksums
A **checksum** is a number that is calculated using an algorithm, and transmitted along with a block of data. The recipient then re-calculates the checksum based on what they receive, and compares against the received checksum. If they do not match, an error has occurred.
#### Check digits
**Check digits** are a digit at the end of a string of numbers, and are typically used to check for errors with human inputted data e.g. ISBN numbers. They can be calculated by applying multiplicative weights, adding, and moduloing.

## Digital and analogue
An **ADC (analogue to digital converter)** is used with analogue sensors to convert measurements into discrete binary signals.

A **DAC (digital to analogue converter)** converts a digital signal to an analogue output. They are commonly used to covert a digital analogue signal into an analogue signal.

## Images
#### Bitmap
A **bitmap** image is represented by an array of pixels, which are each represented by a binary value that represents the colour of that pixel.

Properties of bitmap image files include:
- **Image size** is the width and height of the image in pixels.
- **Resolution** is the number of pixels per inch (ppi), which corresponds to the density of the pixels.
- **Colour depth** is the number of bits used to represent each pixel.
- The size of a bitmap image file is given by:$$\text{size of bitmap image file (bits)} = \text{height} \times \text{width} \times \text{colour depth (bits)}$$
**Metadata** is data about data. Image files often contain metadata. This can include the height and width in pixels, and colour depth.

#### Vector
**Vector** images are represented by a list of geometric objects. Properties of each object are stored, such as position, size, fill colour, line colour, and line weight. Vector images can have smaller file sizes, but are only suitable for graphics such as logos, not real-life photographs. Individual objects can be easily edited in vector graphics.

## Sound
Sound is represented digitally by a series of discrete **samples**, with discrete binary value amplitudes. A analogue to digital converter converts an analogue microphone signal to a binary signal, which is **sampled** at regular intervals, and each sample is **quantised** to a discrete binary value and stored.

Properties of sound files include:
- **Sample rate** (in Hz) is the number of samples per second.
- **Sample resolution** is the number of bits used to represent each sample.
- The size of a sound file is given by:
$$\text{size of sound file (bits)} = \text{length (s)} \times \text{sample rate (Hz)} \times \text{sample resolution (bits)}$$

**Nyquist's Theorem** states that in order to produce an accurate recording, the sampling rate must be at least double the highest frequency.

#### MIDI
**MIDI** is a protocol for electronic musical instruments and computers to communicate. A MIDI controller carries **event messages** that specify notes and contain details such as the pitch, duration, timbre, voice, and velocity of a note. A MIDI file contains a list of MIDI event messages which are used to synthesise the sound. Individual notes can be easily individually manipulated, and it is easy to perform manipulations such as playing in a different key.

## Compression
**Compression** reduces the size (in bytes) of a file. This reduces the storage space needed, reduces bandwidth used when transmitting a file, and reduces file transfer times.
#### Lossy compression
**Lossy compression** works by removing non-essential information. Some information is permanently lost. For example, MP3 files use lossy compression that remove sounds too high to hear, and quieter sounds that are played at the same time as louder sounds.
#### Lossless compression
Lossless compression works by recording patterns in data rather than the actual data. All the original information can be exactly recovered. Lossless compression is suitable for text, but results in much larger file sizes than lossy compression for things such as images.

**Run length encoding** involves storing the length and value of 'runs' of the same consecutive value.

**Dictionary-based methods** store a dictionary and a series of keys. Each key corresponds to a value in the dictionary, which can then be used to reassemble the original message.

## Encryption
**Encryption** is the transformation of data from a one form (the **plaintext**) to another (the **ciphertext**) such that an unauthorised third party can't understand it. The encryption algorithm is the **cipher**, which requires a secret **key** to decrypt the message.
#### Caesar Cipher
The **Caesar Cipher** is a substitution cipher where each letter of the alphabet is shifted by a given number of letters (the key). The Caesar Cipher is insecure as there are only 25 possible keys, making it easy to brute-force. Additionally, each character always maps to a specific output character, making cryptoanalysis techniques such as frequency analysis possible.
#### Vernam Cipher
The **Vernam Cipher** requires a one-time pad equal in or longer than the message being sent. The **one-time pad** must be **truly random** and only ever used once. Each plaintext character is XORed with the one-time pad character. The random key means the distribution of characters is also random, making the Vernam Cipher immune to cryptoanalysis.

While the Vernam Cipher is theoretically unbreakable, Other ciphers are **computationally secure**. In theory, with enough ciphertext and time, every other cryptographic algorithm can be broken.


[^1]: **Footnote on UTF-16**
	UTF-16 is actually a variable-width encoding that uses 8 or 16 bits per character.