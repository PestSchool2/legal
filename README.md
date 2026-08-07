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
python3 docs/legal/publish-site.py --record   # in the app repo, after the push lands
```

Copy the files in rather than replacing the tree — this README is not generated and would be lost.

**Do not skip the last line.** The app repository's unit suite compares the sources against the
fingerprint `--record` writes, so it stays red until a wording change has actually been published
here. That check exists because this site once spent six days serving a privacy policy older than
the app, which nobody could have noticed: a stale legal site returns 200 and renders perfectly.
Recording without pushing is the one way to defeat it, and it is a lie the check cannot catch.

`CNAME` pins the custom domain. GitHub Pages unsets the domain when that file disappears, so it is
regenerated on every publish; do not delete it.
