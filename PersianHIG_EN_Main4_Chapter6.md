\
\

Chapter 1Summary of User Interface Widgets {.western dir="LTR"}
------------------------------------------

### 1.1.Introduction {.western dir="LTR"}

If you have jumped here straight from the table of the contents to get to the actual meat of this document, you are in the wrong place. The key information provided in this document is located in the chapters 2 through 4. This chapter is a small reference catalog of the key user interface widgets and their behavior in Persian/Iran locale. To understand this chapter, you should first read the previous chapters.

We have listed the main GUI widgets common in GUI toolkits without distinguishing their implementation in different GUI toolkits such as KDE and GNOME. Only notable differences among the implementation are mentioned.

Specialized and composite widgets are not presented individually. Instead we have mentioned general points regarding the proper localization of such widgets. The last section of this chapter mentions some of the shortcomings in the major GUI toolkits KDE (Qt) and GNOME (GTK).

\
\

### 1.2.Window {.western dir="LTR"}

The shape and control widget placement of the window depends on the active theme. The window in many themes does not require special localization. Themes that put window title in the left side are not suitable for Persian/Iran locale and should preferably mirror the title placement for Persian/Iran locale. A centered window label is recommended to avoid localization issue for right-to-left locales.

The other consideration about the window behavior is the window placement and stacking behavior. Since the most documents that are used in Persian/Iran locale are Persian documents with right-to-left layout, it is recommended the upper right corner of each document window being placed in a suitable and predictable place, regardless of the window width. So, it is better to arrange documents by stacking their top right corner (offsetting each new window a little to the left and down) when the Persian/Iran locale is active. The other solution is center placement of the windows which does not create a very good stacking if the windows and is not recommended.

### 1.3.Dialog Box {.western dir="LTR"}

Dialog boxes are special types of windows that usually have modal behavior and have a group of action buttons that dismiss the window (instead of using the window control widgets to close them). The localization issues of dialog boxes are similar to that of the regular windows. The special notes about button placement on the dialog boxes are discussed in the section for buttons.

### 1.4.Scrollbar {.western dir="LTR"}

The scrollbar is placed on the edge of the windows or on the edges of lists and tables to facilitate scrolling them to reveal the off-screen content. The issues to note for localizing them for Persian/Iran locale are:

Vertical scrollbar is placed on the right edge of the window or list/table in Latin locales. It is not mandatory to flip it to the left edge of the frames but this relocation is acceptable and is recommended is the environment is expected to be mostly localized in Persian with most of the documents being in Persian, too. The placement of vertical scrollbar does not follow the directionality of the active document. It should be always placed in the same consistent side of the frames regardless of whether a given application is actually localized or whether the document has the same direction as the active locale (which determines the placement of the scrollbar).

The default scroll thumb position for vertical scrollbar in Persian/Iran locale is the top of the scroll bar unless another scroll position is saved along with the document.

The horizontal scroll bar is universally placed on the bottom edge of the frame it is scrolling. The default scroll thumb position for horizontal scrollbar following the direction of the content being scrolled: If the content is right-to-left (the usual case in Persian/Iran locale) the scroll thumb is placed to the right, so that the right side of the content is exposed. If the content is left-to-right (even when Persian/Iran locale is active) the scroll thumb is placed to the left, so that the left side of the content is exposed.

### 1.5.Menu Bar {.western dir="LTR"}

A menu bar is usually placed on the top edge of the window. The menu bar is one of the user interface elements that are text oriented and is usually read like text. For this reason, the menu bar should be right aligned and be right-to-left for the Persian/Iran locale. It should have the same directionality and alignment for each locale regardless of the actual language of the active application or document. Mirroring of the menu bar should always be complete, a left aligned menu bar that is right-to-left, or a right aligned menu bar that is left-to-right is never acceptable. So, if there is some technical limitation is completely changing both alignment and direction of the menu bar for the Persian/Iran locale, it should not change partially.

The alignment and direction of the menu that is opened by selecting each menu bar item should have the same directionality and alignment as the menu bar itself.

If the menu titles in the menu bar include an icon, when the menu bar becomes right-to-left for the Persian/Iran locale, the icons should also be placed to the right of the menu title.

To highlight the keyboard equivalent for a menu title, it is not recommended to use single character underlining. Changing the color of the character or its background is recommended for the Persian/Iran locale.

### 1.6.Menu {.western dir="LTR"}

In Persian/Iran locale, menus are right aligned and right to left. A submenu marker appears at the left side of the menu and if the available space permits, the submenus open to the left of the parent menu. All of the menu items regardless of their actual language follow this rule. The menu title is also right aligned relative to the menu frame.

If the items in the menu bar include an icon or other mark, when the menu becomes right-to-left for the Persian/Iran locale, the icons and marks should also be placed to the right of the menu item.

To highlight the keyboard equivalent for a menu item, it is not recommended to use single character underlining. Changing the color of the character or its background is recommended for the Persian/Iran locale.

### 1.7.Tool Bar {.western dir="LTR"}

Toolbar may or may not follow the writing direction. For example, the placement of the items may depend on which corner of the screen it is placed on. Also, the button arrangement on the toolbar may follow a convention that does not follow the writing direction, such as the arrangement of the buttons that mimic audio/visual equipment. For this reason, it is recommended that GUI toolkits provide more options in determining the directionality and placement of the buttons on a toolbar. It is advised that they support such logical placements as the same as text direction or opposite text direction as well as physical ordering such as left-to-right or right-to-left. Also, a group of the buttons may have a given order while the other groups of the buttons follow a different order.

In the usual case, where there are no special placement requirements for the toolbar buttons, the direction and alignment of the toolbar should be similar to menu bar with similar considerations such as avoiding partial change of its directionality.

