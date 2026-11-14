# nodir0705.github.io

Personal site of Nodirbek Makhtumov, AI/ML engineer in Daejeon, Korea (computer vision on edge hardware, NPU deployment, RAG, network security): https://nodir0705.github.io/

Pages: a landing page with an experience timeline, Projects, About and Resume. Built with Jekyll 4 and deployed by GitHub Actions (`.github/workflows/deploy.yml`), so the repository's Pages source must be set to "GitHub Actions".

## Run locally

Requires Ruby 3.3 and Bundler.

```bash
bundle install
bundle exec jekyll serve          # http://localhost:4000
```

Or with Docker, without a local Ruby:

```bash
docker run --rm -v "$PWD":/srv -w /srv -p 4000:4000 ruby:3.3 \
  bash -lc "bundle install && bundle exec jekyll serve --host 0.0.0.0"
```

Check the production build and links the same way CI does:

```bash
JEKYLL_ENV=production bundle exec jekyll build
bundle exec htmlproofer ./_site --disable-external --allow-hash-href --ignore-empty-alt
```

## Where things live

- `_config.yml`: name, description, profile links and the landing-page typewriter titles
- `_data/timeline.yml`: the experience timeline on the landing page
- `_data/projects.yml`: the cards on /projects/
- `_pages/`: About, Projects and Resume
- `assets/Nodirbek_Makhtumov_Resume.pdf`, `assets/Nodirbek_Makhtumov_Resume_KR.pdf`, `assets/Nodirbek_Makhtumov_Resume_UZ.pdf`: the English, Korean and Uzbek resumes
- `assets/Nodirbek_Makhtumov_Portfolio.pdf`, `assets/Nodirbek_Makhtumov_Portfolio_KR.pdf`, `assets/Nodirbek_Makhtumov_Portfolio_UZ.pdf`: the English, Korean and Uzbek portfolios

The PDFs are generated from HTML sources kept in a separate local `resume` project: run `./build.sh` there, then copy the files from its `dist/` into `assets/` under the same names (the profile README links to these URLs).

## Credits

Design, layouts, styles and scripts are from [yakhyo.github.io](https://github.com/yakhyo/yakhyo.github.io) (MIT), with personal content replaced.

## License

[MIT](LICENSE)
