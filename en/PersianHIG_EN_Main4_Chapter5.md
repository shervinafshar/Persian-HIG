
Chapter 5 - Summary of User Interface Widgets
---------------------------------------------

### 5.1. Introduction

If you have jumped here straight from the table of the contents to get to the actual meat of this document, you are in the wrong place. The key information provided in this document is located in the chapters 2 through 4. This chapter is a small reference catalog of the key user interface widgets and their behavior in Persian/Iran locale. To understand this chapter, you should first read the previous chapters.

We have listed the main GUI widgets common in GUI toolkits without distinguishing their implementation in different GUI toolkits such as KDE and GNOME. Only notable differences among the implementation are mentioned.

Specialized and composite widgets are not presented individually. Instead we have mentioned general points regarding the proper localization of such widgets. The last section of this chapter mentions some of the shortcomings in the major GUI toolkits KDE (Qt) and GNOME (GTK).

### 5.2. Window

The shape and control widget placement of the window depends on the active theme. The window in many themes does not require special localization. Themes that put window title in the left side are not suitable for Persian/Iran locale and should preferably mirror the title placement for Persian/Iran locale. A centered window label is recommended to avoid localization issue for right-to-left locales.

The other consideration about the window behavior is the window placement and stacking behavior. Since the most documents that are used in Persian/Iran locale are Persian documents with right-to-left layout, it is recommended the upper right corner of each document window being placed in a suitable and predictable place, regardless of the window width. So, it is better to arrange documents by stacking their top right corner (offsetting each new window a little to the left and down) when the Persian/Iran locale is active. The other solution is center placement of the windows which does not create a very good stacking if the windows and is not recommended.

### 5.3. Dialog Box

Dialog boxes are special types of windows that usually have modal behavior and have a group of action buttons that dismiss the window (instead of using the window control widgets to close them). The localization issues of dialog boxes are similar to that of the regular windows. The special notes about button placement on the dialog boxes are discussed in the section for buttons.

### 5.4. Scrollbar

The scrollbar is placed on the edge of the windows or on the edges of lists and tables to facilitate scrolling them to reveal the off-screen content. The issues to note for localizing them for Persian/Iran locale are:

Vertical scrollbar is placed on the right edge of the window or list/table in Latin locales. It is not mandatory to flip it to the left edge of the frames but this relocation is acceptable and is recommended is the environment is expected to be mostly localized in Persian with most of the documents being in Persian, too. The placement of vertical scrollbar does not follow the directionality of the active document. It should be always placed in the same consistent side of the frames regardless of whether a given application is actually localized or whether the document has the same direction as the active locale (which determines the placement of the scrollbar).

The default scroll thumb position for vertical scrollbar in Persian/Iran locale is the top of the scroll bar unless another scroll position is saved along with the document.

The horizontal scroll bar is universally placed on the bottom edge of the frame it is scrolling. The default scroll thumb position for horizontal scrollbar following the direction of the content being scrolled: If the content is right-to-left (the usual case in Persian/Iran locale) the scroll thumb is placed to the right, so that the right side of the content is exposed. If the content is left-to-right (even when Persian/Iran locale is active) the scroll thumb is placed to the left, so that the left side of the content is exposed.

### 5.5. Menu Bar

A menu bar is usually placed on the top edge of the window. The menu bar is one of the user interface elements that are text oriented and is usually read like text. For this reason, the menu bar should be right aligned and be right-to-left for the Persian/Iran locale. It should have the same directionality and alignment for each locale regardless of the actual language of the active application or document. Mirroring of the menu bar should always be complete, a left aligned menu bar that is right-to-left, or a right aligned menu bar that is left-to-right is never acceptable. So, if there is some technical limitation is completely changing both alignment and direction of the menu bar for the Persian/Iran locale, it should not change partially.

The alignment and direction of the menu that is opened by selecting each menu bar item should have the same directionality and alignment as the menu bar itself.

If the menu titles in the menu bar include an icon, when the menu bar becomes right-to-left for the Persian/Iran locale, the icons should also be placed to the right of the menu title.

To highlight the keyboard equivalent for a menu title, it is not recommended to use single character underlining. Changing the color of the character or its background is recommended for the Persian/Iran locale.

### 5.6. Menu

In Persian/Iran locale, menus are right aligned and right to left. A submenu marker appears at the left side of the menu and if the available space permits, the submenus open to the left of the parent menu. All of the menu items regardless of their actual language follow this rule. The menu title is also right aligned relative to the menu frame.

If the items in the menu bar include an icon or other mark, when the menu becomes right-to-left for the Persian/Iran locale, the icons and marks should also be placed to the right of the menu item.

