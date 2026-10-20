# go-dsp.github.io

The go-dsp landing page (Hugo), served at <https://go-dsp.github.io/>.

The layout is the go-* family template, imported as the Hugo module
[`github.com/go-fleettools/landingkit`](https://github.com/go-fleettools/landingkit)
(pinned in `go.mod`; `kit.go` keeps `go mod tidy` from dropping the
requirement): the shared stylesheet, theme toggle, fork ribbon and icons come
from the module, `layouts/index.html` is this organization's page, and
`[params.brand]` in `hugo.toml` is generated from the logo's gradient:

```sh
go run github.com/go-fleettools/landingkit/cmd/landingkit brand static/img/logo.svg
hugo server
```

| Workflow | What |
| --- | --- |
| `hugo.yml` | builds on pull requests; builds and deploys to Pages on `main` |
| `ci.yml` | the site builds and names every repository; the landingkit requirement survives `go mod tidy` |
| `links.yml` | every link and image of the built site resolves (`landingkit links`) |

The documentation lives at <https://go-dsp.github.io/docs/>
([go-dsp/docs](https://github.com/go-dsp/docs)).

BSD-3-Clause.
