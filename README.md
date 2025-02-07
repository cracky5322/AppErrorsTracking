# AppErrorsTracking

[![Blank](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/KitsunePie/AppErrorsTracking)
[![Blank](https://img.shields.io/badge/license-AGPL3.0-blue)](https://github.com/KitsunePie/AppErrorsTracking/blob/master/LICENSE)
[![Blank](https://img.shields.io/badge/version-v1.1-green)](https://github.com/KitsunePie/AppErrorsTracking/releases)
[![Blank](https://img.shields.io/github/downloads/KitsunePie/AppErrorsTracking/total?label=Release)](https://github.com/KitsunePie/AppErrorsTracking/releases)
[![Blank](https://img.shields.io/github/downloads/Xposed-Modules-Repo/com.fankes.apperrorstracking/total?label=LSPosed%20Repo&logo=Android&style=flat&labelColor=F48FB1&logoColor=ffffff)](https://github.com/Xposed-Modules-Repo/com.fankes.apperrorstracking/releases)
<br/><br/>
English | [简体中文](https://github.com/KitsunePie/AppErrorsTracking/blob/master/README-zh-CN.md)

Added more features to app's errors dialog, fixed custom rom deleted dialog, the best experience to Android developer.

This project is an Xposed module that can be used in any Android system, currently only tested in **LSPosed**.

This module is specially designed for Android developers.

When it is possible that the computer cannot be connected and ADB cannot be performed, this module can be used to quickly capture any errors of
any installed apps, so as to quickly locate the problem.

The error log of apps crashing is an invaluable asset for developers. If you are not a developer, you can still install this module to provide
developers with more exception information to quickly solve problems.

> Minimum support Android 8.1

## Project Reason

I really can't understand, except for MIUI (except stable version), Android ROMs in mainland China have chosen to delete the dialog box (FC
dialog) of apps crashes. I thought this was always a feature until I decompiled the system. frame, only to confirm that it was indeed deleted.

Does the product manager think that it is the best solution to let the user not see the error, and the apps will crash and exit directly, or is
there another **hidden secret**?

## Woking Principle

Unlike `Thread.UncaughtExceptionHandler`, we use the native method to capture apps errors in all directions by injecting the system framework,
without generating additional registration monitoring, which is better than the original exception monitoring in performance.

At the same time, the system-level exception capture can also capture the `stack trace` of the native platform.

## Precautions

The errors captured by the system natively can only be errors that are not handled by the apps itself. If the apps itself has a
custom `Thread.UncaughtExceptionHandler`
Similar to **Bugly** to automatically collect errors, the system cannot obtain whether the apps actually crashes **(FC)**.

## Features List

- Completely replaces the system's apps errors dialog

- Logs exceptions for each apps and persists until restart

- Copy, share, export errors stack trace functions

- Errors history record function, which can be entered through the notification bar tile "errors history record" and the main interface of the
  module

- Apps errors statistics function

- Errors display function for multi-process apps

## Translation contribution

Contributions to this project are welcome to translate it into your country's language.

## License

- [AGPL-3.0](https://www.gnu.org/licenses/agpl-3.0.html)

```
Copyright (C) 2019-2022 Fankes Studio(qzmmcn@163.com)

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
```

Powered by [YukiHookAPI](https://github.com/fankes/YukiHookAPI)

Copyright © 2019-2022 Fankes Studio(qzmmcn@163.com)