# openHAB-Alexa-SSML
Using openHAB and the [Amazon Echo Control Binding](https://www.openhab.org/addons/bindings/amazonechocontrol/) to run german [Speech Synthesis Markup Language (SSML)](https://developer.amazon.com/en-US/docs/alexa/custom-skills/speech-synthesis-markup-language-ssml-reference.html) examples.

## Items

For each SSML example we need to create a `Switch` item. If this `Switch` item changed to `ON` a rule with an `SSML` example will be triggered.

```
Group Amazon_EchoDot_SSML_Beispiele "SSML Beispiele" <movecontrol>

Switch Amazon_EchoDot_SSML_Beispiel1 "SSML Beispiel 1" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel2 "SSML Beispiel 2" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel3 "SSML Beispiel 3" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel4 "SSML Beispiel 4" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel5 "SSML Beispiel 5" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel6 "SSML Beispiel 6" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel7 "SSML Beispiel 7" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel8 "SSML Beispiel 8" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel9 "SSML Beispiel 9" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel10 "SSML Beispiel 10" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel11 "SSML Beispiel 11" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel12 "SSML Beispiel 12" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel13 "SSML Beispiel 13" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel14 "SSML Beispiel 14" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel15 "SSML Beispiel 15" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel16 "SSML Beispiel 16" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel17 "SSML Beispiel 17" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel18 "SSML Beispiel 18" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel19 "SSML Beispiel 19" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel20 "SSML Beispiel 20" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel21 "SSML Beispiel 21" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel22 "SSML Beispiel 22" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel23 "SSML Beispiel 23" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel24 "SSML Beispiel 24" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel25 "SSML Beispiel 25" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel26 "SSML Beispiel 26" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel27 "SSML Beispiel 27" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel28 "SSML Beispiel 28" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel29 "SSML Beispiel 29" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel30 "SSML Beispiel 30" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel31 "SSML Beispiel 31" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel32 "SSML Beispiel 32" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel33 "SSML Beispiel 33" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel34 "SSML Beispiel 34" <text> (Amazon_EchoDot_SSML_Beispiele)
Switch Amazon_EchoDot_SSML_Beispiel35 "SSML Beispiel 35" <text> (Amazon_EchoDot_SSML_Beispiele)
```

## Rules

Additionally to the SSML example items you have to create an `<textToSpeech_item>`. Therefore you need to configure the [Amazon Echo Control Binding](https://www.openhab.org/addons/bindings/amazonechocontrol/) and an `Amazo Echo` product. At least you have to create an `<textToSpeech_item>` item which are used for text to speech (tts).

```
//
// SSML = Speech Synthesis Markup Language --> Auszeichnungssprache für Sprachsynthese
//

rule "Running Alexa SSML Example 1"
when
    Item Amazon_EchoDot_SSML_Beispiel1 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Hier ist eine Zahl <w role="amazon:VBD">gelesen</w> als eine Kardinalzahl: <say-as interpret-as="cardinal">12345</say-as>. Hier ist ein Wort buchstabiert: <say-as interpret-as="spell-out">Hallo</say-as>.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel1.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 2"
when
    Item Amazon_EchoDot_SSML_Beispiel2 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="excited" intensity="medium">Fünf Sekunden bis zum Start! <say-as interpret-as="digits">54321</say-as>. Start!</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel2.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 3"
when
    Item Amazon_EchoDot_SSML_Beispiel3 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="disappointed" intensity="medium">Ich möchte dir ein Geheimnis verraten. <voice name="Kendra">Ich bin kein echter Mensch.</voice>. Kannst du das glauben?</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel3.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 4"
when
    Item Amazon_EchoDot_SSML_Beispiel4 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="disappointed" intensity="high">Ich möchte dir ein Geheimnis verraten. <voice name="Kendra">Ich bin kein echter Mensch.</voice>. Kannst du das glauben?</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel4.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 5"
when
    Item Amazon_EchoDot_SSML_Beispiel5 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><voice name="Kendra"><amazon:domain name="conversational">Ich wusste wirklich nicht, wie dieser Morgen beginnen würde. Und wenn ich das gewusst hätte, wäre ich vielleicht einfach im Bett geblieben.</amazon:domain></voice></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel5.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 6"
when
    Item Amazon_EchoDot_SSML_Beispiel6 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:domain name="conversational">Ich wusste wirklich nicht, wie dieser Morgen beginnen würde. Und wenn ich das gewusst hätte, wäre ich vielleicht einfach im Bett geblieben.</amazon:domain></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel6.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 7"
when
    Item Amazon_EchoDot_SSML_Beispiel7 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="disappointed" intensity="medium">Ich möchte dir ein Geheimnis verraten. </amazon:emotion><voice name="Kendra">Ich bin kein echter Mensch. </voice><amazon:emotion name="disappointed" intensity="high">Kannst du es glauben?</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel7.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 8"
when
    Item Amazon_EchoDot_SSML_Beispiel8 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:domain name="news">Letzte Neuigkeiten: Die Konversations- und Nachrichtenstile sind jetzt für die Stimmen von Matthew und Joanna verfügbar!</amazon:domain></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel8.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 9"
when
    Item Amazon_EchoDot_SSML_Beispiel9 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:domain name="music">Sweet Child O\' Mine von Guns N\' Roses wurde zu einer ihrer erfolgreichsten Singles und erreichte 1988 die Billboard Hot 100. Slashs Gitarrensolo bei diesem Song wurde als 37. bestes Solo aller Zeiten eingestuft. Hier ist Sweet Child O\' Mine.</amazon:domain></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel9.sendCommand(OFF)
    ])
end

rule "Running Alexa SSML Example 10"
when
    Item Amazon_EchoDot_SSML_Beispiel10 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:domain name="long-form">Darf ich vorstellen: Echo Dot. Unser beliebtester Echo ist jetzt noch besser. Mit einem neuen Lautsprecher und Design ist Echo Dot ein sprachgesteuerter Smart Speaker mit Alexa, perfekt für jeden Raum. Fragen Sie einfach nach Musik, Nachrichten, Informationen und mehr. Sie können auch fast jeden anrufen und kompatible Smart-Home-Geräte mit Ihrer Stimme steuern.</amazon:domain></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel10.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 11"
when
    Item Amazon_EchoDot_SSML_Beispiel11 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:domain name="fun">布団が、ふっとんだ。</amazon:domain></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel11.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 12"
when
    Item Amazon_EchoDot_SSML_Beispiel12 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><voice name="Matthew"><amazon:domain name="news">Letzte Neuigkeiten: Die Konversations- und Nachrichtenstile sind jetzt für die Stimmen von Matthew und Joanna verfügbar!</amazon:domain></voice><voice name="Joanna"><amazon:domain name="conversational">Das war alles für heute. Ich danke Ihnen.</amazon:domain></voice></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel12.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 13"
when
    Item Amazon_EchoDot_SSML_Beispiel13 changed to ON
then
    <textToSpeech_item>.sendCommand('<voice name="Matthew"><amazon:domain name="conversational">Ich wusste wirklich nicht, wie dieser Morgen beginnen würde. Und wenn ich das gewusst hätte, wäre ich vielleicht einfach im Bett geblieben.</amazon:domain></voice>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel13.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 14"
when
    Item Amazon_EchoDot_SSML_Beispiel14 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Ich möchte dir ein Geheimnis verraten. <amazon:effect name="whispered">Ich bin kein echter Mensch.</amazon:effect>. Kannst du das glauben?</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel14.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 15"
when
    Item Amazon_EchoDot_SSML_Beispiel15 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="excited" intensity="medium">Christina gewinnt diese Runde!</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel15.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 16"
when
    Item Amazon_EchoDot_SSML_Beispiel16 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="disappointed" intensity="high">Hier bin ich mit einem Gehirn von der Größe eines Planeten und sie bitten mich, ein Stück Papier aufzuheben.</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel16.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 17"
when
    Item Amazon_EchoDot_SSML_Beispiel17 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><amazon:emotion name="excited" intensity="medium">Okay, lasst uns bewusst sein und tief einatmen. <break time="3s"/>Fühlen wir uns jetzt nicht besser?</amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel17.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 18"
when
    Item Amazon_EchoDot_SSML_Beispiel18 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>So spreche ich normalerweise.<amazon:emotion name="disappointed" intensity="high"> So spreche ich, wenn ich enttäuscht bin. <prosody volume="x-loud">Jetzt sage ich Ihnen, dass ich sehr laut enttäuscht bin!</prosody></amazon:emotion></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel18.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 19"
when
    Item Amazon_EchoDot_SSML_Beispiel19 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Willkommen bei Ride Hailer.<audio src="soundbank://soundlibrary/transportation/amzn_sfx_car_accelerate_01" /> Sie können eine Fahrt bestellen oder einen Kostenvoranschlag anfordern. Was soll es sein?</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel19.sendCommand(OFF)
    ])
end


// sudo apt install ffmpeg
// niedrige Qualität:
// ffmpeg -i <input-file> -ac 2 -codec:a libmp3lame -b:a 48k -ar 16000 -write_xing 0 <output-file>
// hohe Qualität:
// ffmpeg -i <input-file> -ac 2 -codec:a libmp3lame -b:a 48k -ar 24000 -write_xing 0 <output-file>

/*
The MP3 files you use to provide audio must be hosted on an endpoint that uses HTTPS.
The endpoint must provide an SSL certificate signed by an Amazon-approved certificate
authority. Many content hosting services provide this. For example, you could host your
files at a service such as Amazon Simple Storage Service (Amazon S3)
(an Amazon Web Services offering).
https://aws.amazon.com/de/s3/
12 Monate kostenlos 5GB
*/


rule "Running Alexa SSML Example 20"
when
    Item Amazon_EchoDot_SSML_Beispiel20 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Hier gibt es eine drei Sekunden lange Pause <break time="3s"/>dann geht die Rede weiter.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel20.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 21"
when
    Item Amazon_EchoDot_SSML_Beispiel21 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Ich habe dir bereits gesagt, dass ich diese Person <emphasis level="strong">wirklich mag.</emphasis></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel21.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 22"
when
    Item Amazon_EchoDot_SSML_Beispiel22 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>In Paris sprechen sie es  <lang xml:lang="fr-FR">Paris</lang> aus.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel22.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 23"
when
    Item Amazon_EchoDot_SSML_Beispiel23 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><lang xml:lang="fr-FR">J\'adore chanter</lang></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel23.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 24"
when
    Item Amazon_EchoDot_SSML_Beispiel24 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><p>Dies ist der erste Absatz. Nach dem Sprechen dieses Textes sollte eine Pause gemacht werden.</p><p>Dies ist der zweite Absatz.</p></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel24.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 25"
when
    Item Amazon_EchoDot_SSML_Beispiel25 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Du sagst, <phoneme alphabet="ipa" ph="pɪˈkɑːn">pecan</phoneme>.Ich sage, <phoneme alphabet="ipa" ph="ˈpi.kæn">pecan</phoneme> für Pekannuss.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel25.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 26"
when
    Item Amazon_EchoDot_SSML_Beispiel26 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Normale Lautstärke für den ersten Satz. <prosody volume="x-loud">Lautere Lautstärke für den zweiten Satz</prosody>. Wenn ich aufwache, <prosody rate="x-slow">spreche ich ziemlich langsam</prosody>. Ich kann in meiner normalen Tonlage sprechen,<prosody pitch="x-high"> aber auch mit einer viel höheren Tonlage </prosody>, und auch <prosody pitch="low">mit einer tieferen Tonlage</prosody>.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel26.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 27"
when
    Item Amazon_EchoDot_SSML_Beispiel27 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><s>Dies ist ein Satz</s><s> Vor diesem zweiten Satz sollte eine kurze Pause gemacht werden</s> Dieser Satz endet mit einem Punkt und sollte die gleiche Pause haben.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel27.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 28"
when
    Item Amazon_EchoDot_SSML_Beispiel28 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Hier ist eine Zahl, die als Kardinalzahl gesprochen wird: <say-as interpret-as="cardinal">12345</say-as>. Hier ist dieselbe Zahl, wobei jede Ziffer einzeln gesprochen wird:<say-as interpret-as="digits">12345</say-as>. Hier wird ein Wort buchstabiert: <say-as interpret-as="spell-out">Hallo</say-as></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel28.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 29"
when
    Item Amazon_EchoDot_SSML_Beispiel29 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>So hört sich Alexa ohne SSML an.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel29.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 30"
when
    Item Amazon_EchoDot_SSML_Beispiel30 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Mein chemisches Lieblingselement ist <sub alias="Aluminium">Al</sub>, aber Thomas bevorzugt <sub alias="Magnesium">Mg</sub>.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel30.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 31"
when
    Item Amazon_EchoDot_SSML_Beispiel31 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Ich möchte dir ein Geheimnis verraten. <voice name="Kendra">Ich bin kein echter Mensch.</voice>. Kannst du das glauben?</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel31.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 32"
when
    Item Amazon_EchoDot_SSML_Beispiel32 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Hier ist eine Überraschung, die du nicht erwartet hast. <voice name="Kendra"><lang xml:lang="de-DE">Ich möchte dir ein Geheimnis verraten.</lang></voice><voice name="Brian"><lang xml:lang="de-AT">Dein Geheimnis ist bei mir sicher!</lang></voice><voice name="Kendra"><lang xml:lang="de-DE">Ich bin kein echter Mensch.</lang></voice>. Kannst du das glauben?</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel32.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 33"
when
    Item Amazon_EchoDot_SSML_Beispiel33 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Willkommen bei Ride Hailer. <voice name="Celine"><lang xml:lang="fr-FR">Bienvenue à Ride Hailer</lang></voice> Sie können eine Fahrt bestellen oder einen Kostenvoranschlag anfordern. Was soll es sein?</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel33.sendCommand(OFF)
    ])
end


rule "Running Alexa SSML Example 34"
when
    Item Amazon_EchoDot_SSML_Beispiel34 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak>Das Wort <say-as interpret-as="characters">read</say-as> kann interpretiert werden entweder als die einfache Gegenwartsform <w role="amazon:VB">read</w>, oder die Partizipform der Vergangenheit <w role="amazon:VBD">read</w>.</speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel34.sendCommand(OFF)
    ])
end

rule "Running Alexa SSML Example 35"
when
    Item Amazon_EchoDot_SSML_Beispiel35 changed to ON
then
    <textToSpeech_item>.sendCommand('<speak><voice name="Brian"><lang xml:lang="de-DE">Ich bin ein Berliner!</lang></voice></speak>')

    createTimer(now.plusNanos(1000000000), [ |
        Amazon_EchoDot_SSML_Beispiel35.sendCommand(OFF)
    ])
end
```

## Sitemaps

At least you have to add your items to the sitemap:

```
Text label="SSML Beispiele" {
    Switch item=Amazon_EchoDot_SSML_Beispiel1
    Switch item=Amazon_EchoDot_SSML_Beispiel2
    Switch item=Amazon_EchoDot_SSML_Beispiel3
    Switch item=Amazon_EchoDot_SSML_Beispiel4
    Switch item=Amazon_EchoDot_SSML_Beispiel5
    Switch item=Amazon_EchoDot_SSML_Beispiel6
    Switch item=Amazon_EchoDot_SSML_Beispiel7
    Switch item=Amazon_EchoDot_SSML_Beispiel8
    Switch item=Amazon_EchoDot_SSML_Beispiel9
    Switch item=Amazon_EchoDot_SSML_Beispiel10
    Switch item=Amazon_EchoDot_SSML_Beispiel11
    Switch item=Amazon_EchoDot_SSML_Beispiel12
    Switch item=Amazon_EchoDot_SSML_Beispiel13
    Switch item=Amazon_EchoDot_SSML_Beispiel14
    Switch item=Amazon_EchoDot_SSML_Beispiel15
    Switch item=Amazon_EchoDot_SSML_Beispiel16
    Switch item=Amazon_EchoDot_SSML_Beispiel17
    Switch item=Amazon_EchoDot_SSML_Beispiel18
    Switch item=Amazon_EchoDot_SSML_Beispiel19
    Switch item=Amazon_EchoDot_SSML_Beispiel20
    Switch item=Amazon_EchoDot_SSML_Beispiel21
    Switch item=Amazon_EchoDot_SSML_Beispiel22
    Switch item=Amazon_EchoDot_SSML_Beispiel23
    Switch item=Amazon_EchoDot_SSML_Beispiel24
    Switch item=Amazon_EchoDot_SSML_Beispiel25
    Switch item=Amazon_EchoDot_SSML_Beispiel26
    Switch item=Amazon_EchoDot_SSML_Beispiel27
    Switch item=Amazon_EchoDot_SSML_Beispiel28
    Switch item=Amazon_EchoDot_SSML_Beispiel29
    Switch item=Amazon_EchoDot_SSML_Beispiel30
    Switch item=Amazon_EchoDot_SSML_Beispiel31
    Switch item=Amazon_EchoDot_SSML_Beispiel32
    Switch item=Amazon_EchoDot_SSML_Beispiel33
    Switch item=Amazon_EchoDot_SSML_Beispiel34
    Switch item=Amazon_EchoDot_SSML_Beispiel35
}
```
