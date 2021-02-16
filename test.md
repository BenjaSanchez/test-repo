When releasing, please follow these steps:

1. Create a pull request from `devel` to `master`, indicating all new features/fixes/etc. and referencing every previous pull request included (examples [here](https://github.com/SysBioChalmers/GECKO/releases)). Tip: if any [issue](https://github.com/SysBioChalmers/GECKO/issues) gets solved in the release, write in the pull request description "Closes #X", where "X" is the issue number. That way the issue will be automatically closed after merge.
2. Wait at least a day + 1 approval + passing CI.
3. Bump to the new version x.y.z. For this, create in `devel` a single commit `chore: version X.Y.Z` with:
    * Updated `/geckopy/HISTORY.rst` by putting at the top the same description as in the PR from step 1 (use https://pandoc.org/try for transforming markdown to ReSTructured text).
	  * Updated version in:
      - `/docs/conf.py` (lines 57 & 59).
      - `/geckopy/setup.cfg` (line 2).
      - `/geckopy/setup.py` (line 22).
      - `/geckopy/geckopy/__init__.py` (line 10).
	  * Updated `/README.rst` date (line 14).
4. Push the commit and confirm that the CI tool is still passing.
5. Merge PR -> confirm that the CI tool is still passing.
6. In `master`, create LOCALLY a tag `vX.Y.Z` on the latest merge commit + push said tag (in git kraken or with `git push origin vX.Y.Z`) -> confirm that the CI tool is still passing and geckopy deploys to PyPI (check [here](https://pypi.org/project/geckopy/)).
7. Make the new release at GitHub (https://github.com/SysBioChalmers/GECKO/releases/new), using the proper tag and with the same description as the corresponding PR from step 1.