### 1.8.Static Text {.western dir="LTR"}

Static text is not usually stand alone in the user interface. It is usually part of a larger layout that uses other blocks of static text and other widgets. The proper placement of the static text relative to the other widgets in the logical group is determined by the actual language of those elements and not the directionality of the active Persian/Iran locale. So, even in Persian/Iran locale, if a related group of widgets that include static text (and are read like text) are in English, their placement should follow left-to-right placement. For example, if the static text is a label for another widget, the relative order of text and the widget should follow the proper display order of the language of the static text block. The following picture shows a partially localized screen in right-to-left locale, where the placements of all widgets follow the locale direction instead of the actual text direction:

![](PersianHIG-EN-Main45_html_768dd48b.png) **Wrong!**

The placement of the highlighted static text compared to the widgets they are labeling is incorrect.

Since as we mentioned it is not realistic to assume that all of the applications used in Persian/Iran locale will be fully localized, the behavior of the window layout in some of the existing toolkits (especially GTK) needs enhancements to properly support the cases where the actual language of the GUI does not follow the active system locale.

Since Persian fonts may have swashes and floating marks that fall outside of the nominal boundary of the characters, the clipping region around the static text should have some additional drawable margin around the nominal bounding box of the text. A margin of at least one or two pixels is recommended. Also it is recommended that putting static text elements too close to other elements be avoided for the same reason.

\
\

### 1.9.Text Field {.western dir="LTR"}

To properly support various scenarios that can arise in the Persian/Iran locale, the text fields should preferably provide the flexibility of setting the text direction and alignment on a per field basis.

Similar to the placements of static text, the relative placement and orientation of the text fields should follow the actual language used in them and the surrounding related elements such as the labeling static text. Refer to the figure in the previous section. If a set of related text fields are used for numeric data entry their placement may follow numeric (left-to-right) order.

Since Persian fonts may have swashes and floating marks that fall outside of the nominal boundary of the characters, the clipping region around the editable text should have some additional drawable margin around the nominal bounding box of the text. A margin of at least one or two pixels is recommended.

If the text field is a single-line field with automatic horizontal scrolling support, it should behave properly with right-to-left and bidirectional text. The easiest way to get a reasonable display in all cases while auto-scrolling is trying to keep the visual location of the text cursor in the middle of the field instead of close to a side.

The text input and editing behavior is expected to support the behavior described in Chapter 3.

### 1.10.Date/Time Field {.western dir="LTR"}

Date, Time and Date/Time fields usually represent numerically oriented information. The order of the date components despite each component being numeric (hence left-to-right) is right-to-left. As a result, if the date field is broken into component subfields, the correct subfield order would be right to left. On the other hand, time components are left-to-right, if the time field is broken into component subfields, the correct subfield order would be left to right. If there is a button next to field to provide a visual chooser window to aid in data entry, such a button may stay in the current right side location similar to Latin locales, but is preferred to be placed to the left side of the field or field group in Persian/Iran locale.

The display format and other information regarding date and time in Persian locale can be found in the following Persian document: [Locale’03]

نیازهای شرایط محلی برای زبان فارسی ایران

The data entry order of the time components in Persian/Iran locale are: Hour, minute, second.

The data entry order of the date components in Persian/Iran locale are: Day, month, year.

The default calendar used to interpret the date entry is *Hijri Shamsi* unless otherwise specified by the user. The date input according to any of the calendars used in Iran should be supported without requiring a change in the active calendar. This is achieved by appending a single character suffix to the date input. These suffix characters include: U+0634 ش for *Hijri Shamsi*, U+0642 ق for *Hijri Qamari* and U+0645 م for Gregorian (م is the first character of the word *Miladi* میلادی which is the name of the Gregorian calendar in Iran)

The localized applications should display a calendar suffix when displaying dates that are not expressed in the currently active default calendar.

If the expected default calendar in a date input field differs from the global default calendar, this should be clearly indicated in or around the date field (e.g. by a suffix label next to date field).

Naturally, the numeric components of the date and time fields are normally entered using the Persian digits (U+06F0 to U+06F9) which should be supported in addition to the ASCII digits.

### 1.11.Spinbox {.western dir="LTR"}

The spinbox is the small vertical rectangle that has two small up arrow and down arrow buttons used to rotate the numeric values in fields. It is always associated to an input field. In the Persian locale, the proper placement of this widget follows numeric direction, which means it appears to the right of the field that it affects.

Naturally, the numeric values controlled by this widget should support the Persian digits (U+06F0 to U+06F9) in addition to the normal ASCII digits.

### 1.12.Dropdown List {.western dir="LTR"}

In Persian/Iran Locale the direction and orientation of this widget defaults to right-to-left behavior, but follows the text direction of its actual content and the language of the related surrounding widgets such as its static text label. So, even if the locale is set to Persian/Iran, in software with English GUI, it should still appear the same as it does in a Latin locale. If the widget along with its label is read from right-to-left, then the list button should be placed on the left side and the text direction in the widget should be right-to-left. In this case, the selection list should be right aligned. The text label of this widget in this case will be placed to its right. The position of the scrollbar of the choice list of this widget always follows the global scrollbar placement strategy regardless of the direction of this widget.

### 1.13.Combo Box {.western dir="LTR"}

In Persian/Iran Locale the direction and orientation of this widget defaults to right-to-left behavior, but it follows the text direction of its actual content and the language of the related surrounding widgets such as its static text label. So, even if the locale is set to Persian/Iran, in software with English GUI, it should still appear the same as it does in a Latin locale. If the widget along with its label is read from right-to-left, then the list button should be placed on the left side and the text direction in the widget should be right-to-left. In this case, the selection list should be right aligned. The text label of this widget in this case will be placed to its right. The position of the scrollbar of the choice list of this widget always follows the global scrollbar placement strategy regardless of the direction of this widget.

