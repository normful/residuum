# Design philosophy

This needs to be maintainable for at least another 50 years.

There should be validator programs to perform checks on file formatting, file naming, and folder structure.

Assume that you will forget all the minor details about how files should be organized. Let the validators enforce and remind you. The validators should have good error messages.

Friction for writing should be low. There is no point if writing things becomes so difficult that you don't want to write anything.

Those tools should still be functional within 10 years. If you expect them to be deprecated in the coming decades, check them in.

All code dependencies should be checked in.

Compiled binaries for validators should be checked in.

Validators should run as pre-commit hooks.

## Why public?

Maybe other people might find my text useful. Maybe not.

## Should you have stuff marked as private?

Well, if the source of this repository is going to be public, then I guess that's not possible.

Maybe you should consider multiple levels of privacy:

1. totally public
    - turned into a blog post
    - source posted publicly
2. semi-public
    - not turned into a blog post
    - source posted publicly
3. private
    - I don't think you should be keeping such text in such a place.
        - But if I get this stuff all up and running, then the tools and process would be great for it.
        - Perhaps private stuff should be integratable with the public stuff, but kept in a separate submodule repo
            - This should be a separate task










# Tracking TODOs for this little project

Use this Trello board, to keep it simple: <https://trello.com/b/VM40FvzR/residuum>








# Content categories

- HOW-TO's for myself:
    - because I always forget details about things

- HOW-TO's for myself that other people might find useful

- Sharing opinions

- Answering questions that people often ask me
    - I don't like answering the same questions over and over again. Examples:
        - Why do you study Japanese?
        - How do you study Japanese?
        - Why are you vegetarian?
    - I'm tired of answering them and I also cannot remember, on the spot, all of the entire details that I'd like to include in such a response.
    - This will provide a place for answering such common questions so that I can just say: Go visit this URL and read it for yourself.

- Travel log
    - I can't remember anything I do on trips.
    - Photos are currently the only way I can vaguely remember.
    - It would be nice to have a place where I can jot down notes about things like places I went to.

- Drafts for restaurant reviews
    - Maybe really good ones should be turned into Yelp and/or Google Maps reviews

- Drafts for book reviews
    - I don't enjoy writing thorough reviews of books
    - It's nice to at least summarize them

- Reflections on books
    - Note that you should not conflate book reviews or reflections with highlighting of books

- Dumping ground for practicing writing Japanese
    - I don't do enough sentence construction practice
    - This would be a nice place to keep such text, and allow native speakers to look it over

- It's nice to write things down more often. I know I'll forget. I always do. It's nice to keep a record for later.










# Markdown file format

The flavour of Markdown used should support:
- Japanese text
- Japanese ruby furigana
    - Why?
        - I can't read all kanji yet.
    - What about machine generated ruby?
        - Maybe this is best for the long run, to avoid having to manually write ruby, and also to ensure that it can scale with your Japanese level.
- English correction text
    - Why?
        - So that I can write things for 
- Code blocks
- Easy inline color marking of text
- be readable 
- images
    - the image files themselves should be in the same folder for each entry
- MP3 clips
    - Sometimes I might record myself or somebody speaking
        - It 
- videos... maybe? (lower priority)
    - I don't even record videos usually.
    - But that might be different in the future.
- inline LaTeX
    - maybe? I haven't written much inline LaTeX for a few years now
    - MathJax? 
    - make this a low priority requirement

If you need to a custom dialect of Markdown for yourself, you should somehow fork existing Markdown-to-AST tool that is easy to use and maintain.










# Folder structure

- Files associated with each text should be in the same folder as the Markdown file.

- The folder structure should explain the layout of the content.

- You should assume that this will forever be a Git LFS repository

- there should only be 1 markdown file in each folder
    - write a validator that checks this

- folder name:
    - What should you call the folders?
    - Numbered?
    - Dated?
    - I think it makes sense to date them
        - But what about content that spans more than one day?
    - What about using some unique hyphenated-freeform-ascii-slug-as-the-folder-name
        - That would reduce friction of writing
            

- subfolders?
    - Yes, this must be supported.









# Metadata file

- Format:
    - probably YAML

- created at and last updated at timestamps should be inferred from Git history
    - but what about bulk updates that modify the Git history?
        - I don't want to manually have to type out timestamps

- What other metadata do you want?
    - Language? EN/JP?
    - Location? I don't see how this is useful. Maybe it might be useful for posts written during some trip, so that a map can be inferred, given some time range.















## Examples to be inspired from

- https://jvns.ca/
    - I like how the table of contents is front and center
    - I also like how posts are short and sweet

- http://matt.might.net/articles/
- http://www.kalzumeus.com/
- https://sanctum.geek.nz/arabesque/
- http://pgbovine.net/writings.htm
- https://wiki.archlinux.org
    - This begs the question: What should you do about knowledge that should be placed in some wiki?

- http://vimcasts.org/
    - How about tutorial videos? What format should they be in?

- Terminal session recordings?

- look at other people's personal wikis









# Blog generation (supplementary)

- There should be a way to indicate that a given folder should be turned into a blog post


- TODO: Look at general patterns and features of Jekyll and its leading alternatives
    - I'm leaning towards doing this with Hugo
        - Why?
            - Many users
            - Written in Go
            - Kubernetes chose to move their docs from Jekyll to Hugo https://kubernetes.io/blog/2018/05/05/hugo-migration/

## Generated HTML

All generated HTML should be checked in.

## Static website

The output should be a simple static website, to keep it fast and easy to maintain and deploy.

## Deployment

Keep it simple. Maybe use AWS Lambda or some serverless stack so you don't have to maintain any infrastructure.

## Code Syntax Highlighting

### Special syntax highlighting for corrected English or Japanese text (low priority)

(MAYBE, and LOW PRIORITY) You might need to write your own thing that understands stuff like:

```encor
```

```jpcor
```


## CSS

- I don't really care too much about how it visually looks at this point. Worry about that later.

- It should eventually look nice on mobile web

## Table of contents

- The table of contents should be ENTIRELY generated. You should not have to manually edit a table of contents.

## Comments

Disable them. I don't want to have to moderate comments.

## RSS Feed (low priority)

It should exist and it should be wonderful to use.




# Blog generation: posting to Medium (alternative idea)






---------------------

# Less important stuff

### Content: Tags

- Should tags somehow be generated from each article? I don't see the benefit of this.
- Perhaps the text should just be optimized somehow so that it's easily Google-searchable.

### Blog: CDN

### Blog: SEO

- Maybe some kind of metadata generator is good? I don't know.

## Supplementary: PDF generation

- You'll probably use pandoc to do this, since you've been using it for years now.
- The PDF should be downloadable from the blog

## Supplementary: Slide generation (really, really low priority)

- I don't know if this is strictly necessary, but keep it in mind.
