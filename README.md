<a id="readme-top"></a>

[![Tech][tech-shield]][tech-url]
[![project_license][license-shield]][license-url]
[![Contributors][contributors-shield]][contributors-url]

<div align="center">
<h3 align="center">text2cad</h3>

  <p align="center">
    Fine-tune a lightweight Large Language Model (3B–7B parameters) to generate parametric 3D CAD models directly from natural language prompts.
     <br />
    <a href="https://github.com/remiboivin021/text2cad/issues/new?template=bug_report.yml">Report Bug</a>
    &middot;
    <a href="https://github.com/remiboivin021/text2cad/issues/new?template=feature_request.yml">Request Feature</a>
  </p>
</div>


<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>


## About The Project

This project focuses on fine-tuning a lightweight Large Language Model (3B–7B parameters) to generate parametric 3D CAD models directly from natural language prompts.
By leveraging structured CAD datasets (such as Text2CAD) and executable Python CAD libraries (CadQuery / build123d), the system translates text descriptions into valid, exportable 3D geometry (`.step` / `.stl`). To ensure geometric validity, the generation pipeline incorporates an automated self-correction loop that validates code execution and catches topological errors in a headless environment.

### Key Highlights

- **Lightweight & Efficient**: Built around compact code-oriented LLMs (e.g., Qwen2.5-Coder) trained via QLoRA/Unsloth on Kaggle GPUs.
- **Executable Output**: Generates clean, parametric Python scripts rather than raw meshes, making the output easily editable in standard CAD software.
- **Automated Validation**: Features a Python-based orchestration loop that compiles the generated script, verifies manifoldness, and feeds runtime errors back to the model for self-repair.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Built With

* [![Python][Python]][Python-url]


<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ROADMAP -->
## Roadmap

* [ ] **v0.1.0 – Data Pipeline & Preprocessing** 
  * [ ] Download and inspect the Text2CAD dataset
  * [ ] Convert raw CAD command sequences into executable Python scripts (`CadQuery` / `build123d`)
  * [ ] Clean, validate, and split the dataset (train/val/test)

* [ ] **v0.2.0 – Baseline Model Fine-Tuning (MVP)** 
  * [ ] Configure the QLoRA training pipeline with Unsloth on Kaggle
  * [ ] Fine-tune a lightweight code LLM (3B / 7B parameters)
  * [ ] Export LoRA adapters and run initial prompt-to-code inference

* [ ] **v0.3.0 – Orchestration & Self-Correction Loop** 
  * [ ] Build a headless Python execution sandbox to run generated CAD scripts
  * [ ] Implement an iterative retry loop feeding OpenCASCADE/syntax errors back to the LLM
  * [ ] Add automated `.step` and `.stl` file exports for valid solids

* [ ] **v0.4.0 – Evaluation & Visual Verification** 
  * [ ] Benchmark compilation pass rates and geometric accuracy (Chamfer Distance / IoU)
  * [ ] Add headless multi-view rendering (`pyvista` / `trimesh`)
  * [ ] Integrate a VLM judge to verify visual alignment with the input prompt

* [ ] **v1.0.0 – Interactive UI & Public Release** 
  * [ ] Build a web interface (Gradio or Streamlit) with an embedded 3D viewer
  * [ ] Package the inference pipeline and publish model weights on Hugging Face
  * [ ] Complete documentation and usage examples

See the [open issues](https://github.com/remiboivin021/text2cad/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also open an issue with the matching form (Feature Request, Task, Spike, R&D, Documentation or Bug Report).
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch from `develop` (`git checkout -b feat/amazing-feature`)
3. Commit your Changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the Branch (`git push origin feat/amazing-feature`)
5. Open a Pull Request against `develop`

For more information, read [CONTRIBUTING](./CONTRIBUTING.md), [GIT](./GIT.md) and [DEV](./DEV.md).

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Top contributors:

<a href="https://github.com/remiboivin021/text2cad/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=remiboivin021/text2cad" alt="contrib.rocks image" />
</a>


## License

Distributed under the [GPL-3.0](LICENSE) license.

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Contact

[Rémi Boivin](https://www.linkedin.com/in/remi-boivin-embedded-edge-ai-engineer/) - [remiboivin021@gmail.com](mailto:remiboivin021@gmail.com) - [text2cad](https://github.com/remiboivin021/text2cad)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[tech-shield]: https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54
[tech-url]: https://www.python.org/
[contributors-shield]: https://img.shields.io/github/contributors/remiboivin021/text2cad.svg?style=for-the-badge
[contributors-url]: https://github.com/remiboivin021/text2cad/graphs/contributors
[stars-shield]: https://img.shields.io/github/stars/remiboivin021/text2cad.svg?style=for-the-badge
[stars-url]: https://github.com/remiboivin021/text2cad/stargazers
[license-shield]: https://img.shields.io/github/license/remiboivin021/text2cad.svg?style=for-the-badge
[license-url]: https://github.com/remiboivin021/text2cad/blob/main/LICENSE
[Python]: https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54
[Python-url]: https://www.python.org/