To highlight the keyboard equivalent for a menu item, it is not recommended to use single character underlining. Changing the color of the character or its background is recommended for the Persian/Iran locale.

### 5.7. Tool Bar

Toolbar may or may not follow the writing direction. For example, the placement of the items may depend on which corner of the screen it is placed on. Also, the button arrangement on the toolbar may follow a convention that does not follow the writing direction, such as the arrangement of the buttons that mimic audio/visual equipment. For this reason, it is recommended that GUI toolkits provide more options in determining the directionality and placement of the buttons on a toolbar. It is advised that they support such logical placements as the same as text direction or opposite text direction as well as physical ordering such as left-to-right or right-to-left. Also, a group of the buttons may have a given order while the other groups of the buttons follow a different order.

In the usual case, where there are no special placement requirements for the toolbar buttons, the direction and alignment of the toolbar should be similar to menu bar with similar considerations such as avoiding partial change of its directionality.

### 5.8. Static Text

Static text is not usually stand alone in the user interface. It is usually part of a larger layout that uses other blocks of static text and other widgets. The proper placement of the static text relative to the other widgets in the logical group is determined by the actual language of those elements and not the directionality of the active Persian/Iran locale. So, even in Persian/Iran locale, if a related group of widgets that include static text (and are read like text) are in English, their placement should follow left-to-right placement. For example, if the static text is a label for another widget, the relative order of text and the widget should follow the proper display order of the language of the static text block. The following picture shows a partially localized screen in right-to-left locale, where the placements of all widgets follow the locale direction instead of the actual text direction:

![](img/PersianHIG_EN_Main4_Chapter5_768dd48b.png) **Wrong!**

The placement of the highlighted static text compared to the widgets they are labeling is incorrect.

Since as we mentioned it is not realistic to assume that all of the applications used in Persian/Iran locale will be fully localized, the behavior of the window layout in some of the existing toolkits (especially GTK) needs enhancements to properly support the cases where the actual language of the GUI does not follow the active system locale.

Since Persian fonts may have swashes and floating marks that fall outside of the nominal boundary of the characters, the clipping region around the static text should have some additional drawable margin around the nominal bounding box of the text. A margin of at least one or two pixels is recommended. Also it is recommended that putting static text elements too close to other elements be avoided for the same reason.

### 5.9. Text Field

To properly support various scenarios that can arise in the Persian/Iran locale, the text fields should preferably provide the flexibility of setting the text direction and alignment on a per field basis.

Similar to the placements of static text, the relative placement and orientation of the text fields should follow the actual language used in them and the surrounding related elements such as the labeling static text. Refer to the figure in the previous section. If a set of related text fields are used for numeric data entry their placement may follow numeric (left-to-right) order.

Since Persian fonts may have swashes and floating marks that fall outside of the nominal boundary of the characters, the clipping region around the editable text should have some additional drawable margin around the nominal bounding box of the text. A margin of at least one or two pixels is recommended.

If the text field is a single-line field with automatic horizontal scrolling support, it should behave properly with right-to-left and bidirectional text. The easiest way to get a reasonable display in all cases while auto-scrolling is trying to keep the visual location of the text cursor in the middle of the field instead of close to a side.

The text input and editing behavior is expected to support the behavior described in Chapter 3.

### 5.10. Date/Time Field

Date, Time and Date/Time fields usually represent numerically oriented information. The order of the date components despite each component being numeric (hence left-to-right) is right-to-left. As a result, if the date field is broken into component subfields, the correct subfield order would be right to left. On the other hand, time components are left-to-right, if the time field is broken into component subfields, the correct subfield order would be left to right. If there is a button next to field to provide a visual chooser window to aid in data entry, such a button may stay in the current right side location similar to Latin locales, but is preferred to be placed to the left side of the field or field group in Persian/Iran locale.

The display format and other information regarding date and time in Persian locale can be found in the following Persian document: [Locale’03]

نیازهای شرایط محلی برای زبان فارسی ایران

The data entry order of the time components in Persian/Iran locale are: Hour, minute, second.

The data entry order of the date components in Persian/Iran locale are: Day, month, year.

The default calendar used to interpret the date entry is *Hijri Shamsi* unless otherwise specified by the user. The date input according to any of the calendars used in Iran should be supported without requiring a change in the active calendar. This is achieved by appending a single character suffix to the date input. These suffix characters include: U+0634 ش for *Hijri Shamsi*, U+0642 ق for *Hijri Qamari* and U+0645 م for Gregorian (م is the first character of the word *Miladi* میلادی which is the name of the Gregorian calendar in Iran)

