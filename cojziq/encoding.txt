# Unicode

We use the private use area, and encode it as if it were written in the
latinization.  The fonts make heavy use of ligatures to combine these into
individual glyphs.  This design is for use on standard systems and allows one
to type with just a special keyboard layout and the appropriate font instead of
a complicated input method and other custom software.

|      |`___0`|`___1`|`___2`|`___3`|`___4`|`___5`|`___6`|`___7`|`___8`|`___9`|`___A`|`___B`|`___C`|`___D`|`___E`|`___F`|
|---:  |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
|`e00_`| p    | b    | f    | v    | þ    | ð    | s    | z    | t    | d    | c    | ʒ    | k    | g    | x    | q    |
|`e01_`| m    | n    | ṇ    | ŋ    |      |      |      |      | '    | -    | ,    | · \* | .    | (    | )    |  ?   |
|`e02_`| y    | i    | a    | u    | e    | o    |      |      | h    | w    | l    | r    | j    |      |      |      |
|`e03_`| 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | ¤ \* |      |      |      |      |      |

The code points with an asterisk need additional explanation because they
represent orthographic concepts unique to Cojziq:
<table>
 <thead>
  <tr>
   <th></th>
   <th>Name</th>
   <th>Purpose</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td align="center">·</td>
   <td>Proper marker</td>
   <td>
    This marker appears as a small dot right above the leaf-flower boundary
    and marks words that are proper names or borrows from other languages, or
    abbreviations.  It is comparable to capitalization in English.
   </td>
  </tr>
  <tr>
   <td align="center">¤</td>
   <td>Tejvyn cultural symbol</td>
   <td>
    This is a stand alone sigil that is often used as a symbol for Tejvyn, and
    all that's associated with it including Cojziq.
   </td>
  </tr>
 </tbody>
</table>

It's also important to acknowledge the existance of U+200C, the zero-width
non-joiner (ZWNJ).  When writing languages other than Tejvyn, it is occasionally
necessary to prevent vowels and the consonants following them from joining.
This typically occurs at morpheme boundaries.  For example, the English word
"rails" would be written "ral_z", where '_' represents the ZWNJ.

# 16-bit Cojzig glyph encoding (CZQ-GE16)

This gives each combined glyph it's own, unique bit pattern, but is incompatible
with all of unicode.  It is split into blocks with the upper most four bits
representing the block.  Usefully, the `0x0___` block is equivalent to unicode.
Cojziq is in the `0xA___` block.
