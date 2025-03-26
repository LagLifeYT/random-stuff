# Loading old YouTube Polymer UI captures
Have you ever tried to load a capture of YouTube on the Wayback Machine, only to be met with *this*?
![image](https://github.com/user-attachments/assets/3fd84214-dfd3-44b3-a22f-df40f68208a0)
This usually happens when the Internet Archive archives the polymer version of YouTube, which existed alongside the older Hitchhiker UI for about three years, from August 29, 2017 to mid-June 2020.
Unfortunately, while the newer versions of it load just fine, the versions from August 2017 to June 2020 often don't. 

So what causes this? Well, looking in the browser console of one of these broken captures reveals an error. 

![image](https://github.com/user-attachments/assets/1ff90145-0ee9-479f-88f2-932dfe88a724)

So why does this specific function not exist?

Well, Chrome and other major browsers deprecated *and then removed* this API around early 2020, breaking compatibility with any site or extension that still used it.
There's actually reports of this change breaking extensions and websites when the API was removed, as seen [here](https://github.com/Adobe-CEP/CEP-Resources/issues/272)
Now, of course, there's a newer function available that replaces it. But it's not just a drop in replacement, and since it's not, replacing every instance would be a total
waste of time. 

Instead, let's just try using an older browser version!

![image](https://github.com/user-attachments/assets/619b0d5b-fa7d-47fd-8f2b-d2f05f7b202d)
*PewDiePie's channel page, captured on April 14, 2019, using the Polymer UI. Loaded in Google Chrome v70.*

So that worked. But there is one glaring issue with just downgrading your browser version, which is that it will immediately
try to autoupdate. You'd have to disable this, but then that's no good since now you're running a browser which is *at least* 5 years out of date!

Unfortunately, I have been unable to find any other way of loading these captures in 2025. The maximum Chrome version that can be used to load them is 79, as `document.registerElement` was removed in Chrome 80.
