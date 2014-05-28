platform :ios, '7.0'

# Inform CocoaPods that we use some custom build configurations
xcodeproj 'CrushBootstrap',
    'Debug_Staging'   => :debug,   'Debug_Production'   => :debug,
    'Test_Staging'    => :debug,   'Test_Production'    => :debug,
    'AdHoc_Staging'   => :release, 'AdHoc_Production'   => :release,
    'Profile_Staging' => :release, 'Profile_Production' => :release,
    'Distribution'    => :release

# Crush Utility Belt
pod 'Sidecar', :git => 'https://github.com/crushlovely/Sidecar.git'

# Update checker for Installr (installrapp.com)
pod 'Aperitif', :git => 'https://github.com/crushlovely/Aperitif.git'

# Logging & Analytics
pod 'CocoaLumberjack'
pod 'CrashlyticsFramework'
pod 'CrashlyticsLumberjack'

# Networking
pod 'AFNetworking'

# Various goodies
pod 'libextobjc'      # Useful macros and some craziness
pod 'PixateFreestyle' # Style your app with CSS
pod 'FormatterKit'    # For all your string formatting needs
pod 'Asterism'        # Nice & fast collection operations

# You may want...
#pod 'OMPromises'     # Promises/A+-alike
#pod 'Mantle'         # Github's model framework
#pod 'SSKeychain'     # Go-to keychain wrapper
#pod 'DateTools'      # Datetime heavy lifting



# Testing necessities
target 'Specs', :exclusive => true do
  pod 'Specta'
  pod 'Expecta'
  pod 'OCMockito'

# pod 'OHHTTPStubs'
end


# Copy the license settings plist over to our project
post_install do |installer|
    if Dir.exists? 'CrushBootstrap/Resources/Settings.bundle'
        require 'fileutils'
        FileUtils.cp_r('Pods/Pods-Acknowledgements.plist', 'CrushBootstrap/Resources/Settings.bundle/Acknowledgements.plist', :remove_destination => true)
    end

    FileUtils.cp_r('Pods/Pods-Environment.h', 'CrushBootstrap/Other-Sources/Pods-Environment.h', :remove_destination => true)
end
