---
title: Access Data with Cards
author: Cumulus Networks
weight: 509
aliases:
 - /display/NETQ22/NetQ-User-Interface-Overview
 - /pages/viewpage.action?pageId=12321856
pageID: 12321856
product: Cumulus NetQ
version: 2.2
imgData: cumulus-netq-22
siteSlug: cumulus-netq-22
---
Cards present information about your network for monitoring and
troubleshooting. This is where you can expect to spend most of your
time. Each card describes a particular aspect of the network. Cards are
available in multiple sizes, from small to full screen. The level of the
content on a card varies in accordance with the size of the card, with
the highest level of information on the smallest card to the most
detailed information on the full-screen card. Cards are collected onto a
workbench where you see all of the data relevant to a task or set of
tasks. You can add and remove cards from a workbench, move between cards
and card sizes, change the time period of the data shown on a card, and make copies of cards to show different levels of
data at the same time.

## Card Sizes

The various sizes of cards enables you to view your content at just the
right level. For each aspect that you are monitoring there is typically
a single card, that presents increasing amounts of data over its four
sizes. For example, a snapshot of your total inventory may be
sufficient, but to monitor the distribution of hardware vendors may
requires a bit more space.

### Small Cards

Small cards are most effective at providing a quick view of the
performance or statistical value of a given aspect of your network. They
are commonly comprised of an icon to identify the aspect being
monitored, summary performance or statistics in the form of a graph
and/or counts, and often an indication of any related events. Other
content items may be present. Some examples include a Devices Inventory
card, a Switch Inventory card, an Alarm Events card, an Info Events
card, and a Network Health card, as shown here:

{{< figure src="/images/netq/cumulus-wb-default-small-cards-only.png" width="700" >}}

### Medium Cards

Medium cards are most effective at providing the key measurements for a
given aspect of your network. They are commonly comprised of an icon to
identify the aspect being monitored, one or more key measurements that
make up the overall performance. Often additional information is also
included, such as related events or components. Some examples include a
Devices Inventory card, a Switch Inventory card, an Alarm Events card,
an Info Events card, and a Network Health card, as shown here. Compare
these with their related small- and large-sized cards.

{{< figure src="/images/netq/cumulus-wb-default-med-cards-only.png" width="700" >}}

### Large Cards

Large cards are most effective at providing the detailed information for
monitoring specific components or functions of a given aspect of your
network. These can aid in isolating and resolving existing issues or
preventing potential issues. They are commonly comprised of detailed
statistics and graphics. Some large cards also have tabs for additional
detail about a given statistic or other related information. Some
examples include a Devices Inventory card, an Alarm Events card, and a
Network Health card, as shown here. Compare these with their related
small- and medium-sized cards.

{{< figure src="/images/netq/sample-of-large-cards.png" width="500" >}}

### Full-Screen Cards

Full-screen cards are most effective for viewing all available data
about an aspect of your network all in one place. When you cannot find
what you need in the small, medium, or large cards, it is likely on the
full-screen card. Most full-screen cards display data in a grid, or
table; however, some contain visualizations. Some examples include All
Events card and All Switches card, as shown here.

{{< figure src="/images/netq/events-alarms-fullscr.png" width="700" >}}

{{< figure src="/images/netq/inventory-devices-switches-fullscr-allswitch-tab.png" width="700" >}}

### Card Size Summary

<table>
<colgroup>
<col style="width: 16%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
<col style="width: 21%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Card Size</p></td>
<td><p>Small</p></td>
<td><p>Medium</p></td>
<td><p>Large</p></td>
<td><p>Full Screen</p></td>
</tr>
<tr class="even">
<td><p>Primary Purpose</p></td>
<td><ul>
<li><p>Quick view of status, typically at the level of good or bad</p></li>
<li><p>Enable quick actions, run a validation or trace for example</p></li>
</ul></td>
<td><ul>
<li><p>View key performance parameters or statistics</p></li>
<li><p>Perform an action</p></li>
<li><p>Look for potential issues</p></li>
</ul></td>
<td><ul>
<li><p>View detailed performance and statistics</p></li>
<li><p>Perform actions</p></li>
<li><p>Compare and review related information</p></li>
</ul></td>
<td><ul>
<li><p>View all attributes for given network aspect</p></li>
<li><p>Free-form data analysis and visualization</p></li>
<li><p>Export data to third-party tools</p></li>
</ul></td>
</tr>
</tbody>
</table>

## Data Grid Settings

You can manipulate the data in a data grid in a full-screen card in
several ways.

### Sort Data by Column

Hover over a column header and click <img src="https://icons.cumulusnetworks.com/01-Interface-Essential/35-Text-Options/arrange-letter.svg", height="18", width="18"/>.

### Choose Columns to Display

