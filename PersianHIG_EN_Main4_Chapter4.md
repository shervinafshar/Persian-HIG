Chapter 4 - The Visual Elements in the GUI
------------------------------------------

This chapter discusses the visual elements in the GUI and guidelines concerning them for a Persian GUI application. The visual elements include all the images, icons, symbols, text, lines and boxes and the layout and composition of these elements to make the visual appearance of the GUI.

Printed output plays an important role in many software applications and many visual elements in the GUI are modeled after printed page, some parts of the GUI deal with the printed page or visualize it. For this reason, we will first discuss the paper documents and their specifics in Iran/Persian locale.

### 4.1. Paper Documents

Printed output is varied. It could be a single sheet of paper, a continuous roll of paper, thick double sided book with hundreds of pages, a large multi-sheet CAD drawing or a giant color poster. In this discussion we will focus on sheet by sheet print of normal size, whose usage is the most common.

Multi-page documents have different types: It could be unbound sheet-by-sheet document or a bound booklet. They may be single sided or double sided. In the case of a booklet, it could be bound from the side or from the top.

On the other hand the document may be Persian, Latin or bi-lingual Persian/Latin. For example, an international contract could have the Persian and English translations side by side either on adjacent columns or opposing pages. A bi-lingual journal may have a Persian half and a Latin half.

If a printed document is intended to be bound from the side, the proper side for binding depends on the direction of the primary language of the document. This is called the document direction. In a Persian (RTL) document, the binding is on the right side of the booklet. In a Latin (LTR) document, the binding is on the left side of the booklet. When you open a double-sided Persian booklet (printed on both sides on the paper) the right page has an even number and the left page has an odd number. This means that in the Persian book, the first page is the left page. In a Latin book the right page has an odd number and the left page has an even number. This means that in the Latin book, the first page is the right page.

If the page contains multiple columns, Persian columns are placed from right to left, while Latin columns from left to right. Considering the above points the properties of a bi-lingual document also becomes apparent. If a bi-lingual document has two separate Latin and Persian section, each will start at one side of booklet and continue towards the middle, just as if we have pasted the back cover of two booklets (one Persian and the other Latin) to each other. In this case, the page numbers start at one on both sides and grow toward the middle.

If we need to place Persian and Latin sections side by side, then there are two solutions. First solution is using two column Pages. The left side column contains Latin text and the right side column contains Persian text. The other method would be putting Persian and Latin in two facing pages. The left side page would contain Latin and right side page would contain Persian. In both of these cases we need to first assume a direction for the entire booklet and number and arrange the pages accordingly. So, we either consider the document Latin and left bind it or consider Persian and right bind it.

A software that wants to properly support working with a mix of Persian and Latin documents (including bi-lingual documents) needs specific functionality to address the requirements of Persian, Latin and Persian/Latin documents. To support both Persian and Latin, the software needs to properly support both right and left binding of the document. It means that it should be able to both accept the first page as being the left page and as the right page. Beyond the binding it also should support both left-to-right and right-to-left column arrangement. There are currently a few applications that provide this support. The support of bi-lingual software of the side-by-side type, some extra functionality is used which is not fully supported in any of the existing documents. The required functionality is first the ability to work with two independent text streams. This capability exists in normal page layout software. The other is linking the two streams so that the equivalent sections and paragraphs stay in front of each other by adjusting the line and paragraph spacing. This second capability is not provided by any well known software.

In the last part of this section we will look at the various dimensions and metrics of the page that are used in Persian/Iran locale:

The first point to consider is the starting point (zero point) of the measurement ruler. In a normal document where the key factor is the text and the text consists of a single column, the usual place for the zero point of the horizontal ruler is the natural starting point of the text. This is also called a column ruler, since it measures the width of column. When the page layout is the key factor and there are multiple columns, the zero point is usually placed at the upper corner of the page. If there are facing pages, the zero point will be on the binding side of each page. If the page is single sided then the zero point usually is at the side of the natural starting point of writing. This type of ruler is also called the page ruler. For the proper support of bi-directional text, it is recommended that both types of rulers be supported.

The important measurements in a Persian document are paper dimensions, column width, column spacing, margins at four sides of paper, first line indent or out-dent of the paragraph, and paragraph indents within the column for quoted paragraphs. These dimensions are shown in the figure below:

![](PersianHIG-EN-Main44_html_487d4b2d.gif)

