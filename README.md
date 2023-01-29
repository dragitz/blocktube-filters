# blocktube-filters
List of personal regex filters



## Emojis and clickbait)
```
// Emojis and clickbait)
/(?=.*‼️|✅|✔️|👉|👽|💪|📌|🔥|😂|😆|😍|😦|😱|😳|🙏|💖|💞|💡|😊|🐼|🎬|❌)/
/^(you won't believe what happens next|top [0-9]+ things you need to see|[0-9]+ shocking facts about|how to [0-9]+x your [0-9]+ in [0-9]+ easy steps|[0-9]+ reasons why [a-zA-Z0-9\s]+ is the best)$/i
/(viral video)|(simple trick)|(watch until the end)|(over 10 million views)/i
/\d+ (easy|simple|surprising|unexpected|best|clever|crazy|must-know|daily|ingenious) (ways|hacks|must-know|survival|cleaning|secret|solutions) (to|for|that|hacks|tips) [a-zA-Z ]+/i
```

## Remove top 3, 10, 20.. videos - case-insensitive
```
/Top\s*\d+/i
```

## ASCII mode only
```
[^\x00-\x7F]+/g
```

## Malware
```
// Blocks: *2023*, *new*, *crazy*, *undetected*, ecc..
/\*[a-zA-Z0-9]+\*/i

// all the pipes that appeared more than 1 time in the text, whether they were sequential or not
// Blocks "|hello|world|" and "|abc|def|ghi|", often used by scammers and videos with fradulent software
/(?=(?:[^|]*\|){2,})(?:[^|]*\|)/i

// same as before but for "/" , "#" and ","
/(?=(?:[^/]*\/){2,})(?:[^/]*\/)/i
/(?=(?:[^,]*\,){2,})(?:[^,]*\,)/i
/(?=(?:[^#]*\#){2,})(?:[^#]*\#)/i
```
Match multiple words, doesn't matter the order
```
/^(download [a-zA-Z0-9\s]+ cheat|[a-zA-Z0-9\s]+ crack download|download [a-zA-Z0-9\s]+ mod apk)$/i
/(?=.*%)(?=.*hack)(?=.*||)/i
/(?=.*aimbot)(?=.*hack)(?=.*cheat)/i
/(?=.*aimbot)(?=.*hack)(?=.*esp)/i
/(?=.*aimbot)(?=.*hack)(?=.*|)/i
/(?=.*download)(?=.*aimbot)(?=.*free)/i
/(?=.*download)(?=.*cheat)(?=.*free)/i
/(?=.*download)(?=.*esp)(?=.*free)/i
/(?=.*download)(?=.*menu)(?=.*free)/i
/(?=.*download)(?=.*undetected)(?=.*free)/i
/(?=.*download)(?=.*working)(?=.*free)/i
/(?=.*free)(?=.*crack)(?=.*download)/i
/(?=.*free)(?=.*crack)(?=.*|)/i
/(?=.*free)(?=.*discord)(?=.*nitro)/i
/(?=.*free)(?=.*menu)(?=.*aimbot)/i
/(?=.*free)(?=.*menu)(?=.*esp)/i
/(?=.*free)(?=.*menu)(?=.*wallhack)/i
/(?=.*free)(?=.*fire)(?=.*headshot)/i
/(?=.*free)(?=.*fire)(?=.*download)/i
/(?=.*free)(?=.*fire)(?=.*cheat)/i
/(?=.*free)(?=.*fire)(?=.*bypass)/i
/(?=.*free)(?=.*hacks)(?=.*cheats)/i
/(?=.*free)(?=.*cheat)(?=.*download)/i
/(?=.*free)(?=.*hack)(?=.*download)/i
/(?=.*free)(?=.*hack)(?=.*esp)/i
/(?=.*free)(?=.*hack)(?=.*aim)/i
/(?=.*free)(?=.*hack)(?=.*aimbot)/i
/(?=.*hack)(?=.*%)(?=.*free)/i
/(?=.*hack)(?=.*%)(?=.*gratis)/i
/(?=.*hack)(?=.*%)(?=.*gratuito)/i
/(?=.*hack.*)(?=.*undetected.*)/i
/(?=.*wallhack)(?=.*aimbot)(?=.*free)/i
/(?=.*wallhack)(?=.*aimbot)(?=.*gratis)/i
/(?=.*wallhack)(?=.*aimbot)(?=.*gratuito)/i
/(?=.*working)(?=.*aimbot)(?=.*esp)/i
/(?=.*working)(?=.*aimbot)(?=.*wallhack)/i
/(?=.*working)(?=.*nitro)(?=.*discord)/i
/(?=.*working)(?=.*wallhack)(?=.*esp)/i
/(?=.*undetected)(?=.*cheat)(?=.*2021)/i
/(?=.*undetected)(?=.*hack)(?=.*2021)/i
/(?=.*undetected)(?=.*cheat)(?=.*2022)/i
/(?=.*undetected)(?=.*hack)(?=.*2022)/i
/(?=.*undetected)(?=.*cheat)(?=.*2023)/i
/(?=.*undetected)(?=.*hack)(?=.*2023)/i
/(?=.*esp)(?=.*hide)(?=.*hack)/i
/(?=.*esp)(?=.*mod)(?=.*hack)/i
/(?=.*mobile)(?=.*bypass)(?=.*hack)/i
/(?=.*mobile)(?=.*bypass)(?=.*hack)/i
/(?=.*mobile)(?=.*esp)(?=.*hack)/i
/(?=.*mobile)(?=.*aimbot)(?=.*hack)/i
/(?=.*mobile)(?=.*updated)(?=.*hack)/i
/(?=.*mobile)(?=.*updated)(?=.*hack)/i
/(?=.*cheat)(?=.*hack)(?=.*download)/i
/(?=.*|)(?=.*hack)(?=.*apk)/i
/(hack&esp&download)/i
```

## Ignorant and time wasting videos
```
/(?=.*must watch)/i
/(?=.*everyday hacks)/i
/(?=.*food hacks)/i
/(?=.*genius hack)/i
/(?=.*genius hacks)/i
/(?=.*genius tiktok)/i
/(?=.*life hack)/i
/(?=.*life hacks)/i
/(?=.*life saving hacks)/i
/(?=.*lifehack)/i
/(?=.*lifehack,)/i
/(?=.*lifehacks)/i
/(?=.*lifehacks,)/i
/(?=.*react to)/i
/(?=.*123 go)/i
/(?=.*123 go!)/i
/(?=.*la la life)/i
/(?=.*#short)/i
/(?=.*memes)/i
/(?=.*family guy)/i
```