The behavior of scrolling and text editing of the editable text in this widget is the same as the text field described in section 5.9.

### 1.14.Group Box {.western dir="LTR"}

A group box is used to visually group some related widgets together. A group box may contain a text title. Normally, the members of a group follow the same text directionality. This should be reflected in the alignment and placement of the widgets in a group box. The alignment and direction of the title of the group box also follows the same direction as the group. The direction of the group defaults to right-to-left in Persian/Iran locale but follows the actual language of group box title and the language dominate in the widgets inside the group box. The only part of a group box that is actually affected by its direction is the alignment and direction of the text of its title.

### 1.15.Tab Panel {.western dir="LTR"}

The order and placement of tab panels in Persian/Iran locale follows the global locale direction. It is also fully acceptable if its orientation follows the direction of the actual language of the GUI being displayed. When tab panel has right-to-left orientation, the tabs are either right aligned or center aligned (depending on theme) and the tabs are ordered from right-to-left (the first tab being the rightmost one). The overflow of the tabs is indicated on the left side of the tabs. If the tabs have icons in addition to title, the icon appears to the right of the title.

### 1.16.Button {.western dir="LTR"}

There are many different types of buttons with different combinations and arrangements of text and icons, or possibly sticky behavior. The localization of the button itself is similar to the other widgets. The text in the widget is usually centered and the directionality of the text follows the actual language of the text, defaulting to right-to-left for Persian/Iran locale. If an icon is displayed besides the text it may be placed both before and after the text if the text is centered. If the text is right aligned the suggested position of the icon is the right side of the text and if it is left aligned the suggested position is to the left of the text.

The relative position of the buttons is not closely coupled to the text direction of the GUI. For example, both a “Yes” then “No” and “No” then “Yes” arrangement of buttons is acceptable. The important point regarding the arrangement of the buttons is that they follow a consistent ordering scheme, based on their use and effect. So, the position of normal buttons should be the same in a given locale regardless of the actual language of the GUI being displayed. For example if you put “OK” button to the left of “Cancel” button in Persian/Iran locale, it should be placed in the same way whether the actual GUI is in Persian or English.

If a group of buttons is arranged in a way that they are expected to be read like text, their order should follow the text direction of their actual text. This is rarely the case, though.

If a group of buttons model a real world group of buttons (such as buttons in some electronic equipment) they should follow the arrangement of the real world group of buttons. In this case the text direction of the GUI is irrelevant.

### 1.17.Slider {.western dir="LTR"}

The slider widget is normally used to enter information that may be represented by numbers or numeric ratios. Slider is also used to simulate some real world objects such as similar sliders found on electronic equipment. This means that usually the orientation and direction of a horizontal slider has nothing to do with text direction and should not change depending on locale text direction. Generally, the side of a slider that represents the smaller amount is the left side. In Persian/Iran locale unlike most other widgets, the near end of slider is the left end and the far end of it is its right end.

### 1.18.Date Picker {.western dir="LTR"}

Date picker is a widget usually shaped like a tiny month calendar that permits the selection or display of a calendar date or multiple calendar dates. When this widget is used in Persian/Iran locale, its layout should conform to the description of the calendar layout in the following Persian document: [Locale’03]

نیازهای شرایط محلی برای زبان فارسی ایران

The default calendar shown by this widget is the *Hijri Shamsi* calendar, unless a different calendar is specified by the user. The calendar displayed by this widget should be selectable without the need for globally changing the default calendar. This can be achieved by putting a small button that is used to rotate the calendars and show the abbreviated calendar designator next to the displayed year. If this widget is enlarged so that the available space in each day cell permits, it is recommended that the widget shows multiple calendars simultaneously as it is the norm in Persian calendars.

### 1.19.Check Box {.western dir="LTR"}

Each checkbox is usually part of a larger logical group of widgets that consist of a heading or title (as static text or group box) and a set of checkboxes. It may also sometimes act as the label for a text field or other similar widget. The default direction and orientation of this widget in Persian/Iran locale is right-to-left, meaning that the box of the checkbox is placed to the right side and the text of the checkbox is right-to-left and right-aligned in its bounding box, This control is text oriented and its directionality is determined by the actual language of the group it belongs to. So, it should appear left-to-right in Persian locale if the actual language of the active GUI is English. But if the group language is Persian, even if one checkbox in the group has only English text, it should still appear right-to-left. A group of checkboxes are normally aligned so that the boxes of them are lined up.

The check mark image in the check box does not need mirroring when the checkbox is right-to-left.

### 1.20.Radio Button {.western dir="LTR"}

Each individual radio button is always part of a larger logical group of widgets that consist of a usually a heading or title (as static text or group box) and a set of radio buttons. Each radio button may also sometimes act as the label for a text field or other similar widget. The default direction and orientation of this widget in Persian/Iran locale is right-to-left, meaning that the circle of radio button is placed to the right side and the text of the radio button is right-to-left and right-aligned in its bounding box, This control is text oriented and its directionality is determined by the actual language of the group it belongs to. So, it should appear left-to-right in Persian locale if the actual language of the active GUI is English. But if the group language is Persian, even if one radio button in the group has only English text, it should still appear right-to-left. A group of radio buttons are normally aligned so that their buttons are lined up.

### 1.21.List Box {.western dir="LTR"}