There is one point that needs to be considered when naming the above dimension: As you can see left and right are never mentioned and the dimensions are expressed compare relative to natural text starting point as inner and outer margins and near and far indents. Depending on binding side and document direction, each of the inner/near or outer/far dimensions may be located at left or right.

**Rule 1: To specify horizontal dimensions and measurements of page, use inner and outer (relative to binding edge) or near and far (relative to the natural starting point based on writing direction) instead of using left and right.**

**Rule 2: Internationalized software that deals with printed output should be able to handle booklet binding from either top, left or right sides. They should be able to handle both cases of the right page being the first page and the left page being the first page.**

**Rule 3: Internationalized software that support multi-column text should support both left-to-right and right-to-left column order.**

There is another issue when we have paragraphs of different directions in the same column of text. The issue is related to deciding the zero point of the column ruler. As we mentioned, the zero point depends on the direction of the text in the column. When direction of the text changes, the ruler zero point will flip to the opposite edge of the column. This may not be desirable for adjusting the relative position of the RTL vs. LTR paragraphs of text. For this reason, it is recommended that a page ruler is also used whose direction remains the same as paragraphs change direction. Note that the zero point of the page ruler depends on binding and document direction which are global.

The following figure shows an example of the column and page rulers in a right-to-left document when the paragraph containing the cursor is also right-to-left.

![](PersianHIG-EN-Main44_html_m637f3444.png)

The following figure shows an example of the column and page rulers in a right-to-left document when the paragraph containing the cursor is left-to-right.

![](PersianHIG-EN-Main44_html_799d9f99.png)

**Guideline 1: If you show only one ruler, decide the direction of the ruler based on document or section direction and not the paragraph direction. If you display two rulers one for column and another for page, then you may flip the zero point of the column ruler according to the direction of the active paragraph.**

As you can see multiple directionalities can be involved in a single document: Document direction (or the binding side), section[1][1] direction (indicating column layout direction), paragraph direction and string (text run) direction. All of the above directions should be distinctly visualized in the GUI and should be easy to specify and change. For example, putting a thicker edge on the binding side of the paper can help user realize the binding direction.

The default direction for all of the above directions in the Persian/Iran locale is right-to-left.

**Guideline 2: In addition to the direction of the text run and paragraph, the other directions of the document including column and binding directions should be easy to determine and change.**

**Guideline 3: Default section (column) direction is the same as document (binding) direction and the default paragraph direction is the same as section direction.**

   [1]: A section is a part of document where the layout is similar (same column setup and header/footer, etc).

### 4.2. Icons and Images

Extensive use of images, symbols and icons is one of the characteristics of graphical user interfaces. The correct use of these elements helps in making the interface easier to understand and more elegant. Some developers tend to think that images, symbols and icons are automatically international and do not need localization, but this is not always the case.

It is recommended that the images, symbols and icons are designed to be international and not to require localization. But this can be sometimes a none-trivial task. Internationalized images have the following properties:

Avoid using figures of various parts of human body or gestures. Some cultures find certain images offending. The use of human figure in a similar fashion that is used in international symbols (such as traffic symbols) is acceptable. For example, a thumbs up is considered offensive in Persian/Iran locale.

Avoid using the shape of items that have different shapes in different places. For example, the shape of a mailbox is different in different places, but the shape of envelope, stamp and even mail stamp is more universal.

This category of internationalization concern for images is not specific to Persian/Iran locale and is discussed in the general documents dealing with internationalization. For example see [KDE-i18n] or [GNOME-i18n]. So, we will continue the discussion with some bi-directional specific concerns:

There is some misunderstanding as whether writing direction does or does not affect an image. Sometimes an image needs horizontal mirroring but this is not obvious. Sometimes an image seems to need mirror but it does not. An example where mirroring is needed is a side facing user icon. Since potential text should appear in front of the user instead of behind his back, the face should be kept to always look towards the inside and towards the text. This means that in most cases you will need to mirror the image to look the other way for Persian. To make such a user icon international you can change it so that it faces the user instead of looking to the side. Another example is a none-symmetric shape that does not need mirroring for right-to-left writing direction. Although a checkmark ![](PersianHIG-EN-Main44_html_m5a749d7d.png) is not symmetric, it does not need mirroring. A mirrored checkmark look unfamiliar and is actually left handed, instead of being right-to-left. Another example is the playback symbol![](PersianHIG-EN-Main44_html_48e26644.png). Although playback symbol clearly point from left-to-right, it should not be mirrored, because the mirrored symbol does not mean normal play. If anything, it means reverse play which is a different meaning.

