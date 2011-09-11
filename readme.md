About
=====

webcl-manifest is a very simple tool that simply enumerates all the compute
platforms and devices that are available on your system and displays all
platform and device parameters for each of them. It will give you a quick
overview of the capabilities of your system to help in debugging. MIT licensed.

Live version is available at: [http://www.aapolaitinen.fi/webcl-manifest/](http://www.aapolaitinen.fi/webcl-manifest/)

Troubleshooting
===============

Installing the Samsung WebGL prototype
--------------------------------------

This shouldn't pose any problems, as long as the system requirements are met
(Mac OS X 10.6 or 10.7). Just grab the latest tarball from
[Google Code](http://code.google.com/p/webcl/downloads/list), extract it and
read the build instructions from `README.txt`. The only thing the readme doesn't
mention is that you need to download and install Xcode 4 from the App Store
first.

The build should finish in less than an hour with a relatively recent MacBook.

Error messages
--------------

### Your browser does not seem to support WebCL.

This error indicates that the `WebCLComputeContext` global isn't available.
Either your browser really doesn't support WebCL at all or you are using the
[Nokia WebCL prototype extension](http://webcl.nokiaresearch.com/), which has a
different API from the [Samsung WebCL prototype](http://code.google.com/p/webcl/)
that this tool is targeting.

After you managed to get the Samsung prototype to compile, did you remember to
start Safari using `./Tools/Scripts/run-safari`? Also note that this may result
in multiple copies of Safari running, so be careful to use the correct one.

I don't currently have 32-bit Windows or Linux installed, so I can't work
towards supporting the Nokia prototype. Also, the Samsung prototype is closer to
WebGL, so its API is more likely to win anyway.

### Could not create WebCL compute context.

This error indicates that the `WebCLComputeContext` global is available, but for
some reason attempt to create a new context returned `null`.