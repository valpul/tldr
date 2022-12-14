# dnf

> RHEL, Fedora மற்றும் CentOS க்கான தொகுப்பு மேலாண்மை பயன்பாடு (yum ஐ மாற்றுகிறது).
> மேலும் விவரத்திற்கு: <https://dnf.readthedocs.io>.

- நிறுவப்பட்ட தொகுப்புகளை புதிய கிடைக்கக்கூடிய பதிப்புகளுக்கு மேம்படுத்தவும்:

`sudo dnf upgrade`

- முக்கிய வார்த்தைகள் மூலம் தொகுப்புகளைத் தேடுங்கள்:

`dnf search {{முக்கிய வார்த்தைகள்}}`

- தொகுப்பு பற்றிய விவரங்களைக் காண்பி:

`dnf info {{நிரல்தொகுப்பு}}`

- புதிய தொகுப்பை நிறுவவும் (அனைத்து அறிவுறுத்தல்களையும் தானாக உறுதிப்படுத்த `-y` ஐப் பயன்படுத்தவும்):

`sudo dnf install {{நிரல்தொகுப்பு}}`

- ஒரு தொகுப்பை அகற்று:

`sudo dnf remove {{நிரல்தொகுப்பு}}`

- நிறுவப்பட்ட தொகுப்புகளை பட்டியலிடுங்கள்:

`dnf list --installed`

- கொடுக்கப்பட்ட கோப்பை எந்த தொகுப்புகள் வழங்குகின்றன என்பதைக் கண்டறியவும்:

`dnf provides {{கோப்பு}}`

- அனைத்து கடந்த செயல்பாடுகளையும் காண்க:

`dnf history`
