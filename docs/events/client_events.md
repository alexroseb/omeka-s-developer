---
title: Client Events
---

Client events are fired from within Omeka S's JavaScript code. Omeka S makes extensive use of jQuery, particularly on admin pages. Many user interactions require additional actions to respond to the changes on the page. For this, Omeka S uses the `trigger()` function so other parts of javascript code can follow up.

For example, when the sidebar is opened, a module might need to respond in some way, so opening the sidebar fires a `sidebar-opened` event:

```js
    openSidebar : function(sidebar) {
        sidebar.addClass('active');
        this.reserveSidebarSpace();
        sidebar.trigger('o:sidebar-opened');
    },
```

See [the client event reference page](client_event_reference.md) for a list of client-side events provided by Omeka S.
