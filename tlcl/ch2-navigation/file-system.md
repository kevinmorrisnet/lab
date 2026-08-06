## Navigation

**Hierarchical Directory Structure**

- tree like pattern

```bash
.
├── chap1-shell
│   └── commands.md
├── chap2-navigation
│   └── file-system.md
└── README.md
```

- inverted tress structure
- current working directory shown by command `pwd`
- "print working directory"

```bash
/home/kevin/DevOps/Repos/github/tlcl
```

- path above current directory is "parent" directory

`ls` lists files in current dir

```bash
chap1-shell
chap2-navigation
README.md
```

`cd` followed by the path of the desired directory

### Absolute Pathnames

$ cd /usr/bin
kevin@ubuntu-7050:/usr/bin
$ pwd
/usr/bin

### Relative Pathnames

`.` current directory
`..` parent directory

- filesare case sensitive
- filename begin with a period charcater are hidden "dotfiles"
- do not embed spaces in filenames

```bash
cd                # changes working dir to home dir
cd -              # changes to previous dir
cd ~user_name     # changes to home dir of the user_name
