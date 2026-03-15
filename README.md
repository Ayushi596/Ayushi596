<p align="center">
  <img src="https://capsule-render.vercel.app/api?text=Hi, I'm Ayushi! 👋&animation=fadeIn&type=waving&color=gradient&height=120"/>
</p>

<p align="center">
  <img src="http://googleusercontent.com/image_collection/image_retrieval/13988308300268300064" width="600" alt="Lofi Coding Aesthetic" />
</p>

---

### 🧬 About Me
```yaml
profile:
  role: AI Engineering Student (3rd Year)
  academics: Integrated M.Tech | CGPA 8.93
  focus: Physics-Informed ML & Fluid Dynamics
  learning: Soft Computing, Fuzzy Logic & Genetic Algorithms
projects:
  - Blender CFD Toolkit: Automating 3D CAD to OpenFOAM workflows.
  - Stock Trend Prediction: Comparative analysis using LSTM and Bi-LSTM models.
  - Image Captioning Model: Developing vision-to-language deep learning architectures.

```

---

🛠️ Technical Stack
<p align="left">
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="40" height="40" alt="python" />
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg" width="40" height="40" alt="pytorch" />
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg" width="40" height="40" alt="tensorflow" />
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/blender/blender-original.svg" width="40" height="40" alt="blender" />
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="40" height="40" alt="docker" />
<img src="https://www.google.com/search?q=https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" width="40" height="40" alt="linux" />
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" width="40" height="40" alt="bash" />
</p>

📈 Contribution History
<p align="center">
<img src="https://www.google.com/search?q=https://github-readme-stats.vercel.app/api%3Fusername%3DREPLACE_WITH_YOUR_USERNAME%26show_icons%3Dtrue%26theme%3Dradical" alt="Stats" />
</p>

<p align="center">
<img src="https://www.google.com/search?q=https://github.com/REPLACE_WITH_YOUR_USERNAME/REPLACE_WITH_YOUR_USERNAME/blob/output/github-contribution-grid-snake.svg" alt="Snake animation" />
</p>

<p align="center">
<img src="https://www.google.com/search?q=https://capsule-render.vercel.app/api%3Ftype%3Drect%26color%3Dgradient%26height%3D2%26section%3Dfooter"/>
</p>


*Note: Remember to replace `REPLACE_WITH_YOUR_USERNAME` with your actual GitHub username.*

-----

## Step 3: Enable the Snake Animation

To make the snake game actually appear, you need to set up a "GitHub Action":

1.  Click the **Actions** tab at the top of your repository.
2.  Click **"Set up a workflow yourself"**.
3.  Name the file `main.yml`.
4.  Paste this code:

<!-- end list -->

```yaml
name: generate animation

on:
  schedule:
    - cron: "0 */12 * * *" 
  workflow_dispatch:
  push:
    branches:
    - main

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
