# markepalmer.github.io

A permanent redirect to my resume site, nothing else.

`https://markepalmer.github.io` is the address that goes on applications, LinkedIn, and my
resume PDF. It forwards to wherever the site is actually hosted, which today is Cloud Run:

```
https://resume-chatbot-328203120319.us-east1.run.app
```

## Why this exists

A Cloud Run hostname is derived from the service name, project, and region. Change any of
the three, or leave Cloud Run, and every link already sitting in a sent application breaks,
with no way to redirect from a hostname I no longer control. This repo is the stable
indirection: if the hosting moves, I edit one URL here and every link ever sent still lands
in the right place.

## Changing the target

The destination appears in four places in `index.html`: the `canonical` link, the
`http-equiv="refresh"` meta, the visible `<a href>` and its link text, and the
`location.replace` call. Update all of them together.

Source for the site itself lives in `markepalmer/resume-chatbot`.