1.  Click <img src="https://icons.cumulusnetworks.com/01-Interface-Essential/12-Settings/cog-1.svg", height="18", width="18"/> at the top right of the card.
2.  Click **Change Columns** from the **Display Settings**.
3.  Click the checkbox next to each column name to toggle on/off the
    columns you would like displayed. Columns listed under **Active**
    are displayed. Columns listed under **Inactive** are not displayed.

    {{%notice tip%}}

When you have a large number of possible columns for display, you
    can search for the column name using the **Quick Filter** to find
    and select or deselect the column more quickly.

    {{%/notice%}}

4.  Click <img src="https://icons.cumulusnetworks.com/01-Interface-Essential/33-Form-Validation/close.svg", height="16", width="16"/> to close the selection box and view the updated data grid.

### Change Order of Columns

1.  Click <img src="https://icons.cumulusnetworks.com/01-Interface-Essential/12-Settings/cog-1.svg", height="18", width="18"/> and then click **Change Columns**.
2.  Hover over a column name.

    {{%notice tip%}}

You use the **Quick Filter** to find the column when you have a large
    number of columns.

    {{%/notice%}}

3.  Point to the six dots to the left of the checkbox.
4.  Click and drag the selected column up or down in the list.

    {{% imgOld 21 %}}

5.  Click <img src="https://icons.cumulusnetworks.com/01-Interface-Essential/33-Form-Validation/close.svg", height="16", width="16"/> to close the selection box and view the updated data grid.

### Take Actions on Items

In the full screen cards, you can determine which results are displayed
in the results list, and which are exported.

To take actions on the data, click in the blank column at the very left
of a row. A checkbox appears, selecting that item, and an edit menu is
shown at the bottom of the card (shown enlarged here).

{{% imgOld 23 %}}

{{% imgOld 24 %}}

You can perform the following actions on the results list. **Note**:
The actions vary based on the card displayed.

| Option                   | Action or Behavior on Click                                                                                      |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Select All               | Selects all items in the results list                                                                            |
| Clear All                | Clears all existing selections of items in the results list. This also hides the edit menu.                      |
| Edit                     | Edit the selected items                                                                                          |
| Delete                   | Remove the selected items                                                                                        |
| Generate/Delete AuthKeys | Create or remove NetQ Cloud authorization keys                                                                   |
| Open Cards               | Open the corresponding validation or trace result card                                                           |
| Hide Selected            | Hide selected items (switches, sessions, alarms, and so forth) from the results list                             |
| Show Only Selected       | Hide unselected items (switches, sessions, alarms, and so forth) from the results list                           |
| Export Selected          | Exports selected data into a .csv file. If you want to export to a .json file format, use the **Export** button. |

To return to original display of results, click the associated tab.

## Export Data

You can export tabular data from a full screen card to a CSV- or
JSON-formatted file.

To export the data:

1.  If you want to export only a subset of the data listed, select those
    items first.
2.  Click **EXPORT**.

    {{% imgOld 25 %}}

3.  Select all data or selected data for export in the dialog box:

    {{% imgOld 26 %}}

4.  Select the export format.
5.  Click **EXPORT** to save the file to your downloads directory.

{{%notice tip%}}

You can quickly export all data to a .csv file in one of two ways:

  - Click **Export** at top of list, and click **Export** in the dialog,
    or
  - Select one item, click **Select All**, click **Export Selected**.

{{%/notice%}}

## Card Interactions

Every card contains a standard set of interactions, including the
ability to switch between card sizes, and change the time period of the
presented data. Most cards also have additional actions that can be
taken, in the form of links to other cards, scrolling, and so forth. The
four sizes of cards for a particular aspect of the network are connected
into a flow; however, you can have duplicate cards displayed at the
different sizes. Cards with tabular data provide filtering, sorting, and
export of data. The medium and large cards have descriptive text on the
back of the cards.

To access the time period, card size, and additional actions, hover over
the card. These options appear, covering the card header, enabling you
to select the desired option.

### Change the Time Period for the Card Data

All cards have a default time period for the data shown on the card,
typically the last 24 hours. You can change the time period to view the
data during a different time range to aid analysis of previous or
existing issues.

To change the time period for a card:

1.  Hover over any card.
2.  Click <img src="/https://icons.cumulusnetworks.com/01-Interface-Essential/18-Time/time-stopwatch.svg", height="18", width="18"/> in the header.
3.  Select a time period from the dropdown list.

    {{% imgOld 28 %}}

{{%notice tip%}}

Changing the time period in this manner only changes the time period for
the given card.

{{%/notice%}}

### Switch to a Different Card Size

You can switch between the different card sizes at any time. Only one
size is visible at a time. To view the same card in different sizes,
open a second copy of the card.

To change the card size:

