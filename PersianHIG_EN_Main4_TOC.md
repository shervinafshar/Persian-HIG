**Islamic Republic of Iran**

**National Management & Planning Organization**

**High Council of Informatics**

\
\

**Iran National Open Source Project**

Persian Graphical User Interface Specifications and Guidelines {.title-western dir="LTR"}
==============================================================

**English Edition**

**Public Release 1**

**18 Sep 2005**

\
\

**آیین‌نامۀ طرّاحی میانای کاربر گرافیکی فارسی**

**نگارش انگلیسی**

\
\

\
\

**کلیۀ حقوق مؤلف و ناشر محفوظ و مخصوص شورای عالی انفورماتیک جمهوری اسلامی ایران است****.**

با رعایت شرایط اجازه‌نامۀ مستندات آزاد گنو، (ویرایش ۱٫۲ یا ویرایش‌های بعدی که توسط بنیاد نرم‌افزار آزاد منتشر می‌شود) اجازۀ تکثیر، توزیع و/یا تغییر این اثر داده می‌شود. توضیح اینکه، این اثر فاقد «بخشهای ثابت»، «متن روی جلد» و «متن پشت جلد» مذکور در اجازه‌نامۀ فوق است. نسخه‌ای از اجازه‌نامه در بخش ضمائم با عنوان «اجازه‌نامۀ مستندات آزاد گنو» (به زبان انگلیسی) پیوست گردیده است.

\
\

**Copyright © 2004 High Council of Informatics of the Islamic Republic of Iran**

Permission is granted to copy, distribute and/or modify this document under the terms of the GNU Free Documentation License, Version 1.2 or any later version published by the Free Software Foundation; with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.

A copy of the license is included in the section entitled “GNU Free Documentation License”.

\
\

Table of Contents {.عنوان-مقدمه-western dir="LTR" style="page-break-before: always"}
-----------------