The localized applications should display a calendar suffix when displaying dates that are not expressed in the currently active default calendar.

If the expected default calendar in a date input field differs from the global default calendar, this should be clearly indicated in or around the date field (e.g. by a suffix label next to date field).

Naturally, the numeric components of the date and time fields are normally entered using the Persian digits (U+06F0 to U+06F9) which should be supported in addition to the ASCII digits.

### 5.11. Spinbox

The spinbox is the small vertical rectangle that has two small up arrow and down arrow buttons used to rotate the numeric values in fields. It is always associated to an input field. In the Persian locale, the proper placement of this widget follows numeric direction, which means it appears to the right of the field that it affects.

Naturally, the numeric values controlled by this widget should support the Persian digits (U+06F0 to U+06F9) in addition to the normal ASCII digits.

### 5.12. Dropdown List

In Persian/Iran Locale the direction and orientation of this widget defaults to right-to-left behavior, but follows the text direction of its actual content and the language of the related surrounding widgets such as its static text label. So, even if the locale is set to Persian/Iran, in software with English GUI, it should still appear the same as it does in a Latin locale. If the widget along with its label is read from right-to-left, then the list button should be placed on the left side and the text direction in the widget should be right-to-left. In this case, the selection list should be right aligned. The text label of this widget in this case will be placed to its right. The position of the scrollbar of the choice list of this widget always follows the global scrollbar placement strategy regardless of the direction of this widget.

### 5.13. Combo Box

In Persian/Iran Locale the direction and orientation of this widget defaults to right-to-left behavior, but it follows the text direction of its actual content and the language of the related surrounding widgets such as its static text label. So, even if the locale is set to Persian/Iran, in software with English GUI, it should still appear the same as it does in a Latin locale. If the widget along with its label is read from right-to-left, then the list button should be placed on the left side and the text direction in the widget should be right-to-left. In this case, the selection list should be right aligned. The text label of this widget in this case will be placed to its right. The position of the scrollbar of the choice list of this widget always follows the global scrollbar placement strategy regardless of the direction of this widget.

The behavior of scrolling and text editing of the editable text in this widget is the same as the text field described in section 5.9.

### 5.14. Group Box

A group box is used to visually group some related widgets together. A group box may contain a text title. Normally, the members of a group follow the same text directionality. This should be reflected in the alignment and placement of the widgets in a group box. The alignment and direction of the title of the group box also follows the same direction as the group. The direction of the group defaults to right-to-left in Persian/Iran locale but follows the actual language of group box title and the language dominate in the widgets inside the group box. The only part of a group box that is actually affected by its direction is the alignment and direction of the text of its title.

### 5.15. Tab Panel

The order and placement of tab panels in Persian/Iran locale follows the global locale direction. It is also fully acceptable if its orientation follows the direction of the actual language of the GUI being displayed. When tab panel has right-to-left orientation, the tabs are either right aligned or center aligned (depending on theme) and the tabs are ordered from right-to-left (the first tab being the rightmost one). The overflow of the tabs is indicated on the left side of the tabs. If the tabs have icons in addition to title, the icon appears to the right of the title.

### 5.16. Button

There are many different types of buttons with different combinations and arrangements of text and icons, or possibly sticky behavior. The localization of the button itself is similar to the other widgets. The text in the widget is usually centered and the directionality of the text follows the actual language of the text, defaulting to right-to-left for Persian/Iran locale. If an icon is displayed besides the text it may be placed both before and after the text if the text is centered. If the text is right aligned the suggested position of the icon is the right side of the text and if it is left aligned the suggested position is to the left of the text.

The relative position of the buttons is not closely coupled to the text direction of the GUI. For example, both a “Yes” then “No” and “No” then “Yes” arrangement of buttons is acceptable. The important point regarding the arrangement of the buttons is that they follow a consistent ordering scheme, based on their use and effect. So, the position of normal buttons should be the same in a given locale regardless of the actual language of the GUI being displayed. For example if you put “OK” button to the left of “Cancel” button in Persian/Iran locale, it should be placed in the same way whether the actual GUI is in Persian or English.

If a group of buttons is arranged in a way that they are expected to be read like text, their order should follow the text direction of their actual text. This is rarely the case, though.

If a group of buttons model a real world group of buttons (such as buttons in some electronic equipment) they should follow the arrangement of the real world group of buttons. In this case the text direction of the GUI is irrelevant.

### 5.17. Slider