In the Persian/Iran locale the direction and column order of this widget is right-to-left. This means that the direction of the text in each sell is right-to-left and the text in the cell is right-aligned. The order of the columns in this case is also right to left. The direction of the columns may be different based on the data type and the language of the content. In this case the column order usually stays right-to-left. The table itself may be left-to-right; even if it has some right-to-left text columns. Generally, it is best to have control over the directionality of table and its individual columns. So, a multi-column list box is a composite entity with multiple directionality attributes (directionality of each column, and the entire table). If the actual language of the active user interface is left-to-right, it is recommended that the list box stays left-to-right, even if the active locale is Persian/Iran.

It is also advised that the list box widget be flexible enough to let the developer (or localizer) set the alignment of individual columns and column headers in addition to the column directions.

### 1.22.Tree List Box {.western dir="LTR"}

This widget is very similar to a normal list box. The difference is that the first column (rightmost column if the table direction is right-to-left) is a tree with expandable nodes. If the image of the expand/collapse widget of the nodes is not symmetrical, it needs to be mirrored when the tree is right-to-left. In a tree list box, the direction of the first column (the tree column) and the entire table should always be the same. The other considerations are similar to the list box widget described in 5.21.

### 1.23.Text Ruler {.western dir="LTR"}

The text ruler is not a built-in widget in most of the GUI toolkits. This widget is commonly used in text editing and word processing applications when custom tab stops and paragraph margins are supported. It is typically custom built by the developers of the word processing applications. There are two types of text rulers that are commonly used. A text ruler is either page oriented (the zero point is on the edge of the paper) or column oriented (the zero point is on the edge of the active text column). Both rulers may be present in an application especially in page layout applications.

The zero point and placement of the page ruler depends on document properties including its direction, binding and whether it is double sided or single sided. This ruler should not change as the result of activating different paragraphs with different directions.

The zero point and placement of the column ruler usually follows the direction of the active paragraph. The zero point of this ruler is placed on the edge of the column that corresponds to the starting edge of the paragraph (the right edge in right-to-left text). If the direction of the active paragraph is changed, the direction of the ruler also changes and the layout control handles on the ruler also flip to indicate the new start and end of the paragraph. Also, the default alignment of the tab stops is flipped in this case.

It is recommended that word processing applications that support bidirectional layout, support both types of the rulers described above and also have the ability to show both of them simultaneously. This is illustrated in the following figure:

![](PersianHIG-EN-Main45_html_799d9f99.png)

The behavior of the text on tab stops should be visual and does not follow the stream of text across the tab boundary. So, the text should be first segmented into separate fields that fall on each tab stop and the Unicode bidirectional algorithm should be applied on each segment individually. The direction of the movement of the tab character is always determined by the paragraph direction and is never resolved with Unicode bidirectional algorithm.

In the Persian/Iran locale the default document and paragraph directions are right-to-left, so the default ruler direction for both types of rulers is right-to-left.

### 1.24.Progress Bar {.western dir="LTR"}

The progress bar is used to indicate the ratio of the progress of a certain task as a horizontal bar chart. In the Persian/Iran locale the direction of this widget follows the mathematical direction and is left-to-right just like it is in the Latin locales. In Persian/Iran locale unlike most other widgets, the near end of progress bar is the left end and the far end of it is its right end.

### 1.25.KDE Toolbox {.western dir="LTR"}

This widget is KDE specific. In the Persian/Iran locale it is recommended that this widget be mirrored and placed on the right side of the window. Although it is preferable to actually follow the direction of the language of the active application and stay left-to-right if the application is not localized in Persian.

### 1.26.Composite Widgets {.western dir="LTR"}

Designing composite widgets should take into consideration the different directional requirements and options that has been described in the previous chapter and this chapter. It should also be based on the principle of chapter 2 and properly support Persian text as described in chapter 3. It is advised that some flexibility is provided in the direction and positioning of its elements instead of having one fixed directional behavior for it.

### 1.27.Custom Widgets {.western dir="LTR"}

Application may create custom widgets from scratch. In this case the most difficult part of their creation is supporting proper bidirectional behavior for the widgets. For this reason, avoid creating custom widgets unless you have a very good reason for it. If you do create custom widgets pay close attention to its internationalization and bidirectional layout behavior.

### 1.28.Limitations in GNOME and KDE {.western dir="LTR"}

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

\
\

Appendix {.title-western dir="LTR" style="page-break-before: always"}
========

\
\

Definitions {.عنوان-پیوست-western dir="LTR" style="page-break-before: always"}
-----------

**GUI:**Graphical User Interface

**LTR:**Left-to-right

**RTL:**Right-to-left

**Principle:**A statement that is considered to be true without being proved. It is used here with a number to label and introduce the GUI design principles mentioned in this document.

**Rule:**A normative statement that is expected to be followed by each software localized for Persian.

**Guideline:**A none-normative statement that provide a possible solution or a recommendation for dealing with specific issues when localizing application for Persian/Iran locale.

**Internationalized Software:**Software that is designed to be localizable for any locale.

**Localized software:**Software (previously internationalized or not) that is localized for Persian/Iran locale.

**Domestic Software:**Software produced locally for the Persian/Iran locale.

**Persian Software:**Domestic software or Persian localized software.

\
\

References {.عنوان-پیوست-western dir="LTR" style="page-break-before: always"}
----------

[*Jentner/Nielsen*] ***The Anti-Mac Interface*** by *Don Jentner* and *Jakob Nielsen*, (Communications of the ACM, August 1996)

