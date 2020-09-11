# SA-MP Node (easydialogs include)

### SA-MP Node
a SA-MP plugin to support nodejs apps and run them on your server.
(repo link: [AmyrAhmady/samp-node](https://github.com/AmyrAhmady/samp-node))


### How To Use
```
// dialog types
DIALOG_STYLE_MSGBOX				0
DIALOG_STYLE_INPUT				1
DIALOG_STYLE_LIST				2
DIALOG_STYLE_PASSWORD			3
DIALOG_STYLE_TABLIST			4
DIALOG_STYLE_TABLIST_HEADERS	5

// write ur into pawn script

forward JS_DialogShow(playerid, id[], name[], type, header[], message[], button1[], button2[]);
public JS_DialogShow(playerid, id[], name[], type, header[], message[], button1[], button2[])
{
    Dialog_Show(playerid, id, name, type, header, message, button1, button2);
    return 1;
}

// if u want open dialog use this
samp.callPublic("JS_DialogShow", "issdssss", playerid, "dialog_name", "dialog_name", type_id, "header_text", "inputtext", "button1", "button2")
and yes u write dialog_name two times.

// dialog callback in js
samp.registerEvent("dialog_name", "idds");
samp.on("dialog_name", (playerid, response, listitem, inputtext) => {
        // code
});
```
