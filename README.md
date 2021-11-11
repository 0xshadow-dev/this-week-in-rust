This Week in Rust
=================

Content for [this-week-in-rust.org](http://this-week-in-rust.org). Made available under CC-BY-SA.

All code Copyright 2014 Ember Arlynx, made available under [the MIT
license](http://mit-license.org/).

## PRs for next issue are now being accepted

To propose content for inclusion in the next newsletter (found in the `drafts/`
folder), create a new [Pull Request](https://github.com/rust-lang/this-week-in-rust/pulls) updating the relevant section in the 
draft.

Alternately, tweet us [@thisweekinrust](https://twitter.com/thisweekinrust).

### What do we look for when considering whether to include something in This Week in Rust?

This Week in Rust is intended to highlight the incredible work of the Rust Community. 

What we are generally looking for includes:

* how-to intros (and advanced deep dives) into Rust concepts and areas
* Rust walkthroughs that explain concepts in different ways than well known resources like [the Rust book](https://doc.rust-lang.org/stable/book/), [Rustlings](https://github.com/rust-lang/rustlings), and [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
* updates on tooling when in long form or framed as a tutorial (for more details, see what we are not looking for below)
* Rust-related podcast episodes
* Rust-related screenshots and videos
* Rust meetup recordings
* Rust meetup announcements
* Presenter slide decks on Rust
* Observations and thoughts on Rust and the Rust community
* Calls for participation in Rust open source projects
* Rust job announcements
* and more!

What we are generally NOT looking for includes:

* Anything that violates the [Rust Community Code of Conduct](https://www.rust-lang.org/policies/code-of-conduct)
* Rants or anything degrading to any part or member of the Community. Rather than submitting an article about what is wrong with something, we would much rather you write something that explains how you'd make it better.
* Duplicates of recent posts (even with the wording changed slightly)
* Links to crates or GitHub repos without some sort of context. We would much rather you submit a blog post introducing your project and how a Rust user might use it (and what it would help them do) and/or what you learned about Rust in the process of writing the project.
* Anything behind a paywall (this includes Medium's paid article mechanism)
* Anything that requires information to be shared/captured (like an email address) in order to access

These are meant to be guidelines, if you are ever not sure about whether something should be included please feel free to open a pull request anyway and we can discuss it!

The editors of This Week in Rust do reserve the right to make the decision about whether to include something or not, but we intend to do so in a way that is as transparent as possible.

## Link style guidelines:

Links should use the most canonical form. For example, if `example.tech` redirects to `www.example.com`, then the latter is preferred.

Links should not contain unnecessary tracking parameters, e.g. `utm_source`, `utm_campaign`.

Some prefixes are used, and should be placed to the left of the link.
- `[video]` for videos
- `[audio]` for podcasts or other audio.
- `[series]` for articles that are one of a series.
- 2-letter languages codes (e.g. `[ZH]`, `[ES]`, `[FR]`) for content in a language other than English.

## How I get PR lists:

```
git log --author=bors --since='MM/DD/YYYY 12:00PM' --until='MM/DD/YYYY 12:00PM' --pretty=oneline > ~/entropy/twir.txt
# edit in vim to get rid of everything but PR number, copy into clipboard
for pr in $(xsel -ob); do firefox https://github.com/mozilla/rust/pull/$pr; sleep 0.07; done
# wait a long time...
# write TWIR
```

Alternatively use GitHub search:

```
https://github.com/rust-lang/rust/pulls?q=is%3Apr+is%3Amerged+updated%3A2014-11-03..2014-11-10
```

## How I get new contributors:

Use the included `new_contribs.sh` script:

  new_contribs.sh 6/21/2014

## Building

Ensure you have SASS installed. The easiest way to get it is via `gem`, the
Ruby package manager.

```
env SASS_BIN=$HOME/.gem/ruby/*/bin/sass pelican content -s pelicanconf.py
```

### To build the newsletter

* Generate the HTML
  ```
  TWIR_NEWSLETTER_THEME=1 pelican --delete-output-directory content
  ```
* Copy the HTML and inline CSS at http://zurb.com/ink/inliner.php - (MailChimp's inliner doesn't remove the CSS from `<head>`).
* Send the newsletter (we currently use MailChimp).