[*Raskin*] ***The Humane Interface*** by *Jeff Raskin*, (Addison-Wesley Professional; 1st edition, March 29, 2000, ISBN: 0201379376) and related project site at: H[T](http://humane.sourceforge.net/home/)[http://humane.sourceforge.net/home/T](http://humane.sourceforge.net/home/)H

[GNOME-HIG] ***GNOME Human Interface Guidelines*** available online at: H[T](http://developer.gnome.org/projects/gup/hig/)[http://developer.gnome.org/projects/gup/hig/T](http://developer.gnome.org/projects/gup/hig/)H

[KDE-SG] ***KDE Style Guide*** available online at: H[T](http://developer.kde.org/documentation/standards/kde/style/basics/)[http://developer.kde.org/documentation/standards/kde/style/basics/T](http://developer.kde.org/documentation/standards/kde/style/basics/)H

[KDE-UIG] ***KDE User Interface Guidelines*** available online at: H[T](http://developer.kde.org/documentation/design/ui/)[http://developer.kde.org/documentation/design/ui/T](http://developer.kde.org/documentation/design/ui/)H

[Java1] ***Java******™******Look and Feel Design Guidelines, second edition*** by *Sun Microsystems, Inc*. available online at: H[T](http://java.sun.com/products/jlf/ed2/book/)[http://java.sun.com/products/jlf/ed2/book/T](http://java.sun.com/products/jlf/ed2/book/)H

[Java2] ***Java******™******Look and Feel Design Guidelines: Advanced Topics*** by *Sun Microsystems, Inc.* available online at: H[T](http://java.sun.com/products/jlf/at/book/)[http://java.sun.com/products/jlf/at/book/T](http://java.sun.com/products/jlf/at/book/)H

[Apple-HIG] ***Apple Human Interface Guidelines*** by *Apple Computer Inc.* available online at: H[T](http://developer.apple.com/documentation/UserExperience/Conceptual/OSXHIGuidelines/index.html)[http://developer.apple.com/documentation/UserExperience/Conceptual/OSXHIGuidelines/index.htmlT](http://developer.apple.com/documentation/UserExperience/Conceptual/OSXHIGuidelines/index.html)H

[Unicode] ***Unicode How To*** by *Bruno Haible* available online at: H[T](http://www.linux.com/howtos/Unicode-HOWTO.shtml)[http://www.linux.com/howtos/Unicode-HOWTO.shtmlT](http://www.linux.com/howtos/Unicode-HOWTO.shtml)H

[Tognazzini’95] ***Tog on Software Design*** by *Bruce Tognazzini* (Addison-Wesley Professional, 1995)

[Cooper’03] ***About Face 2.0: The Essentials of Interaction Design*** by *Alan Cooper* and *Robert M. Riemann* (Wiley, 2003)

[Norman’02] ***The Design of Everyday Things*** by *Donald A. Norman* (Basic Books, 2002)

[Nielsen’99] ***Designing Web Usability: The Practice of Simplicity*** by *Jakob Nielsen* (New Riders Press, 1999)

[ISIRI-6219] Iranian National Standard ISIRI-6219 “Exchange and Display of Persian Information Using Unicode Standard” 2002, available online in Persian at H[T](http://www.isiri.ir/)[www.isiri.irT](http://www.isiri.ir/)H

[ISIRI-2901] Iranian National Standard ISIRI-2901 “Placement of Persian Characters on Computer Keyboards” 1994, available online in Persian at H[T](http://www.isiri.ir/)[www.isiri.irT](http://www.isiri.ir/)H

[PersianWriting] “Official Guide to Writing in Persian” (دستور خطَ فارسی) by Iranian Academy of Persian Language and Script. Available online in Persian at: H[T](http://www.persianacademy.ir/)[http://www.persianacademy.irT](http://www.persianacademy.ir/)H

[Locale’03] The document titled “نیازهای شرایط محلی برای زبان فارسی ایران” from the Iranian National GNU/Linux Project, 2003. Available online at: H[T](http://projects.farsilinux.org/projects/loosesearch/)[http://projects.farsilinux.org/projects/loosesearch/T](http://projects.farsilinux.org/projects/loosesearch/)H

[Sort’03] The document titled “ترتیب‌بندی و مرتب‌سازی برای زبان فارسی ایران” from the Iranian National GNU/Linux Project, 2003. Available online at: H[T](http://projects.farsilinux.org/projects/loosesearch/)[http://projects.farsilinux.org/projects/loosesearch/T](http://projects.farsilinux.org/projects/loosesearch/)H

[Search’03] The document titled “جستجوی تقریبی برای زبان فارسی ایران” from the Iranian National GNU/Linux Project, 2003. Available online at: H[T](http://projects.farsilinux.org/projects/loosesearch/)[http://projects.farsilinux.org/projects/loosesearch/T](http://projects.farsilinux.org/projects/loosesearch/)H

[OpenType’03] The document titled “توصیف قلم اپن‌تایپ مرجع برای زبان فارسی” from the Iranian National GNU/Linux Project, 2003. Available online at: \
H[T](http://projects.farsilinux.org/projects/opentype/)[http://projects.farsilinux.org/projects/opentype/T](http://projects.farsilinux.org/projects/opentype/)H

[Calendar’03] The reference implementation of Official Iranian Calendars. Part of Iranian National GNU/Linux Project, 2003. Available online at: H[T](http://projects.farsilinux.org/projects/persian-cal/)[http://projects.farsilinux.org/projects/persian-cal/T](http://projects.farsilinux.org/projects/persian-cal/)H

[OOo-L10N] ***OpenOffice.org Localization Project*** at: H[T](http://l10n.openoffice.org/)[http://l10n.openoffice.orgT](http://l10n.openoffice.org/)H

[Mozilla-L10N] ***Mozilla Localization Project*** at: H[T](http://www.mozilla.org/projects/l10n/)[http://www.mozilla.org/projects/l10n/T](http://www.mozilla.org/projects/l10n/)H

[KDE-i18n] ***KDE Internationalization Site*** at: H[T](http://i18n.kde.org/)[http://i18n.kde.orgT](http://i18n.kde.org/)H

[Qt-i18n] ***Internationalization with Qt*** available online at:******H[Thttp://doc.trolltech.com/3.3/i18n.htmlT](http://doc.trolltech.com/3.3/i18n.html)H

[GTKmm-i18n] ***GTKmm Tutorial, Chapter 20: Internationalization and Localization*** by *Murray Cumming* and *Ole Laursen* available online at: H[T](http://www.gtkmm.org/docs/gtkmm-2.4/docs/tutorial/html/ch20.html)[http://www.gtkmm.org/docs/gtkmm-2.4/docs/tutorial/html/ch20.htmlT](http://www.gtkmm.org/docs/gtkmm-2.4/docs/tutorial/html/ch20.html)H

[Pango] ***Pango Design: The Layout Pipeline*** by *Owen Taylor* available online at: H[T](http://www.pango.org/layout.shtml)[http://www.pango.org/layout.shtmlT](http://www.pango.org/layout.shtml)H

[GNOME-i18n] ***Internationalizing GNOME applications*** by *Malcolm Tredinnick* available online at: H[T](http://www.gnome.org/~malcolm/i18n/)[http://www.gnome.org/\~malcolm/i18n/T](http://www.gnome.org/~malcolm/i18n/)H

[GNOME-L10N] ***GNOME L10N Guidelines for Developers*** by *Christian Rose* available online at: H[T](http://developer.gnome.org/doc/tutorials/gnome-i18n/developer.html)[http://developer.gnome.org/doc/tutorials/gnome-i18n/developer.htmlT](http://developer.gnome.org/doc/tutorials/gnome-i18n/developer.html)H

[LSB] ***Linux Standard Base*** project available online at: H[T](http://www.linuxbase.org/)[http://www.linuxbase.org/T](http://www.linuxbase.org/)H

[CCSpec] ***Cursor Conventions Specification*** available online at: H[T](http://freedesktop.org/wiki/Standards_2fcursor_2dspec)[http://freedesktop.org/wiki/Standards\_2fcursor\_2dspecT](http://freedesktop.org/wiki/Standards_2fcursor_2dspec)H

[TSUSpec] ***The Single UNIX® Specification, Version 3*** available online at: H[T](http://www.unix.org/online.html)[http://www.unix.org/online.htmlT](http://www.unix.org/online.html)H

[ICU-UG] ***ICU User Guide*** by *IBM* available online at: H[T](http://icu.sourceforge.net/userguide/)[http://icu.sourceforge.net/userguide/T](http://icu.sourceforge.net/userguide/)H

[Fitts’] ***Fitts’ Law*** information about this law is available online at: H[T](http://en.wikipedia.org/wiki/Fitts'_law)[http://en.wikipedia.org/wiki/Fitts’\_lawT](http://en.wikipedia.org/wiki/Fitts'_law)H

[OpenType] ***The OpenType Standard 1.4*** by *Microsoft Corporation* available online at: H[T](http://www.microsoft.com/typography/otspec/)[http://www.microsoft.com/typography/otspec/T](http://www.microsoft.com/typography/otspec/)H

\
\

\
\

\
\

GNU Free Documentation License {.عنوان-پیوست-western dir="LTR" style="page-break-before: always"}
------------------------------

\
\

**GNU Free Documentation License**

Version 1.2, November 2002

Copyright (C) 2000, 2001, 2002 Free Software Foundation, Inc.

59 Temple Place, Suite 330, Boston, MA 02111-1307 USA

Everyone is permitted to copy and distribute verbatim copies

of this license document, but changing it is not allowed.

**0. PREAMBLE**

The purpose of this License is to make a manual, textbook, or other functional and useful document “free” in the sense of freedom: to assure everyone the effective freedom to copy and redistribute it, with or without modifying it, either commercially or noncommercially. Secondarily, this License preserves for the author and publisher a way to get credit for their work, while not being considered responsible for modifications made by others.

This License is a kind of “copyleft”, which means that derivative works of the document must themselves be free in the same sense. It complements the GNU General Public License, which is a copyleft license designed for free software.

We have designed this License in order to use it for manuals for free software, because free software needs free documentation: a free program should come with manuals providing the same freedoms that the software does. But this License is not limited to software manuals; it can be used for any textual work, regardless of subject matter or whether it is published as a printed book. We recommend this License principally for works whose purpose is instruction or reference.

**1. APPLICABILITY AND DEFINITIONS**

This License applies to any manual or other work, in any medium, that contains a notice placed by the copyright holder saying it can be distributed under the terms of this License. Such a notice grants a world-wide, royalty-free license, unlimited in duration, to use that work under the conditions stated herein. The “Document”, below, refers to any such manual or work. Any member of the public is a licensee, and is addressed as “you”. You accept the license if you copy, modify or distribute the work in a way requiring permission under copyright law.

A “Modified Version” of the Document means any work containing the Document or a portion of it, either copied verbatim, or with modifications and/or translated into another language.

A “Secondary Section” is a named appendix or a front-matter section of the Document that deals exclusively with the relationship of the publishers or authors of the Document to the Document’s overall subject (or to related matters) and contains nothing that could fall directly within that overall subject. (Thus, if the Document is in part a textbook of mathematics, a Secondary Section may not explain any mathematics.) The relationship could be a matter of historical connection with the subject or with related matters, or of legal, commercial, philosophical, ethical or political position regarding them.

The “Invariant Sections” are certain Secondary Sections whose titles are designated, as being those of Invariant Sections, in the notice that says that the Document is released under this License. If a section does not fit the above definition of Secondary then it is not allowed to be designated as Invariant. The Document may contain zero Invariant Sections. If the Document does not identify any Invariant Sections then there are none.

The “Cover Texts” are certain short passages of text that are listed, as Front-Cover Texts or Back-Cover Texts, in the notice that says that the Document is released under this License. A Front-Cover Text may be at most 5 words, and a Back-Cover Text may be at most 25 words.

A “Transparent” copy of the Document means a machine-readable copy, represented in a format whose specification is available to the general public, that is suitable for revising the document straightforwardly with generic text editors or (for images composed of pixels) generic paint programs or (for drawings) some widely available drawing editor, and that is suitable for input to text formatters or for automatic translation to a variety of formats suitable for input to text formatters. A copy made in an otherwise Transparent file format whose markup, or absence of markup, has been arranged to thwart or discourage subsequent modification by readers is not Transparent. An image format is not Transparent if used for any substantial amount of text. A copy that is not “Transparent” is called “Opaque”.

Examples of suitable formats for Transparent copies include plain ASCII without markup, Texinfo input format, LaTeX input format, SGML or XML using a publicly available DTD, and standard-conforming simple HTML, PostScript or PDF designed for human modification. Examples of transparent image formats include PNG, XCF and JPG. Opaque formats include proprietary formats that can be read and edited only by proprietary word processors, SGML or XML for which the DTD and/or processing tools are not generally available, and the machine-generated HTML, PostScript or PDF produced by some word processors for output purposes only.

The “Title Page” means, for a printed book, the title page itself, plus such following pages as are needed to hold, legibly, the material this License requires to appear in the title page. For works in formats which do not have any title page as such, “Title Page” means the text near the most prominent appearance of the work’s title, preceding the beginning of the body of the text.

A section “Entitled XYZ” means a named subunit of the Document whose title either is precisely XYZ or contains XYZ in parentheses following text that translates XYZ in another language. (Here XYZ stands for a specific section name mentioned below, such as “Acknowledgements”, “Dedications”, “Endorsements”, or “History”.) To “Preserve the Title” of such a section when you modify the Document means that it remains a section “Entitled XYZ” according to this definition.

The Document may include Warranty Disclaimers next to the notice which states that this License applies to the Document. These Warranty Disclaimers are considered to be included by reference in this License, but only as regards disclaiming warranties: any other implication that these Warranty Disclaimers may have is void and has no effect on the meaning of this License.

**2. VERBATIM COPYING**

You may copy and distribute the Document in any medium, either commercially or noncommercially, provided that this License, the copyright notices, and the license notice saying this License applies to the Document are reproduced in all copies, and that you add no other conditions whatsoever to those of this License. You may not use technical measures to obstruct or control the reading or further copying of the copies you make or distribute. However, you may accept compensation in exchange for copies. If you distribute a large enough number of copies you must also follow the conditions in section 3.

You may also lend copies, under the same conditions stated above, and you may publicly display copies.

**3. COPYING IN QUANTITY**

If you publish printed copies (or copies in media that commonly have printed covers) of the Document, numbering more than 100, and the Document’s license notice requires Cover Texts, you must enclose the copies in covers that carry, clearly and legibly, all these Cover Texts: Front-Cover Texts on the front cover, and Back-Cover Texts on the back cover. Both covers must also clearly and legibly identify you as the publisher of these copies. The front cover must present the full title with all words of the title equally prominent and visible. You may add other material on the covers in addition. Copying with changes limited to the covers, as long as they preserve the title of the Document and satisfy these conditions, can be treated as verbatim copying in other respects.

If the required texts for either cover are too voluminous to fit legibly, you should put the first ones listed (as many as fit reasonably) on the actual cover, and continue the rest onto adjacent pages.

If you publish or distribute Opaque copies of the Document numbering more than 100, you must either include a machine-readable Transparent copy along with each Opaque copy, or state in or with each Opaque copy a computer-network location from which the general network-using public has access to download using public-standard network protocols a complete Transparent copy of the Document, free of added material. If you use the latter option, you must take reasonably prudent steps, when you begin distribution of Opaque copies in quantity, to ensure that this Transparent copy will remain thus accessible at the stated location until at least one year after the last time you distribute an Opaque copy (directly or through your agents or retailers) of that edition to the public.

It is requested, but not required, that you contact the authors of the Document well before redistributing any large number of copies, to give them a chance to provide you with an updated version of the Document.

**4. MODIFICATIONS**

You may copy and distribute a Modified Version of the Document under the conditions of sections 2 and 3 above, provided that you release the Modified Version under precisely this License, with the Modified Version filling the role of the Document, thus licensing distribution and modification of the Modified Version to whoever possesses a copy of it. In addition, you must do these things in the Modified Version:

A. Use in the Title Page (and on the covers, if any) a title distinct from that of the Document, and from those of previous versions (which should, if there were any, be listed in the History section of the Document). You may use the same title as a previous version if the original publisher of that version gives permission.

B. List on the Title Page, as authors, one or more persons or entities responsible for authorship of the modifications in the Modified Version, together with at least five of the principal authors of the Document (all of its principal authors, if it has fewer than five), unless they release you from this requirement.

C. State on the Title page the name of the publisher of the Modified Version, as the publisher.

D. Preserve all the copyright notices of the Document.

E. Add an appropriate copyright notice for your modifications adjacent to the other copyright notices.

F. Include, immediately after the copyright notices, a license notice giving the public permission to use the Modified Version under the terms of this License, in the form shown in the Addendum below.

G. Preserve in that license notice the full lists of Invariant Sections and required Cover Texts given in the Document’s license notice.

H. Include an unaltered copy of this License.

I. Preserve the section Entitled “History”, Preserve its Title, and add to it an item stating at least the title, year, new authors, and publisher of the Modified Version as given on the Title Page. If there is no section Entitled “History” in the Document, create one stating the title, year, authors, and publisher of the Document as given on its Title Page, then add an item describing the Modified Version as stated in the previous sentence.

J. Preserve the network location, if any, given in the Document for public access to a Transparent copy of the Document, and likewise the network locations given in the Document for previous versions it was based on. These may be placed in the “History” section. You may omit a network location for a work that was published at least four years before the Document itself, or if the original publisher of the version it refers to gives permission.

K. For any section Entitled “Acknowledgements” or “Dedications”, Preserve the Title of the section, and preserve in the section all the substance and tone of each of the contributor acknowledgements and/or dedications given therein.

L. Preserve all the Invariant Sections of the Document, unaltered in their text and in their titles. Section numbers or the equivalent are not considered part of the section titles.

M. Delete any section Entitled “Endorsements”. Such a section may not be included in the Modified Version.

N. Do not retitle any existing section to be Entitled “Endorsements” or to conflict in title with any Invariant Section.

O. Preserve any Warranty Disclaimers.

If the Modified Version includes new front-matter sections or appendices that qualify as Secondary Sections and contain no material copied from the Document, you may at your option designate some or all of these sections as invariant. To do this, add their titles to the list of Invariant Sections in the Modified Version’s license notice. These titles must be distinct from any other section titles.

You may add a section Entitled “Endorsements”, provided it contains nothing but endorsements of your Modified Version by various parties–for example, statements of peer review or that the text has been approved by an organization as the authoritative definition of a standard.

You may add a passage of up to five words as a Front-Cover Text, and a passage of up to 25 words as a Back-Cover Text, to the end of the list of Cover Texts in the Modified Version. Only one passage of Front-Cover Text and one of Back-Cover Text may be added by (or through arrangements made by) any one entity. If the Document already includes a cover text for the same cover, previously added by you or by arrangement made by the same entity you are acting on behalf of, you may not add another; but you may replace the old one, on explicit permission from the previous publisher that added the old one.

The author(s) and publisher(s) of the Document do not by this License give permission to use their names for publicity for or to assert or imply endorsement of any Modified Version.

**5. COMBINING DOCUMENTS**

You may combine the Document with other documents released under this License, under the terms defined in section 4 above for modified versions, provided that you include in the combination all of the Invariant Sections of all of the original documents, unmodified, and list them all as Invariant Sections of your combined work in its license notice, and that you preserve all their Warranty Disclaimers.

The combined work need only contain one copy of this License, and multiple identical Invariant Sections may be replaced with a single copy. If there are multiple Invariant Sections with the same name but different contents, make the title of each such section unique by adding at the end of it, in parentheses, the name of the original author or publisher of that section if known, or else a unique number. Make the same adjustment to the section titles in the list of Invariant Sections in the license notice of the combined work.

In the combination, you must combine any sections Entitled “History” in the various original documents, forming one section Entitled “History”; likewise combine any sections Entitled “Acknowledgements”, and any sections Entitled “Dedications”. You must delete all sections Entitled “Endorsements.”

**6. COLLECTIONS OF DOCUMENTS**

You may make a collection consisting of the Document and other documents released under this License, and replace the individual copies of this License in the various documents with a single copy that is included in the collection, provided that you follow the rules of this License for verbatim copying of each of the documents in all other respects.

You may extract a single document from such a collection, and distribute it individually under this License, provided you insert a copy of this License into the extracted document, and follow this License in all other respects regarding verbatim copying of that document.

**7. AGGREGATION WITH INDEPENDENT WORKS**

A compilation of the Document or its derivatives with other separate and independent documents or works, in or on a volume of a storage or distribution medium, is called an “aggregate” if the copyright resulting from the compilation is not used to limit the legal rights of the compilation’s users beyond what the individual works permit. When the Document is included in an aggregate, this License does not apply to the other works in the aggregate which are not themselves derivative works of the Document.

If the Cover Text requirement of section 3 is applicable to these copies of the Document, then if the Document is less than one half of the entire aggregate, the Document’s Cover Texts may be placed on covers that bracket the Document within the aggregate, or the electronic equivalent of covers if the Document is in electronic form. Otherwise they must appear on printed covers that bracket the whole aggregate.

**8. TRANSLATION**

Translation is considered a kind of modification, so you may distribute translations of the Document under the terms of section 4. Replacing Invariant Sections with translations requires special permission from their copyright holders, but you may include translations of some or all Invariant Sections in addition to the original versions of these Invariant Sections. You may include a translation of this License, and all the license notices in the Document, and any Warranty Disclaimers, provided that you also include the original English version of this License and the original versions of those notices and disclaimers. In case of a disagreement between the translation and the original version of this License or a notice or disclaimer, the original version will prevail.

If a section in the Document is Entitled “Acknowledgements”, “Dedications”, or “History”, the requirement (section 4) to Preserve its Title (section 1) will typically require changing the actual title.

**9. TERMINATION**

You may not copy, modify, sublicense, or distribute the Document except as expressly provided for under this License. Any other attempt to copy, modify, sublicense or distribute the Document is void, and will automatically terminate your rights under this License. However, parties who have received copies, or rights, from you under this License will not have their licenses terminated so long as such parties remain in full compliance.

**10. FUTURE REVISIONS OF THIS LICENSE**

The Free Software Foundation may publish new, revised versions of the GNU Free Documentation License from time to time. Such new versions will be similar in spirit to the present version, but may differ in detail to address new problems or concerns. See http://www.gnu.org/copyleft/.

Each version of the License is given a distinguishing version number. If the Document specifies that a particular numbered version of this License “or any later version” applies to it, you have the option of following the terms and conditions either of that specified version or of any later version that has been published (not as a draft) by the Free Software Foundation. If the Document does not specify a version number of this License, you may choose any version ever published (not as a draft) by the Free Software Foundation.

![](PersianHIG-EN-Main45_html_m63a7d47d.png)

\
\

