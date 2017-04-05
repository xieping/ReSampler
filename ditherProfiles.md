## Summary of Dithering / Noise - Shaping Profiles used in ReSampler

Generally, the noise shaping becomes more intense (has higher amplitude) as the Dither Profile ID increases,
with the ID of 0 corresponding to *flat* (no noise shaping; which is also equivalent to using the **--flat-tpdf** switch).

As the dither profile ID increases, the noise shapes are designed to have progressively less *perceived noise* (despite actually having *more* noise added to the output). 

The noise source for all dither profiles is TPDF noise (Triangular Probability Density Function).

*Note: At normal listening levels, the effects of dithering are very subtle with 16-bit audio.* 

<table>
    <thead>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Description</th>
            <th>Comments</th>
        </tr>
    </thead>
    <tbody>
        <tr><td>0</td><td>flat tpdf</td><td>no noise shaping</td><td>no error correction feedback</td></tr>
        <tr><td>1</td><td>classic</td><td>subtle noise shaping (HF emphasis)</td><td>original noise shaping from older versions of ReSampler</td></tr>
        <tr><td>2</td><td>flat tpdf (with error-correction feedback)</td><td>gentle highpass response</td><td>error correction feedback loop results in first-order (6dB/oct) slope</td></tr>
        <tr><td>3</td><td>Modified E-Weighted</td><td>notch in 3-4kHz range (which our ears are sensitive to)</td><td>from the paper "Minimally Audible Noise Shaping"</td></tr>
        <tr><td>4</td><td>Wannamaker 3-tap</td><td>simple f-weighted curve, with notch around 4kHz</td><td>from the paper "Psychoacoustically Optimal Noise Shaping"</td></tr>
        <tr><td>5</td><td>Lipshitz</td><td>e-weighted curve with notches around 4k and 12k</td><td>from the paper "Minimally Audible Noise Shaping"</td></tr>
        <tr><td><b>6</b></td><td><b>standard</b></td><td><b>Smooth curve with notches at 3150 and 11250Hz, and extreme HF emphasis</b></td><td><b>default noise shape. Good balance between low audibility and low amplitude (Works well for most material)</b></td></tr>
        <tr><td>7</td><td>Wannamaker 24-tap</td><td>notches around 3.5kHz and 12kHz</td><td>from the paper "Psychoacoustically Optimal Noise Shaping"</td></tr>
        <tr><td>8</td><td>Wannamaker 9-tap</td><td>notches around 3.5kHz and 12kHz</td><td>from the paper "Psychoacoustically Optimal Noise Shaping"</td></tr>
        <tr><td>9</td><td>High28</td><td>notches at 3150Hz and 11.25kHz with 28dB high shelf</td><td></td></tr>
        <tr><td>10</td><td>Improved E-Weighted</td><td>widely used in many DAWs and audio software</td><td>from the paper "Minimally Audible Noise Shaping"</td></tr>
        <tr><td>11</td><td>High30</td><td>notches at 3150Hz and 11.25kHz with 30dB high shelf</td><td>sounds great to older listeners, but high-frequencies may annoy younger listeners. Nevertheless, at the intended playback volume, the high-frequency components will still be very quiet relative to the program material</td></tr>
        <tr><td>12</td><td>High32</td><td>notches at 3150Hz and 11.25kHz with 32dB high shelf</td><td>sounds great to older listeners, but high-frequencies may annoy younger listeners. Nevertheless, at the intended playback volume, the high-frequency components will still be very quiet relative to the program material</td></tr>
    </tbody>
</table>

### References

[[1] Lipshitz, Stanley P. and Vanderkooy, John and Wannamaker, Robert A. “Minimally Audible Noise Shaping" J. Audio Eng. Soc., vol. 39(11), pp. 836-852 (1991.).](http://www.aes.org/e-lib/browse.cfm?elib=5956)

[[2] Wannamaker, Robert A. "Psychoacoustically Optimal Noise Shaping" J. Audio Eng. Soc., vol. 40(7/8), pp. 611-620 (1992.).](http://www.aes.org/e-lib/browse.cfm?elib=7039)