There is a tricky issue when we use symbols to indicate the concept of previous and next. The most commonly used symbol for *next* is a right pointing arrow → and the symbol for *previous* is a left pointing arrow ←. These symbols can be confusing in a bi-directional environment when they are associated with text oriented content. Mirroring these symbols in a Persian localized environment is not the solution.

Consider the previous and next buttons in a web browser application. The arrow directions do not correspond to the application localization, but to the document being viewed. The same window (whether localized for Persian or not) may show both left-to-right and right-to-left documents. Flipping the direction of the arrows based on document direction disassociates the concept from a well defined symbol and is not an option. Unlike the playback symbol discussed earlier which has a very old and none-computer related counterpart that is familiar to practically everyone in the world, the arrow symbols for previous and next do not share the same universal recognition. For this reason, the use of horizontal arrows to indicate the concept of previous or next is not recommended.

The solution would be either using vertical arrows (vertical direction of the text is almost universally top to bottom) or avoid symbols altogether and rely on the text instead. The other acceptable method is using the rewind ![](PersianHIG-EN-Main44_html_m75837594.png) and fast forward ![](PersianHIG-EN-Main44_html_m1ca15d1c.png)symbols from audio/visual equipment which enjoy almost the same universal recognition as the playback symbol. If that is the case, the rewind should stay to the left of the fast forward button to maintain the integrity of the model it is following.

**Guideline 4: Avoid using horizontal arrows to symbolize the concepts of previous and next. Try avoiding a symbol and using text, instead.**

**Using vertical arrows and using symbols for this purpose is permitted. Also using rewind ![](PersianHIG-EN-Main44_html_m75837594.png) and fast forward ![](PersianHIG-EN-Main44_html_m1ca15d1c.png) in audio visual equipment is permitted for this purpose, provided the original ordering of the symbols is maintained.**

### 4.3. Direction and Placement of Visual Elements

The overall rules for composing the elements in the user interface are similar to the page layout rules for the paper documents. One difference is having much less white space because of the limited screen space. The same rules also apply in a right-to-left environment. The main difference in a right-to-left environment is the mirroring that occurs in the placement of text related elements as the result of writing direction. Items that are not related to writing direction may not need any change. One method to improve the layout adaptability for right-to-left environments is using a vertically symmetric design by using center aligned elements or providing some widgets at both sides of the window such as a resize handle.

Adapting a left-to-right layout for a right-to-left locale isn’t as easy as some developers think. Some developers think that vertically flipping (mirroring) a left-to-right layout will always create the correct right-to-left layout. The simple mirroring is indeed the correct answer for most of the cases, but not all. The reason is that not all placements follow text direction. Some placements are more a matter of choice than necessity. For example, a page header or footer may be left, right or center justified without any of the alignments being wrong. Also, there are places where the order is not really that important. For example, when we have a multiple choice question in a questionnaire, the order of the suggested answers is usually not important, except for a choice like “neither” which should always be last. But there are other cases where order and direction *is* important, but the correct direction does not follow text direction. This last case is the one that causes problems.

To better understand the reality of a bidirectional environment you should consider the fact that in a Latin environment, there is only one direction which is left-to-right and everything is universally designed in that orientation. Even the surrounding real world objects follow the same left-to-right layout and arrangement. This is different in the Persian/Iran locale where text is mostly right-to-left, but there are left-to-right elements as well. So, this environment is not directionally pure and strict as is the Latin environment and can’t be a perfect mirror of it.

The real world objects and devices further obscure the directionality for computer software when we view software as a tool and like an appliance, not a piece of text (e.g. a book) that someone reads. Look at the technological devices that surround us all around the world. Consider for example the Audio/Visual equipment such as Radios, DVD players, etc. They do not have a regional version with a different right-to-left physical layout for right-to-left/bidirectional locales. Many computer user interfaces simulate a device with buttons, sliders, dials and etc. Such a user interface would not look familiar if mirrored into a right-to-left layout, because the physical and real-world counterparts are never right-to-left. This only causes confusion and makes using the user interface more difficult instead of making it easier to use.

