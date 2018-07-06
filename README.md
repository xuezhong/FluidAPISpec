# PaddlePaddle Fluid API specification file

We currently enforce Fluid API cannot be modified without the permission of
multiple developers.

This repo used to save API.spec file. If you found a CI error like below

```
[06:42:34]	API Difference is: 
[06:42:34]	+ paddle.fluid.InferenceTranspiler.__init__ 
```

You need to send a PR to this repo to change `API.spec` before.


## How to generate `API.spec`

You need to build and install CUDA version of paddle, and generate `API.spec` by

```bash
python ${PADDLE_REPO_ROOT}/tools/print_signatures.py 'paddle.fluid' > API.spec
```

## How to rerun CI

The CI in the `Paddle` repo must be rerun by the generated API.spec in your own
repo. You can rerun CI job by setting the job parameter like

| | |
|--- | --- |
| `API_SPEC_URL` | `https://raw.githubusercontent.com/reyoung/FluidAPISpec/feature/add_readme.md_and_generate_new_spec/API.spec` |

The URL can be obtained in your github repo and just click RAW file.

The PR of `API.spec` must be merged to this repo, then merge the PR in the `Paddle` right now.

