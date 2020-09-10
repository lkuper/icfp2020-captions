# icfp2020-captions

The master copy of each file is the `.ass` file. *Do not edit the .srt file* as your edits will get overwritten.

## Instructions for ICFP/JFP authors

As you might know, this year ICFP had closed captioning for all of the talks in the main program, provided by a professional captioning vendor. We (the ICFP accessibility co-chairs) carefully reviewed and corrected errors in the captions before they appeared at ICFP. However, some errors still remain, and before we publish the individual talk videos on YouTube, we are seeking your expert assistance in reviewing the captions for your talk and correcting any remaining errors.

To review and correct your captions, please do the following by October 1:

1. Clone or download this repository.

2. Find the `sessionN.ass` file for the session in which your talk appeared. For example, if your talk appeared in the session "ICFP NY 1"/"ICFP Asia 1", then the file you want is `session1/session1.ass`.

3. Open the `sessionN.ass` file with any text editor of your choice. The caption files are in the Advanced SubStation Alpha file format, a simple text file format. In the file, you will see captions and timing information. For example:

Dialogue: 0,0:13:00.76,0:13:01.80,Default,,0,0,0,,ADAM CHLIPALA: Hello,\NI'm Adam Chlipala,
Dialogue: 0,0:13:01.80,0:13:03.84,Default,,0,0,0,,Program Chair of ICFP 2020.

4. Navigate to the place in the file where your own talk begins. You can find this part of the file by, for instance, searching for the speaker's name.

5. Review the captions for your talk and make any necessary corrections.  Please modify only the captions themselves, *not* the timing information.  You may wish to re-watch your talk video as you review the captions; all session videos are on YouTube at https://www.youtube.com/playlist?list=PLyrlk8Xaylp4fOgwO5RUTrpgSA_HRjDMW . If you see an instance of "`(INAUDIBLE)`" in the captions for your talk, this was a place where the professional captioner was unable to tell what was being said (and, unfortunately, neither were we). Fortunately, there are only a few such instances.  Note, however, that there are likely to be other captioning mistakes not tagged with `(INAUDIBLE)`.

6. After you've corrected captions for your talk (and only your talk, please), submit the corrections to us either by (1) making a pull request against this repo, or (2) emailing the edited file to <lkuper@ucsc.edu>. Method (1) is strongly preferred, but method (2) is fine, too.

Captions provide access to ICFP talks for Deaf and hard of hearing people, as well as people who might have some degree of hearing loss but who don't self-identify as hard of hearing or deaf. They are also useful for non-native speakers of English, English language learners, and people with dyslexia, auditory processing disorder, or ADHD. Last but not least, they provide a searchable text record of talk content. The better the quality of the captions, the more useful they are for all of these purposes -- so we thank you in advance for your help in making our captions as accurate as possible! 

Please feel free to reach out to us if you have questions or feedback about captions at ICFP.

Best,
Lindsey Kuper and Alan Jeffrey
Accessibility Co-chairs, ICFP 2020

## .ass to .srt conversion (for repo maintainers only, not ICFP/JFP authors)

To convert `sessionN.ass` file to `sessionN.srt`:
```
ffmpeg -i sessionN.ass -f srt - | sed -e 's|</*font[^>]*>||g' > sessionN.srt
```

The `.srt` files from AI Media have DOS line endings, the ones produced by `ffmpeg` have Unix, so the first time you check in an `.srt` file:

```
dos2unix */*.srt
```
