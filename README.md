rubymotion_no_headers_issue
===========================

## UPDATE: found a fix:

[https://github.com/johnezang/JSONKit/pull/140](https://github.com/johnezang/JSONKit/pull/140)

```ruby
pod 'JSONKit',:git => 'git@github.com:matsu911/JSONKit.git'
```


Steps to replicate issue:

1. Run `bundle`
2. Run `rake pod:install`
3. Run `bundle exec rake`

Output:

```
     Build ./build/iPhoneSimulator-7.0-Development
     Build /Users/jh/.gem/ruby/2.0.0/gems/teacup-1.0.4/lib/../vendor/TeacupDummy
     Build vendor/Pods
Build settings from command line:
    ARCHS = i386
    CONFIGURATION_BUILD_DIR = /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/.build
    IPHONEOS_DEPLOYMENT_TARGET = 7.0
    SDKROOT = iphonesimulator7.0

=== BUILD TARGET Pods-CKCalendar OF PROJECT Pods WITH CONFIGURATION Release ===

Check dependencies

Libtool .build/libPods-CKCalendar.a normal i386
    cd /Users/jh/Code/iOS/no_headers_issue/vendor/Pods
    setenv IPHONEOS_DEPLOYMENT_TARGET 7.0
    setenv PATH "/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin:/Applications/Xcode.app/Contents/Developer/usr/bin:/Users/jh/.gem/ruby/2.0.0/bin:/Library/Ruby/Gems/2.0.0/bin:/Users/jh/.rubies/ruby-2.0.0-p247/bin:/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/bin:/Applications/Postgres.app/Contents/MacOS/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/heroku/bin:/Users/jh/Scripts/winscripts"
    /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/libtool -static -arch_only i386 -syslibroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk -L/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/.build -filelist /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-CKCalendar.build/Objects-normal/i386/Pods-CKCalendar.LinkFileList -framework CoreGraphics -framework Foundation -framework QuartzCore -framework UIKit -o /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/.build/libPods-CKCalendar.a

=== BUILD TARGET Pods-JSONKit OF PROJECT Pods WITH CONFIGURATION Release ===

Check dependencies

CompileC build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Objects-normal/i386/JSONKit.o JSONKit/JSONKit.m normal i386 objective-c com.apple.compilers.llvm.clang.1_0.compiler
    cd /Users/jh/Code/iOS/no_headers_issue/vendor/Pods
    setenv LANG en_US.US-ASCII
    setenv PATH "/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/usr/bin:/Applications/Xcode.app/Contents/Developer/usr/bin:/Users/jh/.gem/ruby/2.0.0/bin:/Library/Ruby/Gems/2.0.0/bin:/Users/jh/.rubies/ruby-2.0.0-p247/bin:/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/bin:/Applications/Postgres.app/Contents/MacOS/bin:/usr/local/bin:/usr/local/sbin:/usr/bin:/bin:/usr/sbin:/sbin:/usr/local/heroku/bin:/Users/jh/Scripts/winscripts"
    /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/clang -x objective-c -arch i386 -fmessage-length=125 -fdiagnostics-show-note-include-stack -fmacro-backtrace-limit=0 -fcolor-diagnostics -std=gnu99 -fmodules -fmodules-cache-path=/var/folders/n9/b86gln3175589bgj2rh5jw8h0000gn/C/com.apple.DeveloperTools/5.0.1-5A2053/Xcode/ModuleCache -Wno-trigraphs -fpascal-strings -Os -Wno-missing-field-initializers -Wno-missing-prototypes -Werror=return-type -Wno-implicit-atomic-properties -Werror=deprecated-objc-isa-usage -Werror=objc-root-class -Wno-receiver-is-weak -Wno-arc-repeated-use-of-weak -Wno-missing-braces -Wparentheses -Wswitch -Wunused-function -Wno-unused-label -Wno-unused-parameter -Wunused-variable -Wunused-value -Wempty-body -Wuninitialized -Wno-unknown-pragmas -Wno-shadow -Wno-four-char-constants -Wno-conversion -Wconstant-conversion -Wint-conversion -Wbool-conversion -Wenum-conversion -Wshorten-64-to-32 -Wpointer-sign -Wno-newline-eof -Wno-selector -Wno-strict-selector-match -Wundeclared-selector -Wno-deprecated-implementations -DCOCOAPODS=1 -DNS_BLOCK_ASSERTIONS=1 -isysroot /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk -fexceptions -fasm-blocks -fstrict-aliasing -Wprotocol -Wdeprecated-declarations -g -Wno-sign-conversion -fobjc-abi-version=2 -fobjc-legacy-dispatch -mios-simulator-version-min=7.0 -iquote /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Pods-JSONKit-generated-files.hmap -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Pods-JSONKit-own-target-headers.hmap -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Pods-JSONKit-all-target-headers.hmap -iquote /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Pods-JSONKit-project-headers.hmap -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/.build/include -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/BuildHeaders -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/BuildHeaders/JSONKit -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/CKCalendar -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/JSONKit -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/MBProgressHUD -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/NSData+MD5Digest -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/PHFRefreshControl -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/Headers/SDWebImage -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/DerivedSources/i386 -I/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/DerivedSources -F/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/.build -DNS_BLOCK_ASSERTIONS=1 -include /var/folders/n9/b86gln3175589bgj2rh5jw8h0000gn/C/com.apple.DeveloperTools/5.0.1-5A2053/Xcode/SharedPrecompiledHeaders/Pods-JSONKit-prefix-ecalllmqpgwwtbeqvkfqhoxiqost/Pods-JSONKit-prefix.pch -MMD -MT dependencies -MF /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Objects-normal/i386/JSONKit.d --serialize-diagnostics /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Objects-normal/i386/JSONKit.dia -c /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m -o /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Objects-normal/i386/JSONKit.o
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:745:245: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...but range length is %lu", NSStringFromClass([self class]), NSStringFromSelector(_cmd), NSMaxRange(range)];        }
                         ~~~                                                                ^~~~~~~~~~~~~~~~~
                                                                                            (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:746:245: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...%lu) beyond bounds (%lu)",                          NSStringFromClass([self class]), NSStringFromSelector(_cmd), NSMaxRange(range)...
     ~~~                                                                                                              ^~~~~~~~~~~~~~~~~
                                                                                                                      (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:746:264: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...%lu)",                          NSStringFromClass([self class]), NSStringFromSelector(_cmd), NSMaxRange(range), count]; }
     ~~~                                                                                                             ^~~~~
                                                                                                                     (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:752:184: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...%@]: index (%lu) beyond bounds (%lu)", NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, coun...
                 ~~~                                                                                     ^~~~~~~~~~~
                                                                                                         (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:752:197: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...(%lu) beyond bounds (%lu)", NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count]; }
                          ~~~                                                                              ^~~~~
                                                                                                           (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:773:209: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...(%lu) beyond bounds (%lu)",          NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count ...
      ~~~                                                                                              ^~~~~~~~~~~
                                                                                                       (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:786:209: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...(%lu) beyond bounds (%lu)",          NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count]; }
      ~~~                                                                                              ^~~~~~~~~~~
                                                                                                       (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:786:222: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...bounds (%lu)",          NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count]; }
             ~~~                                                                                       ^~~~~
                                                                                                       (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:795:209: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...(%lu) beyond bounds (%lu)",          NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count]; }
      ~~~                                                                                              ^~~~~~~~~~~
                                                                                                       (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:795:222: warning: values of type 'NSUInteger' should not be
      used as format arguments; add an explicit cast to 'unsigned long' instead [-Wformat]
  ...bounds (%lu)",          NSStringFromClass([self class]), NSStringFromSelector(_cmd), objectIndex, count]; }
             ~~~                                                                                       ^~~~~
                                                                                                       (unsigned long)
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:680:12: warning: 'isa' is deprecated
      [-Wdeprecated-declarations]
    array->isa      = _JKArrayClass;
           ^
In module 'ObjectiveC' imported from /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:108:
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/usr/include/objc/NSObject.h:53:11: note:
      'isa' declared here
    Class isa  OBJC_ISA_AVAILABILITY;
          ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:680:5: error: assignment to Objective-C's isa is deprecated
      in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
    array->isa      = _JKArrayClass;
    ^    ~~~~~~~~~~~~
    object_setClass( ,             )
In module 'ObjectiveC' imported from /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:108:
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/usr/include/objc/NSObject.h:53:11: note:
      instance variable is declared here
    Class isa  OBJC_ISA_AVAILABILITY;
          ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:929:17: warning: 'isa' is deprecated
      [-Wdeprecated-declarations]
    dictionary->isa      = _JKDictionaryClass;
                ^
In module 'ObjectiveC' imported from /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:108:
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/usr/include/objc/NSObject.h:53:11: note:
      'isa' declared here
    Class isa  OBJC_ISA_AVAILABILITY;
          ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:929:5: error: assignment to Objective-C's isa is deprecated
      in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
    dictionary->isa      = _JKDictionaryClass;
    ^         ~~~~~~~~~~~~
    object_setClass( ,                       )
In module 'ObjectiveC' imported from /Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:108:
/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator7.0.sdk/usr/include/objc/NSObject.h:53:11: note:
      instance variable is declared here
    Class isa  OBJC_ISA_AVAILABILITY;
          ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2596:39: warning: bitmasking for introspection of
      Objective-C object pointers is strongly discouraged [-Wdeprecated-objc-pointer-introspection]
  if(JK_EXPECT_F(((NSUInteger)object) & 0x1)) { workAroundMacOSXABIBreakingBug = YES; goto slowClassLookup; }
                 ~~~~~~~~~~~~~~~~~~~~ ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:197:53: note: expanded from macro 'JK_EXPECT_F'
#define JK_EXPECT_F(cond)               JK_EXPECTED(cond, 0U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2598:31: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
       if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.stringClass))     { isClass = JKClassString;     }
                              ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2598:23: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
       if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.stringClass))     { isClass = JKClassString;     }
                      ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2599:31: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.numberClass))     { isClass = JKClassNumber;     }
                              ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2599:23: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.numberClass))     { isClass = JKClassNumber;     }
                      ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2600:31: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.dictionaryClass)) { isClass = JKClassDictionary; }
                              ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2600:23: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.dictionaryClass)) { isClass = JKClassDictionary; }
                      ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2601:31: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.arrayClass))      { isClass = JKClassArray;      }
                              ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2601:23: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.arrayClass))      { isClass = JKClassArray;      }
                      ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2602:31: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.nullClass))       { isClass = JKClassNull;       }
                              ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2602:23: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
  else if(JK_EXPECT_T(object->isa == encodeState->fastClassLookup.nullClass))       { isClass = JKClassNull;       }
                      ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:196:53: note: expanded from macro 'JK_EXPECT_T'
#define JK_EXPECT_T(cond)               JK_EXPECTED(cond, 1U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2605:171: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  ...if(workAroundMacOSXABIBreakingBug == NO) { encodeState->fastClassLookup.stringClass     = object->isa; } isClass = JK...
                                                                                                     ~~^~~
                                                                                               object_getClass( )
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2606:171: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  ...if(workAroundMacOSXABIBreakingBug == NO) { encodeState->fastClassLookup.numberClass     = object->isa; } isClass = JK...
                                                                                                     ~~^~~
                                                                                               object_getClass( )
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2607:171: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  ...if(workAroundMacOSXABIBreakingBug == NO) { encodeState->fastClassLookup.dictionaryClass = object->isa; } isClass = JK...
                                                                                                     ~~^~~
                                                                                               object_getClass( )
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2608:171: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  ...if(workAroundMacOSXABIBreakingBug == NO) { encodeState->fastClassLookup.arrayClass      = object->isa; } isClass = JK...
                                                                                                     ~~^~~
                                                                                               object_getClass( )
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2609:171: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
  ...if(workAroundMacOSXABIBreakingBug == NO) { encodeState->fastClassLookup.nullClass       = object->isa; } isClass = JK...
                                                                                                     ~~^~~
                                                                                               object_getClass( )
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2791:40: error: direct access to Objective-C's isa is
      deprecated in favor of object_getClass() [-Werror,-Wdeprecated-objc-isa-usage]
            if(JK_EXPECT_F((keyObject->isa      != encodeState->fastClassLookup.stringClass)) && JK_EXPECT_F(([keyObj...
                                       ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:197:53: note: expanded from macro 'JK_EXPECT_F'
#define JK_EXPECT_F(cond)               JK_EXPECTED(cond, 0U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:2791:29: error: assignment to Objective-C's isa is
      deprecated in favor of object_setClass() [-Werror,-Wdeprecated-objc-isa-usage]
            if(JK_EXPECT_F((keyObject->isa      != encodeState->fastClassLookup.stringClass)) && JK_EXPECT_F(([keyObj...
                            ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:197:53: note: expanded from macro 'JK_EXPECT_F'
#define JK_EXPECT_F(cond)               JK_EXPECTED(cond, 0U)
                                                    ^
/Users/jh/Code/iOS/no_headers_issue/vendor/Pods/JSONKit/JSONKit.m:195:65: note: expanded from macro 'JK_EXPECTED'
#define JK_EXPECTED(cond, expect)       __builtin_expect((long)(cond), (expect))
                                                                ^
fatal error: too many errors emitted, stopping now [-ferror-limit=]
13 warnings and 20 errors generated.

** BUILD FAILED **


The following build commands failed:
	CompileC build/Pods.build/Release-iphonesimulator/Pods-JSONKit.build/Objects-normal/i386/JSONKit.o JSONKit/JSONKit.m normal i386 objective-c com.apple.compilers.llvm.clang.1_0.compiler
(1 failure)
rake aborted!
Command failed with status (65): [/usr/bin/xcodebuild -project "Pods.xcodepr...]
/Library/RubyMotion/lib/motion/project/vendor.rb:176:in `block in build_xcode'
/Library/RubyMotion/lib/motion/project/vendor.rb:144:in `chdir'
/Library/RubyMotion/lib/motion/project/vendor.rb:144:in `build_xcode'
/Library/RubyMotion/lib/motion/project/vendor.rb:43:in `build'
/Library/RubyMotion/lib/motion/project/builder.rb:60:in `block in build'
/Library/RubyMotion/lib/motion/project/builder.rb:59:in `each'
/Library/RubyMotion/lib/motion/project/builder.rb:59:in `build'
/Library/RubyMotion/lib/motion/project/app.rb:76:in `build'
/Users/jh/.gem/ruby/2.0.0/gems/motion-cocoapods-1.4.0/lib/motion/project/cocoapods.rb:53:in `build_with_cocoapods'
/Library/RubyMotion/lib/motion/project/template/ios.rb:42:in `block (2 levels) in <top (required)>'
/Library/RubyMotion/lib/motion/project/template/ios.rb:55:in `block in <top (required)>'
Tasks: TOP => build:simulator
(See full trace by running task with --trace)
➜  no_headers_issue git:(master) ✗
```
