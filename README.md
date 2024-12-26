<p align="center">
  Do something excellent.<br/>
  It isn't about the money.<br/>
  It isn't about status.<br/>
  It's about the journey.<br/>
<p align="center">:wrench: 𝙻𝚊𝚗𝚐𝚞𝚊𝚐𝚎𝚜 & 𝚃𝚘𝚘𝚕𝚜 :wrench:</p>

<p>
  Shameless plug for C. Until Unicode is verifiably safely implemented at a low enough level,
  disable unicode. 7-bit ASCII only. One way is to swap the existing calls to the lowest-level
  API with something that NOPs. The second way is having the source for every program on your
  computer and removing or fixing their implementations. One of these days I'll enable it,
  but you can do absolute black magic with unicode. It's friggen cool to use as an exploit
  mechanism, but I don't want it running on my everyday system.

  <strong>PS: Hanging on to magic string that does this. Definitely don't email me your PGP key for
  requests for it. It's really neat and I wish I could, but I fear this one. It will be up
  as soon as *recompiles <strong>everything from source*</strong>. Probably released
  simultaneously with write-up when I get around to debugging this.</strong>

Exactly how low-level it is:

  As an example (this is a consistent fail within a c++ program, so this is in the compiler/
  implementation of language itself). These are the lowest level I've found this exploit and
  I've seen it crash things like Qt5 - so at the application/library level instead of language:

```bash
Administrator@o1 UCRT64 /b/apps/windows/security/keepassxc
$ python3 ~/unicode.py
🚗🐎🔋📎
b'\xff\xfe=\xd8\x97\xde=\xd8\x0e\xdc=\xd8\x0b\xdd=\xd8\xce\xdc'
ðððð
牅潲⁲桷汩⁥敲摡湩⁧桴⁥慤慴慢敳›湉慶楬⁤牣摥湥楴污⁳敷敲瀠潲楶敤Ɽ瀠敬獡⁥牴⁹条
b'\xff\xfe<strong>Error while reading the database: Invalid credentials were provided, please try ag'</strong>
牅潲⁲桷汩⁥敲摡湩⁧桴⁥慤慴慢敳›湉慶楬⁤牣摥湥楴污⁳敷敲瀠潲楶敤Ɽ瀠敬獡⁥牴⁹条

Administrator@o1 UCRT64 /b/apps/windows/security/keepassxc
$ cat ~/unicode.py
```

And the source. This is the string segfaulting keepassxc in my tests. Not sure if order matters, lifes been weird and scary.

```python
#!/usr/bin/env python3

STR1 = u'\uD83D\uDE97\uD83D\uDC0E\uD83D\uDD0B\uD83D\uDCCE' # surrogatepass example - need to read more about them homestly and honestly can't remember where I got this from but I don't think that matters.
STR2 = u'\xf0\x9f\x9a\x97\xf0\x9f\x90\x8e\xf0\x9f\x94\x8b\xf0\x9f\x93\x8e'
STR3 = u'\u7245\u6F72\u2072\u6877\u6C69\u2065\u6572\u6461\u6E69\u2067\u6874\u2065\u6164\u6174\u6162\u6573\u203A\u6E49\u6176\u696C\u2064\u7263\u6465\u6E65\u6974\u6C61\u2073\u6577\u6572\u7020\u6F72\u6976\u6564\u2C64\u7020\u656C\u7361\u2065\u7274\u2079\u6761' # Result of lookup in the table that is fucking baller
STR4 = u"\xce\x94\xc3\xb6\xd8\xb6\n" # Password typed on screen by automation
STR5 = u"\xe7\xa7\x98\xe5\xaf\x86" # Key of lookup being passed into KeepassXC command

print(STR1.encode('utf-16', 'surrogatepass').decode('utf-16'))
print(STR1.encode('utf-16', 'surrogatepass'))
print(STR2.encode('utf-16').decode('utf-16'))
print(STR3.encode('utf-16').decode('utf-16'))
print(STR3.encode('utf-16'))
print(STR3.encode('utf-16').decode('utf-16'))

```

<p align="center">
  <a href="https://www.gnu.org/software/bash/"> 
    <img src="https://img.shields.io/badge/-BASH-000000?style=for-the-badge&logo=BASH">
  </a> 
  <img src="https://img.shields.io/badge/-Linux-000000?style=for-the-badge&logo=Linux"> 
  <img src="https://img.shields.io/badge/-C-000000?style=for-the-badge&logo=C">
  <img src="https://img.shields.io/badge/-C++-000000?style=for-the-badge&logo=C++">
  <img src="https://img.shields.io/badge/-Go-000000?style=for-the-badge&logo=Go">
  <a href="https://python.org/"> 
    <img src="https://img.shields.io/badge/-Python-000000?style=for-the-badge&logo=Python">
  </a>
  <img src="https://img.shields.io/badge/-Java-000000?style=for-the-badge&logo=Java">
  <img src="https://img.shields.io/badge/-JavaScript-000000?style=for-the-badge&logo=JavaScript"> 
  <img src="https://img.shields.io/badge/-TypeScript-000000?style=for-the-badge&logo=TypeScript"> 
  <img src="https://img.shields.io/badge/-Node.js-000000?style=for-the-badge&logo=Node.js"> 
  <img src="https://img.shields.io/badge/-Markdown-000000?style=for-the-badge&logo=Markdown"> 
</p> 

<p align="center"> 
  <img src="https://img.shields.io/badge/-Shell-000000?style=for-the-badge&logo=Shell"> 
  <img src="https://img.shields.io/badge/-SQL-000000?style=for-the-badge&logo=mySQL"> 
</p>
<p align="center">𝙾𝚟𝚎𝚛𝚟𝚒𝚎𝚠</p>
  <div align="center">
    <kbd><kbd><kbd><kbd><kbd><kbd><kbd><kbd><kbd><kbd>
      <img src="https://github-readme-stats.vercel.app/api?username=neuroretransmit&show_icons=true&count_private=true&theme=chartreuse-dark"/>
  </div>
      
  <img align="left" style="float:right; margin:30px;" src="https://github-readme-stats.vercel.app/api/top-langs/?username=neuroretransmit&theme=radical&layout=compact">
</p>
<br><br><br>