For example, a progress bar shows a numeric value or ratio. It also resembles some real world devices. The numbers and numerical x-axis are left-to-right. So, a mirrored progress bar is incorrect and looks weird to a user in Persian/Iran locale although the locale is considered right-to-left. This also implies that some supporting objects (say a stop button next to the progress bar) also do not follow right-to-left text direction. Any object that is modeled after a real-world object or represents numeric values or mathematical charts should follow the directionality of whatever concept it is representing and not the text direction.

Also, it should be noted that for the foreseeable future there will be many software applications that are not localized for Persian. The user interface of this software will continue to be Latin with more or less Latin directionality. Having too much difference of layout between Persian and Latin applications makes using a mix of Persian and Latin applications more difficult.

Changing the location and orientation of user interface elements that are not directly affected by text direction is generally not recommended. An example that demonstrates that a certain alignment is not mandated by text direction is the placement of window control widgets (close/minimize/maximize). As you see in the following figures, these controls are placed at the opposite sides of the window with almost mirrored layout between two dominant proprietary operating systems Windows and Mac OS:

![](PersianHIG-EN-Main44_html_163adb16.png) Window control widgets in Microsoft Windows

![](PersianHIG-EN-Main44_html_m1f9926d4.png) Window control widgets in Apple Mac OS X

This clearly indicates that the location of these controls is a matter of choice and design preference rather than being mandated by writing direction. A lot of other placements are also like this. If it was a few years ago, we had to urge developers to consider mirroring their layouts to better conform to our locale, but now it seems that we need to ask them to stop mirroring every single element they encounter. So, it is now recommended that you mirror elements only when there is a good reason to do so, usually based on the writing direction.

We also need to point out another important consideration when changing the location of elements in a layout. Returning to the above example of window control widgets, you see that in both Mac and Windows layouts, the close box is in the corner. The corners (any of the four corners) are places that are better noticed and more easily targeted. So, the most frequently used elements are placed in such strategic places. This means that there are many special design considerations that determine the suitable place for an element. Any layout change should be made in a way that does not sabotage the design and make it harder to use.

There is an important example of incorrectly changing the placement of GUI elements that can be found in GNOME 2.6 as configured by default in Fedora Core 4 distribution. The English locale shows the three menus on the top bar of the screen from left to right as Programs, Places and then Desktop. When we switch to Persian/Iran locale, these menus are still on the left side of the screen but their order is reversed. So, when Persian/Iran locale active, the menus from left to right are Desktop, Places and then Programs. This is shown in the following figures:

![](PersianHIG-EN-Main44_html_514f908b.png) **OK**

![](PersianHIG-EN-Main44_html_m75a9e912.png) **Wrong!**

In the Latin version, the Programs menu is placed in the corner of the screen to benefit from the Fitts’ law (see [Fitts’]) to make it the easiest menu to access. The current rearrangement in the Persian/Iran locale violates this design. If the menu was fully mirrored so that the Programs menu where placed on the top-right corner of the screen, then the design would have been preserved, and the change would be valid.

As a rule of thumb: If for some technical limitation, you can’t fully re-arrange the layout to preserve its intended function, don’t touch it at all.

There is another design issue in the above mentioned GNOME Programs menu. It is related to the use of alphabetical order in that menu. Since the Programs menu is accessed very often, it is important that the most frequently accessed items in this menu placed properly to make them easier to access. Also, their location should be stable so that the user can learn their place and find them easily. In such a menu, use of alphabetical ordering is a design mistake, because it does not guarantee a suitable and stable place for the often used menu items. The important items should have a suitable and fixed place in the menu and the rest of the items arranged either chronologically (to preserve the location of the older items) or alphabetically if the number of the items in the list exceeds about 7 items.

This bad design choice can be partially offset by using clever names to put the frequently used items in proper places. For example, the name of the frequently used Accessories submenu helps it stay at the top of the menu to make it easier to access. But there is no guarantee that a localized version can (or will) preserve that menu order. For example, in the existing draft Persian translation, the location of the first (Accessories) and last (System Tools) submenus in the Programs menu is reversed. The result is a different (reduced) usability for the Persian version compared to the Latin version.

**Rule 1: The localization of software should not adversely affect its usability and design features.**

**Rule 2: Avoid using alphabetical ordering of the interface elements (such as menu commands) in the design of the internationalized software.**