**[Persian Graphical User Interface Specifications and Guidelines 1](#__RefHeading__19_1392265381)**

[](#__RefHeading__21_1392265381)**[Table of Contents 1](#__RefHeading__21_1392265381)**

**[Chapter 1 Introduction 1](#__RefHeading__23_1392265381)**

[1.1. Summary and Purpose 1](#__RefHeading__25_1392265381)

[1.2. Scope 1](#__RefHeading__27_1392265381)

[1.3. Audience 2](#__RefHeading__29_1392265381)

[1.4. Mandate and Authority 3](#__RefHeading__31_1392265381)

**[Chapter 2 Principles of Graphical User Interface Design 4](#__RefHeading__33_1392265381)**

[2.1. Common Principles of GUI Design 4](#__RefHeading__35_1392265381)

[2.2. Applying GUI Design Principles to Persian 5](#__RefHeading__37_1392265381)

[2.3. Specifics of Bi-directional GUI Design 10](#__RefHeading__39_1392265381)

[2.4. Locale Requirements for Iran 14](#__RefHeading__41_1392265381)

[.2.4.1. Search and Sort 14](#__RefHeading__43_1392265381)

[.2.4.2. Calendar 15](#__RefHeading__45_1392265381)

[.2.4.3. Week 17](#__RefHeading__47_1392265381)

[.2.4.4. Naming GUI Objects 18](#__RefHeading__49_1392265381)

[2.5. Dual Language User Interface 19](#__RefHeading__51_1392265381)

**[Chapter 3 Persian Text in the GUI 21](#__RefHeading__53_1392265381)**

[3.1. Characteristics of the Persian Text 21](#__RefHeading__55_1392265381)

[3.2. Characteristics of the Persian Fonts 27](#__RefHeading__57_1392265381)

[.3.2.1. Persian vs. Latin Fonts 28](#__RefHeading__59_1392265381)

[.3.2.2. Persian Font Styles 29](#__RefHeading__61_1392265381)

[.3.2.3. Persian Font Size and Metrics 32](#__RefHeading__63_1392265381)

[.3.2.4. GUI Fonts 33](#__RefHeading__65_1392265381)

[.3.2.5. Classification of Persian Fonts 34](#__RefHeading__67_1392265381)

[.3.2.6. Persian OpenType Fonts 36](#__RefHeading__69_1392265381)

[.3.2.7. Other Font Issues 37](#__RefHeading__71_1392265381)

[3.3. Writing in Persian for the GUI 37](#__RefHeading__73_1392265381)

[3.4. Translating User Interface to Persian 37](#__RefHeading__75_1392265381)

[3.5. Persian Keyboard 38](#__RefHeading__77_1392265381)

[3.6. Entering and Editing Persian Text 42](#__RefHeading__79_1392265381)

[.3.6.1. Types of Text Editors 42](#__RefHeading__81_1392265381)

[.3.6.2. Persian Text Editing Issues 43](#__RefHeading__83_1392265381)

[.3.6.3. Shortcomings of the Existing Editors 43](#__RefHeading__85_1392265381)

[.3.6.4. Resolving Persian Text Editing Issues 44](#__RefHeading__87_1392265381)

[.3.6.5. Detecting Input and Edit Mode 44](#__RefHeading__89_1392265381)

[.3.6.6. Directionality Definitions 45](#__RefHeading__91_1392265381)

[.3.6.7. Cursor Visual Cues for Text Input/Edit 46](#__RefHeading__93_1392265381)

[.3.6.8. The Desired Text Input Behavior 48](#__RefHeading__95_1392265381)

[.3.6.9. Selecting Edit Location 49](#__RefHeading__97_1392265381)

[.3.6.10. The Desired Text Editing Behavior 53](#__RefHeading__99_1392265381)

[.3.6.11. Normalizing Text After Editing 61](#__RefHeading__101_1392265381)

[3.7. Text Engine Architecture 61](#__RefHeading__103_1392265381)

**[Chapter 4 The Visual Elements in the GUI 63](#__RefHeading__105_1392265381)**

[4.1. Paper Documents 63](#__RefHeading__107_1392265381)

[4.2. Icons and Images 68](#__RefHeading__109_1392265381)

[4.3. Direction and Placement of Visual Elements 70](#__RefHeading__111_1392265381)

[4.4. The Effect of Different Direction in Desktop, Software and Document 75](#__RefHeading__113_1392265381)

**[Chapter 5 Summary of User Interface Widgets 78](#__RefHeading__115_1392265381)**

[5.1. Introduction 78](#__RefHeading__117_1392265381)

[5.2. Window 78](#__RefHeading__119_1392265381)

[5.3. Dialog Box 79](#__RefHeading__121_1392265381)

[5.4. Scrollbar 79](#__RefHeading__123_1392265381)

[5.5. Menu Bar 80](#__RefHeading__125_1392265381)

[5.6. Menu 80](#__RefHeading__127_1392265381)

[5.7. Tool Bar 81](#__RefHeading__129_1392265381)

[5.8. Static Text 81](#__RefHeading__131_1392265381)

[5.9. Text Field 82](#__RefHeading__133_1392265381)

[5.10. Date/Time Field 83](#__RefHeading__135_1392265381)

[5.11. Spinbox 84](#__RefHeading__137_1392265381)

[5.12. Dropdown List 84](#__RefHeading__139_1392265381)

[5.13. Combo Box 85](#__RefHeading__141_1392265381)

[5.14. Group Box 85](#__RefHeading__143_1392265381)

[5.15. Tab Panel 85](#__RefHeading__145_1392265381)

[5.16. Button 86](#__RefHeading__147_1392265381)

[5.17. Slider 86](#__RefHeading__149_1392265381)

[5.18. Date Picker 87](#__RefHeading__151_1392265381)

[5.19. Check Box 87](#__RefHeading__153_1392265381)

[5.20. Radio Button 88](#__RefHeading__155_1392265381)

[5.21. List Box 88](#__RefHeading__157_1392265381)

[5.22. Tree List Box 88](#__RefHeading__159_1392265381)

[5.23. Text Ruler 89](#__RefHeading__161_1392265381)

[5.24. Progress Bar 90](#__RefHeading__163_1392265381)

[5.25. KDE Toolbox 91](#__RefHeading__165_1392265381)

[5.26. Composite Widgets 91](#__RefHeading__167_1392265381)

[5.27. Custom Widgets 91](#__RefHeading__169_1392265381)

[5.28. Limitations in GNOME and KDE 91](#__RefHeading__171_1392265381)

**[Appendix 94](#__RefHeading__173_1392265381)**

[](#__RefHeading__175_1392265381)**[Definitions 95](#__RefHeading__175_1392265381)**

[](#__RefHeading__177_1392265381)**[References 96](#__RefHeading__177_1392265381)**

[](#__RefHeading__179_1392265381)**[GNU Free Documentation License 100](#__RefHeading__179_1392265381)**

\
\

Chapter 1[Introduction](PersianHIG-EN-Main41.html) {.western dir="LTR" style="page-break-before: always"}
--------------------------------------------------

Chapter 2[Principles of Graphical User Interface Design](PersianHIG-EN-Main42.html) {.western dir="LTR" style="page-break-before: always"}
-----------------------------------------------------------------------------------

Chapter 3[Persian Text in the GUI](PersianHIG-EN-Main43.html) {.western dir="LTR" style="page-break-before: always"}
-------------------------------------------------------------

Chapter 4[The Visual Elements in the GUI](PersianHIG-EN-Main44.html) {.western dir="LTR" style="page-break-before: always"}
--------------------------------------------------------------------

Chapter 5[Summary of User Interface Widgets](PersianHIG-EN-Main45.html) {.western dir="LTR" style="page-break-before: always"}
-----------------------------------------------------------------------

\
\

