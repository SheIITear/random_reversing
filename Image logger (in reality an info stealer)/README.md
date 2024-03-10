This is something I came across claiming to be "image logger for discord". In short it was marketed as something that could grab a discord users information (cookies, ip, pc info etc) just by opening an image.
This is usually not possible (if we do not include special cases) so it caught my attention.

Sources: https://www.youtube.com/watch?v=IYYG61Isgh8 (taken down) -> https://mega.nz/file/xAVzgZJR#KFAziSTHwyzQn1PXWpzDUYHIkPnDpDBkoYHrGvS4La4

So what's really inside the that piece of a python code?

1. The code was obfuscated multiple times by someone.
2. They used two different methods of obfuscation; compiling to bytecode and making the code harder to read -> first layer: https://github.com/Blank-c/BlankOBF, I was not able to identify the tool used for last layer.
3. The code under its hood was in reality an info stealer built using "luna grabber" -> https://github.com/Smug246/Luna-Grabber and used a fake error to hide its intentions.
4. The stolen data from victims would be sent to their discord webhook -> https://discord.com/api/webhooks/1212945438219698216/8Fgnm2-6EiG414pB1y2spJJdk0OOf1Qejpzn-RDhW7D33VkX_x9ef0b07b5uruzrTmzE. 

Sneak peeks from the inside:
![image](https://github.com/SheIITear/random_reversing/assets/62976449/dd2dde26-6fb9-4057-8dca-17b33382b1b0)
![image](https://github.com/SheIITear/random_reversing/assets/62976449/bd8e9edf-325f-4ad2-9736-00465e9bbb9e)

```
(0, None, 'wintypes', 'cpu_count', 'copy2', 'ZIP_DEFLATED', 'ZipFile'), 'AES', ('Image', 'ImageGrab'), 'MultipartEncoder', 'CryptUnprotectData', 'https://discord.com/api/webhooks/1212945438219698216/8Fgnm2-6EiG414pB1y2spJJdk0OOf1Qejpzn-RDhW7D33VkX_x9ef0b07b5uruzrTmzE', True, 'Everyone', False, ('webhook', 'ping', 'pingtype', 'fakeerror', 'startup', 'defender', 'systeminfo', 'backupcodes', 'browser', 'roblox', 'obfuscation', 'injection', 'minecraft', 'wifi', 'killprotector', 'antidebug_vm', 'discord', 'anti_spam', 'self_destruct', 'clipboard'), 'temp', '', 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789', 10, 'k', 'localappdata', 'webhook', <code object main, file "<string>", line 34>, 'main', <code object Luna, file "<string>", line 71>, 'Luna', <code object configcheck, file "<string>", line 87>, 'configcheck', <code object fakeerror, file "<string>", line 106>, 'fakeerror', <code object startup, file "<string>", line 110>, 'startup', <code object disable_defender, file "<string>", line 124>, 'disable_defender', ('_dir', <code object create_temp, file "<string>", line 129>, 'create_temp', <code object killprotector, file "<string>", line 140>, 'killprotector', <code object zipup, file "<string>", line 178>, 'zipup', <code object PcInfo, file "<string>", line 189>, 'PcInfo', <code object Discord, file "<string>", line 232>, 'Discord', <code object Browsers, file "<string>", line 499>, 'Browsers', <code object Wifi, file "<string>", line 699>, 'Wifi', <code object Minecraft, file "<string>", line 729>, 'Minecraft', <code object BackupCodes, file "<string>", line 758>, 'BackupCodes', <code object AntiSpam, file "<string>", line 775>, 'AntiSpam', <code object SelfDestruct, file "<string>", line 799>, 'SelfDestruct', <code object Clipboard, file "<string>", line 818>, 'Clipboard', <code object Injection, file "<string>", line 836>, 'Injection', <code object Debug, file "<string>", line 888>, 'Debug', '__main__', 'nt', 'webhook', (None)
```