The slider widget is normally used to enter information that may be represented by numbers or numeric ratios. Slider is also used to simulate some real world objects such as similar sliders found on electronic equipment. This means that usually the orientation and direction of a horizontal slider has nothing to do with text direction and should not change depending on locale text direction. Generally, the side of a slider that represents the smaller amount is the left side. In Persian/Iran locale unlike most other widgets, the near end of slider is the left end and the far end of it is its right end.

### 5.18. Date Picker

Date picker is a widget usually shaped like a tiny month calendar that permits the selection or display of a calendar date or multiple calendar dates. When this widget is used in Persian/Iran locale, its layout should conform to the description of the calendar layout in the following Persian document: [Locale’03]

نیازهای شرایط محلی برای زبان فارسی ایران

The default calendar shown by this widget is the *Hijri Shamsi* calendar, unless a different calendar is specified by the user. The calendar displayed by this widget should be selectable without the need for globally changing the default calendar. This can be achieved by putting a small button that is used to rotate the calendars and show the abbreviated calendar designator next to the displayed year. If this widget is enlarged so that the available space in each day cell permits, it is recommended that the widget shows multiple calendars simultaneously as it is the norm in Persian calendars.

### 5.19. Check Box

Each checkbox is usually part of a larger logical group of widgets that consist of a heading or title (as static text or group box) and a set of checkboxes. It may also sometimes act as the label for a text field or other similar widget. The default direction and orientation of this widget in Persian/Iran locale is right-to-left, meaning that the box of the checkbox is placed to the right side and the text of the checkbox is right-to-left and right-aligned in its bounding box, This control is text oriented and its directionality is determined by the actual language of the group it belongs to. So, it should appear left-to-right in Persian locale if the actual language of the active GUI is English. But if the group language is Persian, even if one checkbox in the group has only English text, it should still appear right-to-left. A group of checkboxes are normally aligned so that the boxes of them are lined up.

The check mark image in the check box does not need mirroring when the checkbox is right-to-left.

### 5.20. Radio Button

Each individual radio button is always part of a larger logical group of widgets that consist of a usually a heading or title (as static text or group box) and a set of radio buttons. Each radio button may also sometimes act as the label for a text field or other similar widget. The default direction and orientation of this widget in Persian/Iran locale is right-to-left, meaning that the circle of radio button is placed to the right side and the text of the radio button is right-to-left and right-aligned in its bounding box, This control is text oriented and its directionality is determined by the actual language of the group it belongs to. So, it should appear left-to-right in Persian locale if the actual language of the active GUI is English. But if the group language is Persian, even if one radio button in the group has only English text, it should still appear right-to-left. A group of radio buttons are normally aligned so that their buttons are lined up.

### 5.21. List Box

In the Persian/Iran locale the direction and column order of this widget is right-to-left. This means that the direction of the text in each sell is right-to-left and the text in the cell is right-aligned. The order of the columns in this case is also right to left. The direction of the columns may be different based on the data type and the language of the content. In this case the column order usually stays right-to-left. The table itself may be left-to-right; even if it has some right-to-left text columns. Generally, it is best to have control over the directionality of table and its individual columns. So, a multi-column list box is a composite entity with multiple directionality attributes (directionality of each column, and the entire table). If the actual language of the active user interface is left-to-right, it is recommended that the list box stays left-to-right, even if the active locale is Persian/Iran.

It is also advised that the list box widget be flexible enough to let the developer (or localizer) set the alignment of individual columns and column headers in addition to the column directions.

### 5.22. Tree List Box

This widget is very similar to a normal list box. The difference is that the first column (rightmost column if the table direction is right-to-left) is a tree with expandable nodes. If the image of the expand/collapse widget of the nodes is not symmetrical, it needs to be mirrored when the tree is right-to-left. In a tree list box, the direction of the first column (the tree column) and the entire table should always be the same. The other considerations are similar to the list box widget described in 5.21.

### 5.23. Text Ruler

The text ruler is not a built-in widget in most of the GUI toolkits. This widget is commonly used in text editing and word processing applications when custom tab stops and paragraph margins are supported. It is typically custom built by the developers of the word processing applications. There are two types of text rulers that are commonly used. A text ruler is either page oriented (the zero point is on the edge of the paper) or column oriented (the zero point is on the edge of the active text column). Both rulers may be present in an application especially in page layout applications.

The zero point and placement of the page ruler depends on document properties including its direction, binding and whether it is double sided or single sided. This ruler should not change as the result of activating different paragraphs with different directions.

The zero point and placement of the column ruler usually follows the direction of the active paragraph. The zero point of this ruler is placed on the edge of the column that corresponds to the starting edge of the paragraph (the right edge in right-to-left text). If the direction of the active paragraph is changed, the direction of the ruler also changes and the layout control handles on the ruler also flip to indicate the new start and end of the paragraph. Also, the default alignment of the tab stops is flipped in this case.

