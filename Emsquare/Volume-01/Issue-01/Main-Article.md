---
title: "Space the initial frontier"
modules:
    - "Emsquare/Volume-01/js/main.mjs"
styles:
    - "explorations/wikipedia/css/varla-varfo.css"
    - "explorations/wikipedia/css/widgets.css"
    - "Emsquare/Volume-01/main.css"
---

The largest key on the keyboard is the space key. Typography starts with its parent space, the “imaginary” em square, into rectangles of the same height as the em square representing the default widths of each glyph in a font, including the space. These rectangles are only "defaults", as the space between lines,  between glyphs, and the word space, can be changed by the user, and then by the final display of font in print or screen.

## Square one.

This is a rectangle of equal sides and angles, making it a square.

{% include emsquare-figure
        src="./images/Figure 1.png"
        fig=1
        caption="The em square."
%}

In type, this square represents to the type designer two things that are important links to the reader. Vertically, the space represents the intersection between lines of text when the font is composed without additional space between lines.

{% include emsquare-figure
        src="./images/Figure 2.png"
        fig=2
        caption="The vertical dimensions of a font’s main glyph groups."
%}

Second, chosing where the baseline is in the em square, is how the font line up with every other font of any size or style. This gives the type designer  the extents that can be allotted above and below the baseline, for the typeface family.

And so the type designer plans the vertical metrics and horizonatal of all the characters of a typeface, based on how the designer wants collections of glyphs to be glimpsed, seen, viewed, skimmed, read, or read for a long time.

{% include emsquare-figure
        src="./images/Figure 3.png"
        fig=3
        caption="Length of text / various ways to \"see\" it."
        alt="Length of text / various ways to 'see' it."
%}

Horizontally, the height is the same as the em in each glyph and except when the script and design are monospaced, each glyph has an appropriate width. In such fonts, the horizontal dimension represents the default spacing of as the glyphs space best with all the other characters in the font.

{% include emsquare-figure
        src="./images/Figure 4.png"
        fig=4
        caption="Glyphs of different widths. Monospaced all one width."
%}

(So far, this is true of all scripts, and all designs)


Add direction of reading, at the behest of whichever direction, or directions, a language allows, and the square has direction. For example, and to zero in on one language at a time, all the types of Latin are designed for all the languages that use Latin, to be read in lines from top to bottom, with each line being read from left to right. So the square has a beginning on the top and left sides, and has ends at the bottom and the right side.

{% include emsquare-figure
        src="./images/Figure 5.png"
        fig=5
        caption="Beginnings and ends of transparencies."
%}

The em square (called an em quad in metal type), can be seen typographically as a space with beginnings and ends, and nothing in the midst of that, at the size of the type with no additional spacing around it. The other spaces affecting the appearance of our square between the lines, is line spacing, and/or between the letters is letter spacing. Besides reading following from the beginning to end of each glyph, when programs responding to type specifications are told to add line spacing or letterspacing, they do so to the end, i.e. the bottom and right sides of glyphs. 

{% assign figures6 = "" | split: "" %}
{% assign figure6a = "./images/Figure 6.png,6,Em square w/w-out additional line spacing." | split: "," %}
{% assign figure6b = "./images/Figure 6b.png,6b,Default letters w/w-out letter spacing." | split: "," %}
{% assign figures6 = figures6 | push: figure6a %}
{% assign figures6 = figures6 | push: figure6b %}

{% include emsquare-multi-figure
        figures=figures6
        caption="Em square w/w-out additional line spacing and<br />**Figure 6b**: Default letters w/w-out letter spacing."
%}

## Line Space
Between the lines is called line spacing, in CSS, and is valued either by the size of the space or as a percentage of the size of the type. Between the letters are default letter spacing and kerning, with tracking being a function for changes to both, also usually expressed as a percentage of size. Letterspacing is obviously added at the end of each letter, and line spacing was traditionally, and today in most design applications, added to the bottom of each line. This was done to facilitate cooperative use of the em square and leading, between users and font developers in the use of languages with and without diacritic accents above the uppercase.

Since time immemorial, many type designers have striven to keep all decending glyphs, diacritics and attachment, at or near the bottom of the em, all uppercase heights at or near the top, and all diacritics above the upper and lowercases, within the em, plus 20% of the em. This defacto standard allows the user to align the type on the uppercase at the top of their text container, and either the baseline for all-cap use, or the bottom of the em for mixed case use, allowing any diacritics in the first line to "float" above the rest, with interline diacritics clear of the descenders in the line above.

Perhaps with a broader world view, CSS splits additional line spacing to place half above the em, and half below. this has the effect of starting the first line slightly lower than in traditional typography, but otherwise, on fonts made the traditional way, the behavior is the same from there to the bottom line, which of course, is slightly lower than in traditional type. 

