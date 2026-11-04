# I finally learned to use the debugger

For two years I debugged with print statements. It worked, mostly.

Last week a bug only showed up on the third request after a login, and my prints scrolled past faster than I could read them. A teammate watched me for a minute and said, "Just set a breakpoint."

So I did. I stopped at the third request, looked at the session, and saw the token had already been refreshed once. The fix took ten minutes after that.

I'm not giving up print statements. They're still the fastest way to check one value. But when a bug depends on what happened before, I reach for the debugger first now.
