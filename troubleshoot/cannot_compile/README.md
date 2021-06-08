## Trouble Description

This suddenly happened to me one day on one of my Arch Linux machine.

The story goes like this: I edited and compiled a beautiful document in $\LaTeX$ on a Debian machine. And
then when I shifted to one Arch Linux machine, the `.tex` suddenly couldn't compile! The error message
went like the following:
```
~/.../phunc20/self-intro ❯❯❯ pdflatex slide.tex
This is pdfTeX, Version 3.141592653-2.6-1.40.22 (TeX Live 2021/Arch Linux) (preloaded format=pdflatex)
 restricted \write18 enabled.
---! /var/lib/texmf/web2c/pdftex/pdflatex.fmt made by different executable version
(Fatal format file error; I'm stymied)
```


## Troubleshoot
I ended with the following solution:

01. Uninstall `texlive` in `pacman`. There are a number of them -- **Uninstall them all**. Some of them might depend on others, so the order of uninstallation would have to be taken care of.
02. The next step should be to reinstall by `pacman -S texlive-most`, right? Well, that is basically correct.  However, if you simply do that, your machine will complain like this:
  ```bash
  ~/.../phunc20/self-intro ❯❯❯ pacman -S texlive-most
  :: There are 12 members in group texlive-most:
  :: Repository extra
     1) texlive-bibtexextra  2) texlive-core  3) texlive-fontsextra  4) texlive-formatsextra  5) texlive-games
     6) texlive-humanities  7) texlive-latexextra  8) texlive-music  9) texlive-pictures  10) texlive-pstricks
     11) texlive-publishers  12) texlive-science
  
  Enter a selection (default=all):
  resolving dependencies...
  looking for conflicting packages...
  
  Packages (17) perl-file-which-1.24-2  potrace-1.16-2  t1lib-5.1.2-8  texlive-bin-2021.58686-3  zziplib-0.13.72-1
                texlive-bibtexextra-2021.58697-1  texlive-core-2021.58710-2  texlive-fontsextra-2021.58704-1
                texlive-formatsextra-2021.57972-1  texlive-games-2021.56833-1  texlive-humanities-2021.58589-1
                texlive-latexextra-2021.58668-2  texlive-music-2021.58331-1  texlive-pictures-2021.58558-1
                texlive-pstricks-2021.58293-1  texlive-publishers-2021.58683-1  texlive-science-2021.58667-1
  
  Total Installed Size:  2188.21 MiB
  
  :: Proceed with installation? [Y/n]
  (17/17) checking keys in keyring                                      [######################################] 100%
  (17/17) checking package integrity                                    [######################################] 100%
  (17/17) loading package files                                         [######################################] 100%
  (17/17) checking for file conflicts                                   [######################################] 100%
  error: failed to commit transaction (conflicting files)
  texlive-core: /etc/texmf/web2c/updmap-hdr.cfg exists in filesystem
  texlive-core: /usr/bin/a2ping exists in filesystem
  texlive-core: /usr/bin/a5toa4 exists in filesystem
  texlive-core: /usr/bin/adhocfilelist exists in filesystem
  texlive-core: /usr/bin/afm2afm exists in filesystem
  ...
  texlive-core: /usr/bin/typeoutfileinfo exists in filesystem
  texlive-core: /usr/bin/updmap exists in filesystem
  texlive-core: /usr/bin/updmap-sys exists in filesystem
  texlive-core: /usr/bin/updmap-user exists in filesystem
  texlive-core: /usr/bin/vpl2ovp exists in filesystem
  texlive-core: /usr/bin/vpl2vpl exists in filesystem
  texlive-core: /usr/bin/xhlatex exists in filesystem
  texlive-core: /usr/bin/xindex exists in filesystem
  texlive-core: /usr/bin/xindy exists in filesystem
  texlive-core: /usr/share/fontconfig/conf.avail/09-texlive-fonts.conf exists in filesystem
  texlive-core: /usr/share/libalpm/hooks/mktexlsr.hook exists in filesystem
  texlive-core: /usr/share/libalpm/hooks/texlive-fmtutil.hook exists in filesystem
  texlive-core: /usr/share/libalpm/hooks/texlive-updmap.hook exists in filesystem
  texlive-core: /usr/share/libalpm/scripts/mktexlsr exists in filesystem
  texlive-core: /usr/share/libalpm/scripts/texlive-fmtutil exists in filesystem
  texlive-core: /usr/share/libalpm/scripts/texlive-updmap exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLConfFile.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLConfig.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLCrypto.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLDownload.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLPDB.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLPOBJ.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLPSRC.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLPaper.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLTREE.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLUtils.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TLWinGoo.pm exists in filesystem
  texlive-core: /usr/share/tlpkg/TeXLive/TeXCatalogue.pm exists in filesystem
  texlive-bibtexextra: /usr/bin/bbl2bib exists in filesystem
  texlive-bibtexextra: /usr/bin/bib2gls exists in filesystem
  texlive-bibtexextra: /usr/bin/bibdoiadd exists in filesystem
  texlive-bibtexextra: /usr/bin/bibexport exists in filesystem
  texlive-bibtexextra: /usr/bin/bibmradd exists in filesystem
  texlive-bibtexextra: /usr/bin/biburl2doi exists in filesystem
  texlive-bibtexextra: /usr/bin/bibzbladd exists in filesystem
  texlive-bibtexextra: /usr/bin/convertgls2bib exists in filesystem
  texlive-bibtexextra: /usr/bin/listbib exists in filesystem
  texlive-bibtexextra: /usr/bin/ltx2crossrefxml exists in filesystem
  texlive-bibtexextra: /usr/bin/multibibliography exists in filesystem
  texlive-bibtexextra: /usr/bin/urlbst exists in filesystem
  texlive-bibtexextra: /var/lib/texmf/arch/installedpkgs/texlive-bibtexextra_58697.pkgs exists in filesystem
  Errors occurred, no packages were upgraded.
  ```
03. That is, there will be a lot of complaint about files already **exist in the filesystem**. The solution? Weel, it turned out to have a quite simple solution -- Delete the mentioned the files, yes, delete them all!
  - You can copy those error messages and use, say, `vim` to edit a shell script to run `rm` efficiently
  - Or you can use the `fc` command, which is more or less the same thing as above
04. After the deletion of the above-mentioned files, you're good to go: Just `pacman -S texlive-most`



