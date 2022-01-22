# redmine-polish-locale

To jest pomocnicze repozytorium do tłumaczenia [Redmine](https://www.redmine.org/) na język polski. 
Branch [`upstream`](https://github.com/rob006/redmine-polish-locale/tree/upstream) zawiera oryginalne angielskie frazy,
branch [`master`](https://github.com/rob006/redmine-polish-locale/tree/master) zawiera polskie tłumaczenie.
Możesz porównać obie wersje [tutaj](https://github.com/rob006/redmine-polish-locale/compare/upstream..master).

## Przydatne polecenia

Aktualizacja brancha `upstream`:

```console
git checkout upstream
wget -O locale.yml https://svn.redmine.org/redmine/trunk/config/locales/en.yml
git add locale.yml
git commit -m "Update translations from upstream."
git push
```

Wygenerowanie patcha do przesłania na [redmine.org](https://www.redmine.org/projects/redmine/issues/new?tracker_id=3):

```console
svn co https://svn.redmine.org/redmine/trunk/ redmine
cd redmine/config/locales/
wget -O pl.yml https://raw.githubusercontent.com/rob006/redmine-polish-locale/master/locale.yml
cd ../..
svn diff > ../pl.patch
cp config/locales/pl.yml ../pl.yml
```
