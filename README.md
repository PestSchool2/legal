# legal

Public legal documents for A&K apps and services. Served by GitHub Pages at
**https://legal.thepestpic.com**, which is the privacy policy and account-deletion URL registered
in the App Store and Google Play listings for PestPic. A dead link there is a policy violation, so
treat this repository as production.

## Do not edit the pages here

`privacy.md`, `terms.md`, `index.md`, `delete-account.md` and `_config.yml` are **generated**. The
wording lives in the PestPic app repository, under `docs/legal/`, alongside the Korean and Spanish
translations and the copies in `strings.xml` that the in-app Legal screen renders. Editing a page
here would make the site disagree with the app, and the next publish would overwrite the edit
anyway.

To change the wording, edit `docs/legal/*.en.md` in the app repository and republish:

```
python3 docs/legal/publish-site.py --out /tmp/legal-site
cp /tmp/legal-site/* /path/to/this/checkout/
git commit -am "publish: <what changed>" && git push
```

Copy the files in rather than replacing the tree — this README is not generated and would be lost.

`CNAME` pins the custom domain. GitHub Pages unsets the domain when that file disappears, so it is
regenerated on every publish; do not delete it.