Line spacing at 120% of the size was a de facto standard for print, based on an “ideal” line length of somewhere between 60 and 75 characters, for long, sometimes called immersive reading. The size of type considered in that standard was between 9 and 11 points, with exceptions for smaller books, (going down to 8pt), and for younger readers, (going up to 12pt).

More will come on type sizes, including the vague nature of them in CSS, but the line spacing of text in immersive reading of 65-character, 9-11 pt type with 120% line spacing “standard”, comes along with gradually decreasing line spacing % as the column shrinks in width. In addition to length of text and column width playing roles in line spacing, prerequisite to this kind of reading is a style selection of a normal or regular weight and width, from a typeface family likely to be familiar to the reader.

Leaving the effects of styles beyond a regular weight and width until later, here we’ll dwell on column length, size and case, as in Latin composition, all caps and mixed case usually occupy different vertical metrics. At the default of 65 characters you read here, if I smash a line’s Collin width down to the width of the widest word in the line, regardless of what size it is, I don’t need extra line spacing, 100% is fine. All caps in narrow columns can be linespaced at 90-80% in English use and almost to 75% in some cases of narrow columns at large sizes.

As size ranges up, it is almost certainly the result of the length of text getting shorter, leaving the range of immersive reading and entering the realm of a shorter attention span from the reader. So between the poles of 1 character per column and 65, and a size range from 9 to 144, line spacing for mixed case ranges from 100-120% of size, with collision avoidance of descenders and ascenders being a limiting factor. All caps line spacing usually ranges from 80-95%, with presence of uppercase descenders, like “Q” or J providing a possible limitation. 

## Word Space

The most important character to reading in a font is the space glyph, or word space. In Latin use, its width is derived from a formula, based on the width of one of the letters, or simply chosen visually by the type designer. It is often adjusted by applications, but its fundamental task is to make certain it’s the largest horizontal space in text. Readers can't be confused by the spaces between letters, between letters and punctuation or between punctuation and punctuation, and the word space. While this sounds obvious, it rarely is an issue with Latin type because so much work in the development of typefaces used by the public goes into elimintating any space that can compete, visually, with the word space. 

{% include emsquare-figure
        src="./images/Figure 7 & 8 one third.png"
        fig=7
        caption="Word space and its adjustment."
%}

The word space's second most critical appearance is to remain around or be smaller than the line space, i.e. the space between lines. Obviously the word space is less important and sometimes absent entirely from type that’s glimpsed, seen, or quickly viewed, and is increasingly important as the text is to be skimmed, read, or read for a long time. In the most complex case, justification of narrow columns, the word space's range of widths needs to be kept narrow relative linespacing, which for narrow columns can be quite small.

The type designer’s task, then, is to create a default word space and letter spacing, that work over a rnage of sizes, column widths, with hyphenation and justification a distinct possibilty. Included in that, beyond the default letterspacing, is the type designer's task of making kerning pairs, in essence a list of exceptions to the default letter spacing that need to be prevented from being too far apart, like /T/o, thus competing with the size of the word space.



{% assign figures8 = "" | split: "" %}
{% assign figure8a = "./images/Figure 7 & 8 two thirds.png,7 & 8,Default letter spacing and Kerning vs word space." | split: "," %}
{% assign figure8b = "./images/Figure 7 & 8.png,7 & 8,Default letter spacing and Kerning vs word space." | split: "," %}
{% assign figures8 = figures8 | push: figure8a %}
{% assign figures8 = figures8 | push: figure8b %}

{% include emsquare-multi-figure
        figures=figures8
        caption="Default letter spacing and Kerning vs word space."
%}

There’s only one other kind of space left in type and it’s inside the letters. This may be fully enclosed, like /o’s interior, trapped along the baseline and cap height, like /K, or swirling amidst the stem of the /S, but it’s what gives a typeface the start on all the other spaces we’ve covered.

{% include emsquare-figure
        src="./images/Figure 9.png"
        fig=9
        caption="Counters."
%}

The user has three kinds of control over this space. Type size, applied to a single style of type, makes them grow and shrink linearly to the change of size. Changing to the use of different styles within a regular font family alters the internal white spaces according to the style change from one to the next. Variation font technology, which can provide both of the above, can also provide optical sizes that adjust the internal white spaces over a range of sizes, as well as adding fluid ranges of weight and width axes.

{% include emsquare-figure
        src="./images/Figure10.png"
        fig=10
        caption="Counter changes via size, style and opsz."
%}

And while typefaces overwhelmingly end with well defined spaces, between words, letters and exceptional pairs, and many typeface families include a blizzard of styles, each with unique spacing, the way the font format, composition software, like design applications and web browsers, Latin typography faces challenges to the type user. And where there is a challenge in Latin, there’s likely to be more elsewhere in the world of scripts.

## Takeaways:

* ???
