# -*- coding: utf-8 -*-
$:.unshift("/Library/RubyMotion/lib")
require 'motion/project/template/ios'

begin
  require 'bundler'
  Bundler.require
rescue LoadError
end

Motion::Project::App.setup do |app|
  # Use `rake config' to see complete project settings.
  app.name = 'no_headers_issue'

  app.pods do 
    pod 'NSData+MD5Digest'
    pod "MBProgressHUD"
    # pod "ASIHTTPRequest" # For downloading images and storing them locally
    pod "PHFRefreshControl" # For pull-to-refresh
    pod "JSONKit" # For store favorite notes
    pod "SDWebImage" # Async load of images from URL
    pod "CKCalendar" # For calendar controls
  end
end
