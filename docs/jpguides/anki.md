# Anki Setup

<figure markdown="span">
    ![anki tan](../assets/images/anki-tan.png)
</figure>

### Download
Get the latest version from [Official Anki Download Page](https://apps.ankiweb.net/#downloads).

### Preferences
Go to `Tools→Preferences` and set all settings as below. Configure **Answer Keys** to your liking.

![anki preferences](../assets/images/anki_preferences1.png)

#### Apperance Tab
![anki preferences](../assets/images/anki_preferences2.png)

#### Review Tab
![anki preferences](../assets/images/anki_preferences3.png)

#### Editing Tab
![anki preferences](../assets/images/anki_preferences4.png)

#### Syncing Tab
Log into your AnkiWeb Account on **Syncing** page.
![anki preferences](../assets/images/anki_preferences5.png)

#### Other Tabs
Set remaining tabs to whatever.

### Presets
Click on your deck's `settings knob → options` and setup the default preset for Japanese decks:

* 10 new cards a day
* All available reviews
* New cards with 5min → 15min steps
* Failed cards with 10min → 1hour steps
* After 5 failed reviews card is suspended

![anki presets](../assets/images/anki_presets.png)

### Note Type
My favourite Anki Note Type for Japanese is [jp-mining-note](https://github.com/arbyste/jp-mining-note). You can find installation gudie [here](https://arbyste.github.io/jp-mining-note/setup/#installing-jp-mining-note). After that you can read through [Reference](https://arbyste.github.io/jp-mining-note/ui/) to understand card structure and Note Type features.

!!! example
    You can download [my sample card](https://drive.google.com/file/d/1EpV1fMM3mi5A1MsDRPjv_sGjAWMqP-bF/view?usp=sharing) to see how I usually use this template. The only thing I changed is the field order to make card creation a bit easier.

![anki note type](../assets/images/anki_note_type.png)

One of my favourite things about this note is that you can hover over kanji and see in which your other card this kanji was used. Very helpful to make connections between cards and increase retantion rate.

![anki note type](../assets/images/anki_note_type2.png)

!!! warning
    Card will create a warning if you have multiple cards for the same word. I personally ignore them and don't mind having multiple cards in multiple contexts for complicated words.

### Add-ons

Highly recommended to install listed below essential add-ons. Navigate to `Tools→Add-ons`, push `Get Add-ons...`, and type the code according to addon page. Then some of these add-ons will have `Config` option or separate settings button in `Tools` tab which you can tweak up to your liking. I leave everything at default, except Review Heatmap.

#### Essential add-ons

* [**AnkiConnect**](https://ankiweb.net/shared/info/2055492159) (2055492159): essential add-on to connect anki to external apps such as yomitan dictionaries
* [**AJT Japanese for JP Mining Note**](https://ankiweb.net/shared/info/200813220) (200813220): furigana and pitch accent generator for jp-mining-note Note Type
* [**Review Heatmap**](https://ankiweb.net/shared/info/1771074083) (1771074083): review activity visualization GitHub style

#### Optional add-ons

* [**VOICEVOX Japanese Text To Speech Audio Generator**](https://ankiweb.net/shared/info/366960193) (366960193): AI TTS generator
* [**Kanji Grid Kuuube**](https://ankiweb.net/shared/info/1610304449) (1610304449): learnt kanji visualization
* [**FSRS Helper**](https://ankiweb.net/shared/info/759844606) (759844606): additional useful functionality for anki scheduler
* [**Advanced Browser**](https://ankiweb.net/shared/info/874215009) (874215009): more features to anki browser

#### Settings
Navigato to `Tools→Add-ons→Config` to edit add-on's json config or go to respective gui context menu, usually located in `Tools` tab.

##### AnkiConnect
Add links for asbplayer and ttsu e-book reader by modifying the json like this:

```json
{
    "apiKey": null,
    "apiLogPath": null,
    "ignoreOriginList": [],
    "webBindAddress": "127.0.0.1",
    "webBindPort": 8765,
    "webCorsOriginList": [
        "http://localhost",
        "https://killergerbah.github.io",
        "https://reader.ttsu.app"
    ]
}
```

##### AJT Japanese

TODO: add copy button to the code and make scrolling a bit nicer

These are the settings that I use to generate furigana for sentences and words and pitch accents for JP Mining Note:

```json
{
    "audio_settings": {
        "attempts": 4,
        "audio_download_timeout": 6,
        "dictionary_download_timeout": 30,
        "ignore_inflections": false,
        "maximum_results": 99,
        "search_dialog_field_name": "VocabAudio",
        "stop_if_one_source_has_results": false,
        "tag_separator": "<br>"
    },
    "audio_sources": [
        {
            "enabled": false,
            "name": "NHK-2016",
            "url": "https://github.com/Ajatt-Tools/nhk_2016_pronunciations_index/releases/download/v1.3/NHK-2016_main.zip"
        },
        {
            "enabled": false,
            "name": "NHK-1998",
            "url": "https://github.com/Ajatt-Tools/nhk_1998_pronunciations_index/releases/download/v1.2/NHK-1998_main.zip"
        },
        {
            "enabled": false,
            "name": "Shinmeikai-8",
            "url": "https://github.com/Ajatt-Tools/shinmeikai_8_pronunciations_index/releases/download/v1.5/Shinmeikai-8_main.zip"
        },
        {
            "enabled": false,
            "name": "Daijisen",
            "url": "https://github.com/Ajatt-Tools/daijisen_pronunciations_index/releases/download/v1.0/Daijisen_main.zip"
        },
        {
            "enabled": false,
            "name": "TAAS",
            "url": "https://github.com/Ajatt-Tools/taas_pronunciations_index/releases/download/v1.0/TAAS_main.zip"
        }
    ],
    "cache_lookups": 1024,
    "context_menu": {
        "browser_search": true,
        "generate_furigana": true,
        "literal_pronunciation": true,
        "look_up_word": true,
        "to_hiragana": true,
        "to_katakana": true
    },
    "definitions": {
        "behavior": "append",
        "destination": "VocabDef",
        "dict_name": "meikyou",
        "remove_marks": true,
        "search_type": "exact",
        "source": "VocabKanji",
        "timeout": 10
    },
    "furigana": {
        "blocklisted_words": "人",
        "discard_mode": "discard_extra",
        "maximum_results": 1,
        "mecab_only": "彼,猫,首,母,顔,木,頭,私,弟,空,体,行く",
        "prefer_literal_pronunciation": false,
        "reading_separator": ", ",
        "skip_numbers": true
    },
    "last_file_save_location": "",
    "pitch_accent": {
        "blocklisted_words": "こと,へ,か,よ,ん,だ,び,の,や,ね,ば,て,と,た,が,に,な,は,も,ます,から,いる,たち,てる,う,ましょ,たい,する,です,ない",
        "discard_mode": "discard_extra",
        "kana_lookups": true,
        "lookup_shortcut": "Ctrl+8",
        "maximum_results": 100,
        "output_hiragana": false,
        "reading_separator": "・",
        "skip_numbers": true,
        "style": "none",
        "word_separator": "、"
    },
    "profiles": [
        {
            "destination": "SentenceReading",
            "mode": "furigana",
            "name": "Add furigana for sentence",
            "note_type": "JP Mining Note",
            "overwrite_destination": false,
            "source": "Sentence",
            "split_morphemes": true,
            "triggered_by": "focus_lost,toolbar_button,note_added,bulk_add"
        },
        {
            "destination": "VocabFurigana",
            "mode": "furigana",
            "name": "Add furigana for word -- UNUSED BY jp-mining-note",
            "note_type": "AJT_JAPANESE_IGNORE_PROFILE",
            "overwrite_destination": false,
            "source": "VocabKanji",
            "split_morphemes": false,
            "triggered_by": "focus_lost,toolbar_button,note_added,bulk_add"
        },
        {
            "destination": "AJTWordPitch",
            "mode": "pitch",
            "name": "Add pitch accent for word",
            "note_type": "JP Mining Note",
            "output_format": "html",
            "overwrite_destination": false,
            "source": "Word",
            "split_morphemes": false,
            "triggered_by": "focus_lost,toolbar_button,note_added,bulk_add"
        },
        {
            "destination": "VocabAudio",
            "mode": "audio",
            "name": "Add audio for word -- UNUSED BY jp-mining-note",
            "note_type": "AJT_JAPANESE_IGNORE_PROFILE",
            "overwrite_destination": false,
            "source": "VocabKanji",
            "split_morphemes": false,
            "triggered_by": "focus_lost,toolbar_button,note_added,bulk_add"
        }
    ],
    "toolbar": {
        "add_definition_button": {
            "enabled": false,
            "shortcut": "",
            "text": "意"
        },
        "audio_search_button": {
            "enabled": false,
            "shortcut": "",
            "text": "検"
        },
        "clean_furigana_button": {
            "enabled": false,
            "shortcut": "",
            "text": "削"
        },
        "furigana_button": {
            "enabled": false,
            "shortcut": "",
            "text": "振"
        },
        "generate_all_button": {
            "enabled": false,
            "shortcut": "Alt+P",
            "text": "入"
        },
        "hiragana_button": {
            "enabled": false,
            "shortcut": "",
            "text": "平"
        },
        "regenerate_all_button": {
            "enabled": false,
            "shortcut": "Alt+;",
            "text": "再"
        }
    }
}
```

##### Review Heatmap
I recommend to put heatmap `Tools→Review Heatmap Options...` in **Continuous Timeline** for better looks.
![anki heatmap](../assets/images/anki_heatmap_settings2.png)

### Finish
Now your Anki Setup should be completed, congratulations! :star:

As the next setup, you can go to [setting up Yomitan](/jpguides/yomitan/) for quick look ups and easy card creation.

### Thanks

* [Damien Elmes](https://github.com/dae) and [Anki Team](https://github.com/ankitects/anki/graphs/contributors) for the best software in existence
* [Shigeyuki](https://www.reddit.com/user/Shige-yuki/) for Anki-tan
* [Aquafina-water-bottle](https://github.com/Aquafina-water-bottle) and [arbyste](https://github.com/arbyste) for [jp-mining-note](https://github.com/arbyste/jp-mining-note)