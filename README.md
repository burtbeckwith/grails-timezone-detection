# About
The Grails Timezone Detection Plugin makes use of the
[jsTimezoneDetect Library](http://pellepim.bitbucket.org/jstz/) in order to make the
client/browser's timezone available on the server/JVM.  Additionally, this plugin overrides
the default Grails formatDate tag to make use of the user's current timezone.

# Installation

TBD - pending approval

# Usage

Simply include the tz:detect tag inside of your head tag (preferably in your layout):

```rhtml
<head>
    ...
    <tz:detect />
</head>
```

If the timezone has not already been detected, the plugin will do a quick redirect to set the timezone,
and will then redirect back to the originally requested page.  This guarantees that the formatDate tag
will make use of the end user's timezone, even on the first page.

You can also use the 'show' tag to render other timezone information:

```rhtml
<tg:show /> <!-- results in TimeZone ID (i.e. UTC, CST) -->
<tg:show attribute="displayName" /> <!-- results in TimeZone display name (i.e. Universal Time Coordinated, America/Chicago, etc) -->
```

See the [java.util.TimeZone class](http://docs.oracle.com/javase/7/docs/api/java/util/TimeZone.html) for all available attributes.