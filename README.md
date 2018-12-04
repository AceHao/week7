# Project 7 - WordPress Pentesting

Time spent: **10** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID  : WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
By exploiting a Cross-site scripting vulnerability the attacker can
hijack a logged in user’s session. This means that the malicious
hacker can change the logged in user’s password and invalidate the
session of the victim while the hacker maintains access. As seen from
the XSS example in this article, if a web application is vulnerable to
cross-site scripting and the administrator’s session is hijacked, the
malicious hacker exploiting the vulnerability will have full admin
privileges on that web application.
    - Vulnerability types:    Unauthenticated Stored Cross-Site Scripting (XSS)
    - Tested in version: 4.2.0
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough:  
  ![gif1](https://imgur.com/a/nEKiWlx.gif)
  - [x] Steps to recreate: 
        1. post " <a title='x onmouseover=alert(unescape(/hello%20world/.source))
style=position:absolute;left:0;top:0;width:5000px;height:5000px
 AAAAAAAAAAAA [64 kb] ...'></a> " as comment
 
  - [x] Affected source code:
    - [Link 1](https://klikki.fi/adv/wordpress2.html)
    
2. (Required) Vulnerability Name or ID : WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: A stored XSS vulnerability in WordPress allows an user with the posting capability to compromise the website.

Under default configuration, the attack requires a Contributor or Author level account. The attacker would insert specially formatted HTML containing JavaScript on a WordPress page or post. Some special configurations may allow posting or editing page content for unauthenticated users.

The malicious script is executed when an administrator views the page. From this point on the attack could proceed to server-side code execution in the same way as with the other recently published WordPress XSS's.

    - Vulnerability types: Authenticated Stored Cross-Site Scripting (XSS)
    - Tested in version: 4.2.0
    - Fixed in version:  4.2.3
  - [x] GIF Walkthrough: 
  ![gif2](https://imgur.com/a/U65Gbiz.gif)
  - [x] Steps to recreate: 
  1.  entered "<a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>
" in a page or posting using the HTML edit mode. 
  2. save a move mouse over the hyperlink to show alert.
  
  - [x] Affected source code:
    - [Link 2](https://codex.wordpress.org/Version_4.2.3)
3. (Required) Vulnerability Name or ID : WordPress 3.6.0-4.7.2 - Authenticated Cross-Site Scripting (XSS) via Media File Metadata
  - [x] Summary: Two Cross-Site Scripting vulnerabilities exists in the playlist
functionality of WordPress. These issues can be exploited by convincing
an Editor or Administrator into uploading a malicious MP3 file. Once
uploaded the issues can be triggered by a Contributor or higher using
the playlist shortcode.
    - Vulnerability types: Authenticated Cross-Site Scripting (XSS)
    - Tested in version: 4.2.0
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: ![gif3](https://i.imgur.com/2Cv1dRL.gif)
  - [x] Steps to recreate: 
  1. upload MP3 file to the Media Library (as Editor or Administrator).
  2. Insert an Audio Playlist in a Post containing this MP3 (Create Audio
Playlist).
  - [x] Affected source code:
    - [Link 3](https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php) 

## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
