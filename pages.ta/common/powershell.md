# powershell

> குறிப்பாக கணினி நிர்வாகத்திற்காக வடிவமைக்கப்பட்ட கட்டளை வரி ஷெல் மற்றும் ஸ்கிரிப்டிங் மொழி.
> மேலும் பார்க்கவும்: `pwsh`.
> மேலும் விவரத்திற்கு: <https://learn.microsoft.com/windows-server/administration/windows-commands/powershell>.

- ஊடாடும் ஷெல் அமர்வைத் தொடங்கவும்:

`powershell`

- தொடக்க கட்டமைப்புகளை ஏற்றாமல் ஊடாடும் ஷெல் அமர்வைத் தொடங்கவும்:

`powershell -NoProfile`

- குறிப்பிட்ட கட்டளைகளை இயக்கவும்:

`powershell -Command "{{echo 'பவர்ஷெல் செயல்படுத்தப்படுகிறது'}}"`

- ஒரு குறிப்பிட்ட ஸ்கிரிப்டை இயக்கவும்:

`powershell -File {{பாதை/டு/ஸ்கிரிப்ட்.ps1}}`

- பவர்ஷெல்லின் குறிப்பிட்ட பதிப்பைக் கொண்டு அமர்வைத் தொடங்கவும்:

`powershell -Version {{பதிப்பு}}`

- தொடக்க கட்டளைகளை இயக்கிய பிறகு ஷெல் வெளியேறுவதைத் தடுக்கவும்:

`powershell -NoExit`

- பவர்ஷெல்லுக்கு அனுப்பப்பட்ட தரவின் வடிவமைப்பை விவரிக்கவும்:

`powershell -InputFormat {{Text|XML}}`

- பவர்ஷெல்லின் வெளியீடு எவ்வாறு வடிவமைக்கப்படுகிறது என்பதைத் தீர்மானிக்கவும்:

`powershell -OutputFormat {{Text|XML}}`
