# VAM — maximizing overall Vim experience
“VAM” is short name for vim-addon-manager.
You declare a set of plugins. VAM will fetch & activate them at startup or
runtime depending on your needs. Activating means handling runtimepath and
making sure all .vim file get sourced.

## If you believe in VAM's collaborative properties
then you may also want to have a look at [vim-git-wiki](https://github.com/MarcWeber/vim-git-wiki)
If you contribute to this git based wiki editable by Vim we have a chance
making it official ot www.vim.org.


## MINIMAL setup (3 lines)

    set runtimepath+=/path/to/vam
    call vam#ActivateAddons([])
    VAMActivate tlib matchit.zip
    " find plugins by :VAMPluginInfo NAME and completion
    " VAMActivateInstalled (this is like pathogens "infect"

Keep reading to get an overview about VAM by
- skimming this README.md file
- Read about how to make your .vimrc bootstrap VAM (check it out)
  by looking at the minimal install example (Section 2)
[doc/\*getting-started.txt](https://raw.github.com/MarcWeber/vim-addon-manager/master/doc/vim-addon-manager-getting-started.txt).


## FEATURES
- Declarative: The behaviour of Vim is determined by your .vimrc only. [1]
- Automatic runtimepath handling: install/ update/ use manually installed addons 
  on startup or load them lazily as needed when you feel that way. [3]
- Builtin dependency management. [2]
- Based on a [pool](http://mawercer.de/~marc/vam/index.php) of addons which is 
  maintained by the community. This allows warning you if you’re going to 
  install outdated packages. Of course you can opt-out and use your own pool 
  easily.
- Sources from www.vim.org, git, mercurial, subversion, bazaar, darcs, [...]
- Addon name completion in .vim files and :(Update|Activate)Addons commands.
- Short syntax for github repos: `github:name/repo`.
- Optionally writes update logs.
- Cares about [windows users](http://mawercer.de/~marc/vam/index.php).
- Addon info by name or script id (:AddonInfo).
- Tries to preserve user modifications by using diff/patch tools on unix like
  environments (for non-version-controlled sources).
- 100 % VimL (is this really that good?..)

[1]: assuming you always use latest versions

[2]: this serves the community by making it easy to reuse other’s code. 
     Implemented by a addon-info.json file and patchinfo database for addons 
     without VAM support.

[3]: Yes — there are some special cases where it does not work correctly because 
     some autocommands don’t get triggered

[4]: Plugin authors should use addon-info file instead. patchinfo.vim is for 
     addons not supporting VAM.

## SUPPORT
VAM is well supported by at least 2 maintainers. Try github tickets or Vim irc
channel on freenode.

## Let me see all docs!
Here you go:

- [GETTING STARTED](https://raw.github.com/MarcWeber/vim-addon-manager/master/doc/vim-addon-manager-getting-started.txt)
- [additional docs](https://raw.github.com/MarcWeber/vim-addon-manager/master/doc/vim-addon-manager-additional-documentation.txt)

## CONTACT / HELP
See contact information in GETTING STARTED documentation.

## BUGS
It’ll never have nice install progress bars — because the “progress” is not very 
well known because addons can be installed at any time — and additionall 
dependencies may be encountered.

If you want to be able to rollback you have to use git submodules yourself or 
find a different solution — because VAM also supports other VCS and installing 
from archives.

## Related work

[vim-wiki's list of alternatives](http://vim-wiki.mawercer.de/wiki/topic/vim%20plugin%20managment.html)

[debian’s vim plugin manager](http://packages.debian.org/sid/vim-addon-manager)
The author (Jamessan) is fine with this project sharing the same name.
