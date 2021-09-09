# Matchroot

Match root is inspired by Rooter but is more restrictive on the different types of workspaces it can find.

To find a project root you can specify 3 things:
 - directory/files needed
 - optional files that can make the root finding easier
 - file that discalify the directory as root

## Usage
By default the plugin do nothing to enable it you need to populate the `g:mroot_pats` list of patterns.
```viml
let g:mroot_pats = ['rust_crate', 'git-workspace']
```

## Features
### Add custom patterns
To add your custom paterns to the ones provided by the plugins populate the `g:mroot_custom_pats` dictionary.
For each entry of the dictionary 3 list are provided. The first one need to be non empty.
Here are all the ones provided by the plugin as an example:
```viml
let g:mroot_custom_pats = {
    \ 'rust-crate'      : [['Cargo.toml', 'src/'],['build.rs', 'rustmft.toml', 'doc/'],['*.rs']],
    \ 'rust-workspace'  : [[],[],[]],
    \ 'git-workspace'   : [['.git/'],['Readme.md', 'REARME.md'],[]],
    \ 'Cmake-workspace' : [['Cmakelist.txt'],[],[]]
}
```

### Set into manual mode.
```viml
let g:disable_auto_matching = 1
```

### Define the depth of the search
```viml
let g:mroot_search_max_depth = 4
```

### Define default fallback root dir
```viml
let g:mroot_default_dir = 'home'
```