It is recommended that word processing applications that support bidirectional layout, support both types of the rulers described above and also have the ability to show both of them simultaneously. This is illustrated in the following figure:

![](img/PersianHIG_EN_Main4_Chapter5_799d9f99.png)

The behavior of the text on tab stops should be visual and does not follow the stream of text across the tab boundary. So, the text should be first segmented into separate fields that fall on each tab stop and the Unicode bidirectional algorithm should be applied on each segment individually. The direction of the movement of the tab character is always determined by the paragraph direction and is never resolved with Unicode bidirectional algorithm.

In the Persian/Iran locale the default document and paragraph directions are right-to-left, so the default ruler direction for both types of rulers is right-to-left.

### 5.24. Progress Bar

The progress bar is used to indicate the ratio of the progress of a certain task as a horizontal bar chart. In the Persian/Iran locale the direction of this widget follows the mathematical direction and is left-to-right just like it is in the Latin locales. In Persian/Iran locale unlike most other widgets, the near end of progress bar is the left end and the far end of it is its right end.

### 5.25. KDE Toolbox

This widget is KDE specific. In the Persian/Iran locale it is recommended that this widget be mirrored and placed on the right side of the window. Although it is preferable to actually follow the direction of the language of the active application and stay left-to-right if the application is not localized in Persian.

### 5.26. Composite Widgets

Designing composite widgets should take into consideration the different directional requirements and options that has been described in the previous chapter and this chapter. It should also be based on the principle of chapter 2 and properly support Persian text as described in chapter 3. It is advised that some flexibility is provided in the direction and positioning of its elements instead of having one fixed directional behavior for it.

### 5.27. Custom Widgets

Application may create custom widgets from scratch. In this case the most difficult part of their creation is supporting proper bidirectional behavior for the widgets. For this reason, avoid creating custom widgets unless you have a very good reason for it. If you do create custom widgets pay close attention to its internationalization and bidirectional layout behavior.

### 5.28. Limitations in GNOME and KDE

Practically all of the existing GUI toolkits for GNU/Linux have serious design shortcoming when it comes to proper and optimal support of bidirectional locales such as Persian. The main focus of this section is the most popular GUI toolkits, namely KDE (Qt) and GNOME (GTK+). These design shortcomings are the result of either not considering bidirectional layout in the original design (the situation in KDE/Qt) or being too simplistic as if it is just strict right-to-left instead of bidirectional (the situation in GTK+). The main shortcoming include that there is almost no explicit distinction between directionalities and concepts such as near and far as opposed to left and right. As a result, both of these environments lack the finer grain of control that is needed for proper bidirectional layout. In most cases there is no place for any additional data or metadata to help correctly identify proper orientation of each element or groups of elements in a bidirectional locale when the application is either localized or is in a Latin language. Enhancing these toolkits to better support bidirectional locales is not easy. It may result in some API changes and some new concepts being introduced. So, the situation is not expected to be improved in the short term. But since the proper behavior of a bidirectional locale such as Persian/Iran is impossible to achieve without the proper support of these environments, this issue is brought up here to at least help put the issue on the table for the designers and maintainers of these toolkits.

Some of the issues that currently exist are the result of the following issues:

-   There are no provisions for explicitly setting the direction of text or text-like widgets or groups of widgets.
-   Logical alignment (near side, far side, etc.) alongside physical alignment (left side, right side) is not distinguished and provided.
-   Left, right, previous and next and similar concepts are inappropriately named and defined in the existing APIs or are mixed up with each other. An example, consider the name of U+0028 Unicode character. It is named “Left Parenthesis” while it actually means opening parenthesis.
-   It is assumed that bidirectional locals are actually strictly mirrored and right-to-left.
-   There is no API for accessing and assigning directional behavior to individual elements or groups of elements.
-   There is also no way for the localizers to specify the correct directionality of each element.
-   Multi-calendar locales are not properly supported. The existing calendar services like the ones provided in glib do not support none-Gregorian calendars and having multiple active calendars.
-   The text input and editing environments incorrectly reflect the Unicode text ordering model instead of providing a true visual editing environment.

The above issues create different effects on a localized applications but the net result is the reduced usability of the applications localized for Persian vs. their Latin counterparts.

The above issues along with a more extensive list of the design issues in the existing versions of KDE/Qt and GNOME/GTK+ needs to be properly communicated with the developers and maintainers of the above environments so that acceptable solution can be found or developed as quickly as possible.