1.  Hover over the card.
2.  Hover over the Card Size Picker and move the cursor to the right or
    left until the desired size option is highlighted.

    {{% imgOld 29 %}}

    Single width opens a small card. Double width opens a medium card.
    Triple width opens large cards. Full width opens full-screen cards.

3.  Click the Picker.  
    The card changes to the selected size, and may move its location on
    the workbench.

### View a Description of the Card Content

When you hover over a medium or large card, the bottom right corner
turns up and is highlighted. Clicking the corner turns the card over
where a description of the card and any relevant tabs are described.
Hover and click again to turn it back to the front side.

{{% imgOld 30 %}}

{{% imgOld 31 %}}

### Reposition a Card on Your Workbench

You can also move cards around on the workbench, using a simple drag and
drop method.

To move a card:

1.  Simply click and drag the card to left or right of another card,
    next to where you want to place the card.
2.  Release your hold on the card when the other card becomes
    highlighted with a dotted line. In this example, we are moving the
    medium Network Health card to the left of the medium Devices
    Inventory card.  

    {{% imgOld 32 %}}

    {{% imgOld 33 %}}

    {{% imgOld 34 %}}

### Add or Remove a Card

You can add or remove cards from a workbench at any time.

To add a card:

1.  Click {{% imgOld 35 %}}.

    {{% imgOld 36 %}}

2.  Select a card from the available list.

The card is placed at the end of the set of cards currently on the
workbench. You might need to scroll down to see it. By default, the
medium size of the card is added to your workbench. You can move it to
another location as described above.

To remove a card:

1.  Hover over the card you want to remove.
2.  Click <img src="/https://icons.cumulusnetworks.com/01-Interface-Essential/03-Menu/navigation-menu-horizontal.svg", height="18", width="18"/> (*More Actions* menu).
3.  Click **Remove**.

    {{% imgOld 38 %}}

The card is removed from the workbench, but not from the application.

## Card Workflows

The UI provides a number of card workflows. Card workflows focus on a
particular aspect of your network and are a linked set of each size
card—a small card, a medium card, one or more large cards, and one or
more full screen cards. The following card workflows are available:

  - **Network Health**: network-wide view of network health
  - **Devices|Switches**: health of a given switch
  - **Inventory|Devices**: information about all switches and hosts in
    the network
  - **Inventory|Switches**: information about the components on a given
    switch
  - **Events|Alarms**: information about all critical severity events in
    the system
  - **Events|Info**: information about all warning, info, and debug
    events in the system
  - **Network Services**: information about the network services and
    sessions
  - **Validation Request** (and Results): network-wide validation of
    network protocols and services
  - **Trace Request** (and Results): find available paths between two
    devices in the network fabric

### Access a Card Workflow

You can access a card workflow in multiple ways:

  - For workbenches available from the main menu, open the workbench
    that contains the card flow
  - Open a prior search
  - Add it to a workbench
  - Search for it

{{%notice tip%}}

If you have multiple cards open on your workbench already, you might
need to scroll down to see the card you have just added.

{{%/notice%}}

To open the card workflow through an existing workbench:

1.  Click <img src="https://icons.cumulusnetworks.com/52-Arrows-Diagrams/01-Arrows/arrow-button-down-2.svg", height="14", width="14"/> in the workbench task bar.

2.  Select the relevant workbench.

    {{% imgOld 40 %}}

    The workbench opens, hiding your previous workbench.

To open the card workflow from a prior search:

1.  Browse your search list in the navigation panel.
2.  Look for an "Add: \<card name\>" item.
3.  If it is still available, click the item.

    The card appears on the current workbench, at the bottom.

To access the card workflow by adding the card:

1.  Click <img src="https://icons.cumulusnetworks.com/44-Entertainment-Event-Hobbies/02-Card-Games/card-game-diamond.svg", height="14", width="14"/> in the workbench task bar.
2.  Select the relevant card.

    The card appears on the current workbench, at the bottom.

To access the card workflow by searching for the card:

1.  Click in the **Global Search** field.
2.  Begin typing the name of the card.
3.  Select it from the list.

    {{% imgOld 42 %}}

    The card appears on a current workbench, at the bottom.

## Card Decks

A card deck is a collection of related cards that can be added and
removed from a workbench all at once. They are distinct from card
workflows, which focus on a particular aspect of your network. A card
deck pulls multiple cards with related information to aid the user in
performing a broader task. It also simplifies the creation of new
workbenches when a card deck is available. The following card decks are
provided by default:

  - **Inventory**: includes the medium Inventory | Switches and
    Inventory | Devices cards
  - **Events**: includes the medium Events | Alarms and Events | Info
    cards

To add a card deck:

1.  Click {{% imgOld 43 %}} in the workbench task bar.
2.  Select the deck you want to add to your workbench.
