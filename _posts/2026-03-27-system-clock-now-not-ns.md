---
layout: post
title: "system_clock::now() 不保证纳秒精度"
tags: [cpp, chrono, trading]
---

最近遇到一个小问题，和 `std::chrono::system_clock::now()` 有关。我们在接收行情的时候，会用 `system_clock::now()` 记一个本地接收时间。这段代码在旧环境里一直没暴露什么问题。后来换了一套环境，突然发现很多条行情的接收时间戳是一样的。一开始还以为是消息被批量处理，或者落库的时候时间被截断了，查完才发现不是。

真正的问题是：我们一直默认 `system_clock::now()` 能给到纳秒级的时间，但它其实没有这个保证。我们当时会把 `now().time_since_epoch()` 转成 `nanoseconds` 存下来。但这一步只是换了一个表示单位，底层时钟是不是真的能分辨到纳秒，是另一回事。C++ 标准没有要求 `system_clock::now()` 必须是纳秒级。`system_clock::duration` 的精度本身也是实现定义的，最后能细到什么程度，还是要看标准库、操作系统和实际时钟源。

参考：

- [cppreference: std::chrono::system_clock](https://en.cppreference.com/w/cpp/chrono/system_clock)
- [cppreference: std::chrono::system_clock::now](https://en.cppreference.com/w/cpp/chrono/system_clock/now)
- [C++ draft: system clock overview](https://eel.is/c++draft/time.clock.system.overview)
