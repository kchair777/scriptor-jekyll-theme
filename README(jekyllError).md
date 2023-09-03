# jekyll 오류 해결 (부제: github 블로그 만들기)

[jekyll Error](https://velog.io/@minji-o-j/jekyll-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0)

[velog.io소개](https://velog.io/)

깃허브 블로그 만드는데 오류가 너무 많이 나서 쓰는 글

전체적인 flow는 여기와 여기2블로그를 참조했는데 설명과는 다르게 오류가 너무 많이나서...

우선 다 설치한 후 실행 명령어는...

jekyll serve
❌ Bundler could not find compatible versions for gem "bundler"
C:\Users\minji\Documents\GitHub\paper_review>bundle exec jekyll serve
Bundler could not find compatible versions for gem "bundler":
  In Gemfile:
    bundler (~> 2.1.4)

  Current Bundler version:
    bundler (2.2.26)

Your bundle requires a different version of Bundler than the one you're running, and that version could not be found.
❕ 해결 방법
C:\Users\minji\Documents\GitHub\paper_review>gem install bundler:2.1.4
C:\Users\minji\Documents\GitHub\paper_review>bundle _2.1.4_ update
❌ Jekyll 4.2.0 Please append --trace to the serve command
                    ------------------------------------------------
      Jekyll 4.2.0   Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
                    ------------------------------------------------
❕ 해결 방법
C:\Users\minji\Documents\GitHub\paper_review>bundle exec jekyll serve --trace
❌ cannot load such file -- webrick
C:/Ruby30-x64/lib/ruby/gems/3.0.0/gems/jekyll-4.2.0/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
❕ bundle add webrick
를 하면 해결된다고 하지만... (보통은...)
++ 수정 이건 오타 낸거였음 webric아니고 webrick가 맞다..

❌ Could not find gem 'webric x64-mingw32'
C:\Users\minji\Documents\GitHub\paper_review>bundle add webric
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Could not find gem 'webric x64-mingw32' in any of the gem sources listed in your
Gemfile.
❕ 설치
C:\Users\minji\Documents\GitHub\paper_review>gem install webrick
아니면

https://rubygems.org/gems/webrick
여기서 명령어로 버전 맞춰줘도 된다.

❕ gem 버전 업데이트
C:\Users\minji\Documents\GitHub\paper_review>bundle exec jekyll serve
다시 build

C:\Users\minji\Documents\GitHub\paper_review>jekyll build
❕ (다시) bundle add webric
C:\Users\minji\Documents\GitHub\paper_review>bundle add webrick
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
Resolving dependencies...
Fetching gem metadata from https://rubygems.org/..........
Fetching gem metadata from https://rubygems.org/.
...생략
✅ 끝!
C:\Users\minji\Documents\GitHub\paper_review>bundle exec jekyll serve
Configuration file: C:/Users/minji/Documents/GitHub/paper_review/_config.yml
            Source: C:/Users/minji/Documents/GitHub/paper_review
       Destination: C:/Users/minji/Documents/GitHub/paper_review/_site
 Incremental build: disabled. Enable with --incremental
      Generating...
                    done in 1.352 seconds.
  Please add the following to your Gemfile to avoid polling for changes:
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
 Auto-regeneration: enabled for 'C:/Users/minji/Documents/GitHub/paper_review'
    Server address: http://127.0.0.1:4000/just-the-docs/
  Server running... press ctrl-c to stop.
잘 실행된다

profile
𝐌𝐢𝐧𝐣𝐢