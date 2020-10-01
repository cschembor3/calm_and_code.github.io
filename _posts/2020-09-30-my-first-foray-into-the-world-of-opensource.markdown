---
layout: post
title: My first foray into the world of open-source
date: 2020-09-30 23:35:00 -0400
categories: opensource gleam
---

# Open-source and why it matters

<p><em>If you don't want to read about me gushing over open-source, you can <a href="#gleam-section">skip</a> over this.</em></p>

Open-source software is software which is not only free to use, but also free to modify. This is
due to the "open" nature of it, where the source code is freely and widely available, either via
being hosted in a public source control repository (such as on GitHub or Gitlab), by direct
download, or some other means of distribution. Typically this software is released under some
<a href="https://www.gnu.org/licenses/copyleft.en.html" target="_blank">copyleft</a> license
(such as GPL), or a less restrictive license such as Apache or MIT.

I use open-source software every day, both in personal practice and professional practice.
Whether it be my browser (<a href="https://searchfox.org" target="_blank">FireFox</a>), my
terminal (<a href="https://github.com/gnachman/iTerm2" target="_blank">iTerm2</a>), my
Latex editor 
    (<a href="https://pages.uoregon.edu/koch/texshop/anniversary.html" target="_blank">TeXShop</a>),
even my favorite way to pass the time and exercise my brain a bit 
    (<a href="https://lichess.org/source" target="_blank">Lichess</a>).
And that's not even getting into what I use every day professionally
    (<a href="https://github.com/xamarin/xamarin-macios" target="_blank">Xamarin.iOS</a>,
    <a href="https://github.com/mono/mono" target="_blank">Mono</a>,
    <a href="https://www.sqlite.org/src/doc/trunk/README.md" target="_blank">SQLite</a>).

While the free and readily accessible nature of open-source is wonderful, what really excites
me about it is the multitude of oppotunities which it opens up. By making source code readily
available **as well as** open for modification, suddenly tons of possibilites are created. One
piece of open-source software that I use daily is 
<a href="https://github.com/neovim/neovim" target="_blank">neovim</a>, a fork
of vim (which itself is an improvement over vi). This type of software development can be
looked at as a form of iterative development, but if there's something you don't like, you now
have the ability, as a user, to change it!

I've always been curious about open-source, and recently I began to (finally) contribute to a few open-source
projects.

<h1 id="gleam-section">Gleam</h1>

<a href="https://gleam.run" target="_blank">Gleam</a> is a statically-typed, functional programming language that runs on top of the 
<a href="https://en.wikipedia.org/wiki/BEAM_(Erlang_virtual_machine)" target="_blank">BEAM</a>. It compiles to Erlang, which in turn
compiles to byte code to run on the virtual machine. The language was created and is maintained by 
<a href="https://github.com/lpil" target="_blank">Louis Pilfold</a>.

Gleam first came onto my radar through the GitHub Explorer feature, which I really never use, but wanted
to try it out. I've been interested in Elixir for a while, which also runs on top of the BEAM, so I'm
guessing that played a part in my discovery of Gleam. After going through the readme and the docs, I really
was drawn in. What immediately caught my eye was the syntax. It felt much more familiar coming from a
C#/Java/[*insert industry-popular language here*], as opposed to erlang or elixir (I don't have
a ruby background).

In addition to this, the various <a href="https://github.com/gleam-lang" target="_blank">gleam-lang</a>
repositories all seemed well-organized to me, which included the categorization of the issues being tracked
on GitHub. Tags such as "good first issue" and "help wanted" made it helpful when looking at something to
contribute. I felt welcome as a newcomer to contribute, and really wanted to.

# My first contributions to Gleam

The first issue I picked up was in the gleam language repo, and was very simple - rename a field in one of
the types in the rust code (the gleam compiler is written in rust). While it wasn't much, 
<a href="https://github.com/gleam-lang/gleam/pull/750" target="_blank">my first open-source
contribution was officially merged in on August 11, 2020</a>. The community, and especially Louis himself,
was so welcoming that it really just made me want to contribute more and be a part of this growing community.

#### Http

After exploring some of the other repositories under gleam-lang organization, I decided to start contributing
a bit to the http library for gleam. Here's a quick changelog of what I've contributed here so far:
- <a href="https://github.com/gleam-lang/http/pull/13" target="_blank">Add missing unit tests</a>
- <a href="https://github.com/gleam-lang/http/pull/18" target="_blank">Update code to use new update record syntax</a>
- <a href="https://github.com/gleam-lang/http/pull/23" target="_blank">Add get_req_origin function</a>

#### Stdlib

I also added a few contributions to the gleam standard library:
- <a href="https://github.com/gleam-lang/stdlib/pull/102" target="_blank">Add a few simple math functions to the float module</a>

# Conclusion

I still haven't done very much in terms of code contributions, however I plan on continuing this as I really enjoy it.
Open-source contributing has become something that I look forward to doing. The gleam community has really
played a large role in making me feel this way - everyone has been so welcoming and accepting, it really
feels like everyone is valued and enjoys what they are doing. My experience has only strengthened my thoughts
on open-source.

