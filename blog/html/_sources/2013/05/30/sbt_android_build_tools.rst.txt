SBT Android and the New Build Tools
=====================================

I updated my Android platform tools to vesion 17 and installed the new Build Tools.  These new build tools break the sbt android plugin.  This is because they moved some of the tooling to live under a new "build-tools" directory.  

To fix this I wrote a ruby script to create a set of sim links from the build tools back to platform tools.  All you need to have to run this is:

.. code-block:: bash

  $ export ANDROID_SDK_HOME = <Where you have the SDK Installed>
  $ curl https://gist.github.com/cajun-code/5674831/raw/13adb1670b5c7ee763f51a730e62f5feb4924c4a/patch_android.rb | ruby
  
The code is:

.. code-block:: ruby

  Dir.chdir(File.absolute_path("#{ENV['ANDROID_SDK_HOME']}/build-tools/17.0.0/"))
  Dir.glob("*").each{|x| system "ln -s #{ENV['ANDROID_SDK_HOME']}/build-tools/17.0.0/#{x} #{ENV['ANDROID_SDK_HOME']}/platform-tools/#{x}"}


.. author:: default
.. categories:: android
.. tags:: sbt, android, ruby
.. comments::
