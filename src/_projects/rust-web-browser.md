---
layout: project
title: Browser From Scratch
summary: Curiosity-driven project dive into how the web works by reimplementing a minimal browser from scratch in Rust.
date: 2025-07-01
weight: 1
cover: /assets/projects/browser/cover.png   # optional
status: in-progress                          # draft | in-progress | shipped
core_tech: [Rust]
tags: [systems, networking, parsing, rendering]
course:
  name: "Web Browser Engineering"
  link: "https://browser.engineering/"
why:
  spark: "Most people take browsers for granted; I wanted to see the gears move."
  journey: "Followed the book but rewrote examples in Rust, making deliberate design choices and notes."
  takeaway: "I now reason about performance/architecture tradeoffs across parsing → layout → paint."
links:
  notion_overview: "https://notion.so/your-overview"
  repo: "https://github.com/you/rust-web-browser"
  demo: ""   # optional
chapters:
  - title: "URLs & Fetch"
    notion: "https://notion.so/urls-notes"
    repo: "https://github.com/you/rust-web-browser/tree/main/ch01"
  - title: "HTML Parsing"
    notion: "https://notion.so/html-parsing"
    repo: "https://github.com/you/rust-web-browser/tree/main/ch02"
  - title: "Layout & Painting"
    notion: "https://notion.so/layout-paint"
    repo: "https://github.com/you/rust-web-browser/tree/main/ch03"
---

Short intro paragraph if you want one. You can also leave body empty and let the layout handle rendering.
