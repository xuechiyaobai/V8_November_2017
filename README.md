V8_November_2017

Some V8 vuls which they were fixed in about November 2017.

CVE-2017-5070

https://bugs.chromium.org/p/chromium/issues/detail?id=722756

Chrome version: 58.0.3029.110 Channel: stable

This problem belongs to the crankshaft,in the latest V8 version(16th May 2017)(use crankshaft to JIT),I can reproduce this issue.At this version,the chrome use crankshaft to JIT.

CVE-2017-15399

https://bugs.chromium.org/p/chromium/issues/detail?id=776677

https://chromium.googlesource.com/v8/v8.git/+/5f960dfc06a7c95af69e2b09f772b2280168469b

VULNERABILITY DETAILS

This is a Use After Free Vul in V8.More information please see the html file.

VERSION

Chrome Version: 62.0.3202.62 Stable (32bit)

Operating System: [Windows 10 1703 64bit] 8G Memory


CVE-2017-15428

https://bugs.chromium.org/p/chromium/issues/detail?id=782145

https://chromium.googlesource.com/v8/v8.git/+/55a98076827edac8eba775f8025df3749bcd8367

VULNERABILITY DETAILS

There is a type confusion problem in the String.prototype.replace runtime call.If we change the RegExp type(from fast regexp to slow regexp),we will also go to the fast regexp code path.At last,this will cause OOB Read Write of the lastIndex.

VERSION

Chrome Version: 62.0.3202.89 Stable 64 bit

Operating System: Windows 10 1703 64bit

REPRODUCTION CASE

In the debug build,it will crash in CSA_ASSERT(this, IsFastRegExp(context, regexp)) of the function TF_BUILTIN(RegExpReplace, RegExpBuiltinsAssembler);

In the release build,it will crash in the address 0x300000008,and please note that,this addresss we can control it through control the lastIndex value.

CVE-2017-XXXX(duplicate with chromium worker)

https://bugs.chromium.org/p/chromium/issues/detail?id=782102

https://chromium.googlesource.com/v8/v8.git/+/b60438869987952083597c2ce55a9abdba19d557

VULNERABILITY DETAILS

This is a OOB Read Write Problem in V8:WebAssembly.

VERSION

Chrome Version: 62.0.3202.89 Stable Operating System: Windows 10 1703 64bit

REPRODUCTION CASE
