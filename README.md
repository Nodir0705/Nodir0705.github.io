# nodir0705.github.io

Resume site of Nodirbek Makhtumov, AI/ML engineer (computer vision on edge hardware, NPU deployment, RAG, network security), served by GitHub Pages at https://nodir0705.github.io/.

- `index.html`: the whole page
- `assets/Nodirbek_Makhtumov_Resume.pdf`, `assets/Nodirbek_Makhtumov_Resume_KR.pdf`, `assets/Nodirbek_Makhtumov_Resume_UZ.pdf`: the English, Korean and Uzbek resumes behind the download buttons
- `assets/Nodirbek_Makhtumov_Portfolio.pdf`, `assets/Nodirbek_Makhtumov_Portfolio_KR.pdf`, `assets/Nodirbek_Makhtumov_Portfolio_UZ.pdf`: the English, Korean and Uzbek portfolios
- `assets/css/`: theme from [yakhyo.github.io](https://github.com/yakhyo/yakhyo.github.io) (MIT, see `assets/css/LICENSE`)

The PDFs are generated from HTML sources kept in a separate local `resume` project: run `./build.sh` there, then copy the files from its `dist/` into `assets/`.

To update, replace a PDF or edit `index.html` and push to `main`. Pages redeploys in a minute or two.
