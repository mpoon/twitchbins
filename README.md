#How To Integrate the Twitch Broadcasting SDK

###PC


- You will need 2012 or later to build the code. Open the twitchsdk.sln in Visual Studio and select the appropriate config to build. If you want to statically link the SDK code into your game select one of the non-dll configs; otherwise select the dll configs and build.

- Add the SDK include directory to your game's include path and include twitchsdk.h

- Add the SDK lib directory to your game's linker include path and add the appropriate twitchsdk lib to your linker input

- Copy all the DLL's for your platform (win32 or x64) from twitchsdk/intel/bin, twitchsdk/ffmpeg/bin/, twitchsdk/libmp3lame/bin and libcurl/bin to your executable's directory. If using the DLL, also copy the twitchsdk DLL that you built.

- Copy twitchsdk\libcurl\cacert\curl-ca-bundle.crt to where-ever (full path will be provided to the sdk functions)

- If you get compiler errors about inttypes.h create one (in twitchsdk/include is fine) and just #include \<stdint.h\> in it  

- In order to stream to your channel, you'll need to supply the SDK with your Twitch user name and password, as well as your application's Client ID and Client Secret. To get your Client ID and Secret:
	- Go to twitch.tv and log into your account
	- From the top right, click on your channel name and select Settings
	- Select Applications
	- Under Developer Applications, select Register your application
	- Enter your application name and website and click Register
	- On the next page you'll see your Client ID and Client Secret
	- If you've already registered, you can just click Edit to see your Client ID and Client Secret
 	- **IMPORTANT** 
  		- You'll need to provide us with this Client ID (e-mail brooke@twitch.tv) so that we can  whitelist it prior to streaming (no need to do this for the Client Secret)
        - If your endpoint is api.justin.tv you have googled and stumbled across the old api we are currently depracating

###iOS  
- Copy the libtwitchsdk.a library from the ioslibs.tar file under the twitchbins repo to a location that you'll include in your project's library path  
- Copy twitchsdk\libcurl\cacert\curl-ca-bundle.crt to where-ever (full path will be provided to the sdk functions)  
- Either add the SDK include directory to your project's include path or copy the header files there to a folder that's in your include path
- Include twitchsdk.h
- Minimum supported iOS deployment target is iOS 5.0
- Please note that you cannot build for the simulator (only building for the device is supported)
- Make sure you have the following frameworks included: AVFoundation, Security, CoreVideo, CoreMdia
- If you get STL linker errors you'll need to set your project setting for "C++ Standard Library" to "libc++ (LLVM C++ standard library with C++11 support)." This won't work for iOS < 5.0
- Follow the steps for getting your client ID and Secret and whitelisting it as described in the PC section above
- For audio capture to work, you must initialize your audio session with the kAudioSessionCategory_PlayAndRecord category

[![githalytics.com alpha](https://cruel-carlota.pagodabox.com/da4459390fa5c35119bd2f8c398e89f4 "githalytics.com")](http://githalytics.com/twitchsdk/twitchbins)
