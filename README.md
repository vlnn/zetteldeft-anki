# zetteldeft-anki

![unit tests](https://github.com/vlnn/zetteldeft-anki/workflows/Shell%20Scripts%20Unit%20Testing/badge.svg)

Set of scripts to export of plain text zettels to deck of anki cards.

## Purpose

[Zetteldeft](https://github.com/EFLS/zetteldeft/) and similar software packages based on the [Zettelkasten concept](https://en.wikipedia.org/wiki/Zettelkasten) provide possibility to quickly store a big set of small notes being used as a "external brain". It's pretty easy to write down something, but it can be hard to find the information that has been stored long time ago, even when tags or full text search is used. Moreover, wouldn't it be nice to bring information from "external" brain to the "natural" one effectively? Review process should be used in order to keep most relevant things in your head, but while paper notes give you this possibility naturally (you read through seemingly unrelated stuff while looking for the card of your interest), this is not so with software-based setups. You either find whatever you're looking for in a fraction of a second or just drop the idea.

This is why I'm trying to set up the interface that will bind together data in your local directory full of org files with zettel-data and your [anki deck](https://apps.ankiweb.net/). This should provide you at least possibility to remember things that you've decided are valuable for you.

## Proof of concept stage

Several scripts should convert org files from the directory of your choice to json format and upload it using Anki Connect API. Convert is very simple and may result in unreadable or not-easy-to-use anki cards.

## Dependencies

- [Anki for your linux desktop](https://apps.ankiweb.net/)
- [AnkiConnect plugin](https://ankiweb.net/shared/info/2055492159)

## How it works

`z2a.sh --calls--> z2j.sh --converts--> j2a.sh --exports--> Anki Connect`

`z2a` is main interface for user, getting a zettels directory and deck name as an input.
`z2j` converts org format to json and feeds result to j2a
`j2a` exports json to Anki Connect

## Plans for future

- [ ] Make it work "good enough for me"
- [ ] Make it "good enough to be promoted among zettel-users"
- [ ] Potentially move from bash to elisp providing more integration with emacs