**The alphabetical ordering is only advised in list of elements that are dynamic and contain many elements.**

**Guideline 1: To support right-to-left (actually bidirectional) locales, avoid blindly mirroring the entire user interface. Developer tools and graphical toolkits should provide more control for developers and localizers in specifying the proper placement of user interface elements.**

**Guideline 2: To reduce unexpected directionality related issues with GUI designs it is advised the vertically symmetric designs used as much as possible.**

### 4.4. The Effect of Different Direction in Desktop, Software and Document

We briefly mentioned the issues of a mixed Persian/Latin environment. Since this is a common scenario, we will discuss it in more detail here. The first thing to note is the three main elements that the user is dealing with when using a computer:

-   First element is the graphical desktop environment which provides the basic facilities including windows and menus.
-   The second element is the application which is used to perform the intended task.
-   The third element is the content or the data related to the task which could often be a document.

At any given time, only one locale should be designated as the active user locale and changing the active locale may require restarting the user session to give a change to properly refresh and relocated the user interface. Having different active locales per running applications is not recommended since it can break the stability of the user interface, especially if each locale has a different directionality. Still, if we have the same locale set for all applications, it is not guaranteed that the three elements above all adhere to the same active locale. When a certain locale is made active, still the desktop environment or the applications may not be localized to support the locale language.

Also, the active locale does not determine the language of the data that we will be using. The document opened in the application may have any language and may need to be formatted according to any locale. For example, when the English/US locale is active we may prepare an invoice for an international customer in Spanish (with Spanish number delimiters and date format). This means that some flexibility in the locale activation is required for properly handling data intended for a different locale without completely switching to that locale. Such a document specific locale only affects the document content and should not affect the GUI.

The directionality of the active GUI locale, usually takes precedence over the actual language of the user interface to maintain the consistency and stability of common GUI elements. For example, menu bar is a GUI element that is almost universally available in all applications. It also usually has similar menus in all applications, such as File and Edit menus. For this reason, and despite the fact that menu bar has a text oriented appearance which suggests adhering to the direction of the language, the direction of the menu bar should stay the same for all applications on the same desktop environment. If the active locale is Persian/Iran the menu bar will be right-to-left even for applications that are not localized to Persian. In such a case while localized Persian applications have menu bars with expected orientation, such as the following figure

پرونده ویرایش نمایش جستجو … **OK**

None-localized applications will appear to have a reversed menu bar as in the following figure:

File Edit View Search … **OK**

This behavior is the correct behavior despite looking strange in the none-localized application, because it maintains the consistency of the placement of equivalent elements. Any elements that are very common and have a consistent placement across most applications should maintain a consistent placement according to active locale. Another example in this regard is the placement of OK and Cancel buttons and other similar elements. One of the most important elements that are sometimes misplaced in this regard is the vertical scroll bar. It has been seen in some web browsers that they flip the position of the vertical scroll bar if you navigate from a page into another page that has the opposite directionality. This is definitely wrong behavior, since scroll bar is one of the most frequently used elements in the user interface and maintaining consistency and stability in its location is very important. The other point regarding scroll bar is that its placement does not really depend on writing direction. For example, in the SmallTalk environment the vertical scroll bar placed on the opposite side. So, unlike the menu bar where keeping the main locale direction makes it look strange, the scroll bar is perfectly OK wherever it is placed as long as it does not flip around.

But this does not apply to the parts of the user interface that are expected to be read like text. For example, a form where there are labels and fields, the relative order of fields and their labels should follow the direction of the language they are written in, not that of the active locale. The following screen shot shows the existing incorrect behavior of GNOME:

![](PersianHIG-EN-Main44_html_768dd48b.png) **Wrong!**

As you see in the above picture right-to-left layout is clearly incorrect when the actual language of the text in the GUI is English.

**Rule 1: The placement of the common interface elements follows the direction of the active locale, even if the actual language has a different direction.**

**The directionality of custom GUI elements that are read like text should adhere to the actual language of the GUI regardless of the active locale direction.**

The decision of the proper placement of the GUI elements is also affected by the fact that there is a considerable user base for the existing none-localized and left-to-right desktop environments. In order to ease the transition of the existing users, the changes in the placement and orientation of the GUI elements should be kept to the minimum that is necessary.

**Rule 2: Do not change the orientation and placement of GUI elements unless this is really necessary.**
