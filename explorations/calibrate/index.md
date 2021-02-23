---
title:  "Calibrate CSS"
order: 100
modules:
    - "explorations/calibrate/js/main.js"
styles:
    - "explorations/techniques/main.css"
    - "explorations/calibrate/style.css"
calibrated: calibrated
---

*This is a draft.*

# Calibrate CSS

<p>This article is inspired by a
<a href ="https://github.com/w3c/csswg-drafts/issues/614">comment by
@frivoal on w3c/csswg-drafts#614</a>, a discussion on the Topic
"<strong>[css-values] Ability to address actual physical size #614 </strong>":
</p>

<blockquote>
    <p>[…]</p>
    <p>It is possible that most members of the CSSWG and most browser
    engineers are wrong, that there's a big flaw in the collective
    reasoning, and that one way or another, this is actually a good
    idea. If you think so, start by understanding the arguments against,
    then build a strong case debunking them, and explain why you're right.</p>
    <p>Merely stating that there's no downside isn't going to be convincing.</p>
</blockquote>

<h3>Disclosure</h3>
<p>As of beginning this, I don't know if a good case can be build, but
I'm instinctively biased towards having the ability to use real world
physical sizes in CSS.</p>

<h3>Contribute</h3>
<p>I understand this as an open document, meaning that contributions
are welcome via the <a href="https://github.com/graphicore/varla-vafo/issues">GitHub
issue tracker</a> and <a href="https://github.com/graphicore/varla-vafo/blob/main/explorations/calibrate/index.html">Pull
Requests on the actual document</a>. But this openness also means it's
possible, even likely, that the article changes over time. The change
history can be examined via git, but when quoting, it may still be a
good idea to keep the current git commit hash of the source document.
<!-- TODO: include commit hash and link in an automated build step --></p>

<h2>Calibration of Browser Length-Units</h2>

<p>In an <a href="https://github.com/w3c/csswg-drafts/issues/614#issuecomment-611217635">#614
issue comment</a> @tabatkins describes a calibration page:</p>

<blockquote>
<p>Notably, this would basically be:</p>
<ol>
    <li>Have a calibration page, where you ask the user to measure
    the distance between two lines that are some CSS distance apart
    (say, <code>10cm</code>), and input the value they get.</li>
    <li>Use this to find the scaling factor necessary for that screen
    (CSS length divided by user-provided length), and store it locally
    (via localStorage, or a cookie, etc).</li>
    <li>On the pages where you need the accurate length, fetch it from
    local storage, and set a <code>--unit-scale: 1.07;</code> (subbing
    in the real value) property on the <code>html</code> element.</li>
    <li>Anywhere you use a length that needs to be accurate, instead of
    <code>width: 5cm;</code>, write
    <code>width: calc(5cm * var(--unit-scale, 1));</code>.</li>
</ol>
<p>This is a robust and minimal calibration scheme that will
"fail open" - if the user hasn't calibrated, or clears local data, or
has JS turned off, it'll just use standard CSS units (due to the , 1
default arg for the unit scale), rather than breaking.</p>
</blockquote>

<p>I build that calibration device as a widget into this page:<br>
    <button class="ui-init-calibrate">click this button to calibrate</button>.
</p>
<p>Note: no persistence/local storage of the calibration yet.</p>
<p>The result is stored in CSS on <code>:root</code> as <code>--unit-scale-adjust</code>.</p>


<p>CAVEAT: the example works only for square pixels. It's generally
possible to calibrate width and height separately.</p>

<p>
    One real centimeter: <span style="display: inline-block; width: 1cm; height: 1cm; background: black"></span>
    One real inch: <span style="display: inline-block; width: 1in; height: 1in; background: black"></span>
</p>

<blockquote>
The reference pixel is the visual angle of one pixel on a device with
a pixel density of 96dpi and a distance from the reader of an arm’s
length. For a nominal arm’s length of 28 inches [71,12 centimeters], the visual angle
is therefore about 0.0213 degrees. For reading at arm’s length,
1px thus corresponds to about 0.26 mm (1/96 inch).
</blockquote>

Therefore, on your device the reading distance to have one
CSS-inch to appear at an visual angle of 0.0213 degrees is: <span class="insert insert-normal-reading-distance"></span>

<p><em>Note to me</em>
The behavior of the "auto" algorithm of
<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust"><code>text-size-adjust</code></a>
is a case where we need a good automation in <code>font-optical-sizing</code>
to automatically adjust, <code>font-variation-settings</code> won't do it in that case.

</p>

### more use cases:

* print proofing/designer preview. We can help reducing paper
  wastage!
* Effective web proofing by correctly scaling to actual
  e.g. phone-screen sizes.
* optical size proofing for type design
* getting an impression what the default viewing distance is
  supposed to be on certain devices, as it is not easy to to
  do on the spot.

* touch device UI must be touched with physical fingers,
  hence controls designed with physical sizes are best practice.
* the web platform usage diversifies as it is becoming more ubiquitous.
* the web platform is becoming more ubiquitous, not all use cases
  fit well into the "reference pixel" approach. Sometimes
  target screen and viewing distance could be very well known
  and hence a direct way of designing for these target could be
  desirable. In web, the flexibility of the CSS-unit approach
  requires that there's a scroll somewhere. Paged media can't
  afford this. Where a user can't scroll, e.g. a digital poster
  on a screen, that is not interactive, pages become important
  and alse that the designer can control the viewing distance
  assumptions. <!-- Clames like this need backup! it's also just
  not a good argument yet and may have false statements, definitely
  not all strong points.
  -->
* We can control for different device sizes even when designing
  with real world units, though a support in media-queries would
  help a lot.
* hi-res screens are so good now, we can anchor to physical units
  and won't get blurry lines.
* what about e.g. font-sizes for legal print, are there absolute
  requirements? "legible" is one of them, but fonts becoming regularly
  smaller than e.g. 12 pt because the device defaults to 20 inches
  viewing distance instead of 28 inches may be unfortunate.