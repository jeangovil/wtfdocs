---
title: "Google Calendar"
date: 2018-05-10T08:25:33-07:00
draft: false
weight: 10
---

<img class="screenshot" src="/imgs/modules/gcal.png" width="320" height="389" alt="gcal screenshot" />

Displays your upcoming Google calendar events.

**Note:** Setting up access to Google Calendars for Go is a bit unobvious. Check out Google's [Go Quickstart](https://developers.google.com/calendar/quickstart/go), and follow `Enable The Google Calendar API`. The configuration file downloaded is the file you use for the `secretFile` configuration option.

## Configuration

```yaml
gcal:
  colors:
    title: "red"
    description: "lightblue"
    highlights:
    - ['1on1|1\/11', 'green']
    - ['apple|google|aws', 'blue']
    - ['interview|meet', 'magenta']
    - ['lunch', 'yellow']
    past: "gray"
  conflictIcon: "🚨"
  currentIcon: "💥"
  displayResponseStatus: true
  email: "chriscummer@me.com"
  enabled: true
  eventCount: 12
  multiCalendar: true
  position:
    top: 0
    left: 0
    height: 4
    width: 1
  refreshInterval: 300
  secretFile: "~/.config/wtf/gcal/client_secret.json"
  showDeclined: true
  withLocation: true
```

### Attributes

`colors.title` <br />
The default colour for calendar event titles. <br />
Values: Any <a href="https://en.wikipedia.org/wiki/X11_color_names">X11 color</a> name.

`colors.description` <br />
The default color for calendar event descriptions. <br />
Values: Any <a href="https://en.wikipedia.org/wiki/X11_color_names">X11 color</a> name.

`colors.highlights` <br />
A list of arrays that define a regular expression pattern and a color.
If a calendar event title matches a regular expression, the title will
be drawn in that colour. Over-rides the default title colour. <br />
Values: [a valid regular expression, any <a href="https://en.wikipedia.org/wiki/X11_color_names">X11 color</a> name.]

`colors.past` <br />
The color for calendar events that have passed. <br />
Values: Any <a href="https://en.wikipedia.org/wiki/X11_color_names">X11 color</a> name.

`conflictIcon` <br />
The icon displayed beside calendar events that have conflicting times
(they intersect or overlap in some way). <br />
Values: Any displayable unicode character.

`currentIcon` <br />
The icon displayed beside the current calendar event. <br />
Values: Any displayable unicode character.

`displayLocation` <br />
Whether or not to display the location of the calendar event. <br />
Values: `true`, `false`.

`displayResponseStatus` <br />
Whether or not to display your response status to the calendar event.
<br />
Values: `true`, `false`.

`email` <br />
The email address associated with your Google account. Necessary for
determining `responseStatus`. <br />
Values: A valid email address string.

`enabled` <br />
Whether or not this module is executed and if its data displayed onscreen. <br />
Values: `true`, `false`.

`eventCount` <br />
The number of calendar events to display. <br />
Values: A positive integer, `0..n`.

`multiCalendar` <br />
Whether or not to display your primary calendar or all calendars you
have access to. <br />
Values: `true`, or `false`

`position` <br />
Where in the grid this module's widget will be displayed. <br />

`focusChar` <br />
Define one of the number keys as a short cut key to access the widget. <br />

`refreshInterval` <br />
How often, in seconds, this module will update its data. <br />
Values: A positive integer, `0..n`.

`secretFile` <br />
Your <a href="https://developers.google.com/calendar/quickstart/go">Google client secret</a> JSON file. <br />
Values: A string representing a file path to the JSON secret file.

`showDeclined` <br />
_Optional_. Whether or not to display events you've declined to attend. <br />
Values: `true`, or `false`

`withLocation` <br />
Whether or not to show the location of the appointment. <br />
Values: `true`, or `false`

## Source Code

```bash
wtf/modules/google/gcal/
```
